---
title: Migrating Extension framework changes for Editor 2.0
description: Learn about the migration to extension framework for Editor 2.0
feature: Web Editor Configuration
role: Admin
level: Experienced
---

# Migrate Extension framework to Editor 2.0 (New Editor)

This guide helps extension authors understand what's involved in moving their customizations from the **Old Editor** to the **New Editor** in AEM Guides, so that they can plan their transition smoothly and with minimal disruption.

>[!IMPORTANT]
> 
> If you have an existing AEM Guides extension (Old Editor), including custom context menu items, toolbar buttons, dialogs, attribute or metadata logic, or content styling, this guide helps you keep it working with the New Editor.


## Overview

1. **Your registration does not change**: Keep using `window.extension` / `tcx.extension.register`.
2. **The Editor canvas is a new surface.** Context-menu items must declare the new widget id
   `markup_editor_menu`; in-editor behavior must stop touching the DOM.
3. **Stop reading/writing the DOM**: Replace `tcx.curEditor.*` DOM access with the
   `guides.editor` API: read with `runUtil(...)`, write with `runCommand(...)`, style with
   decorations, and run global actions (save) through app events.
4. **App-shell menus (repository, map viewer, file/folder) are unchanged**: they still run on
   the legacy framework.
5. **Both editors coexist** Target both with arrays. **Register** plugins unconditionally at load;
   gate only *runtime* actions by `guides.editor.version` (which stays `1.0.0` until a file is
   open, view [Detect the editor and bootstrap safely](#detect-the-Editor-and-bootstrap-safely)).


## Why the change?

|Criteria | Legacy CKEditor | New MarkupEditor |
|---|---|---|
| Source of truth | DOM | ProseMirror document |
| Selection | `getSelection()` on a root document | ProseMirror selection (positions/ranges) |
| To change content | Mutate DOM attributes/classes | Dispatch a command (transaction) |
| Rendering | DOM is permanent | DOM is an ephemeral render in a shadow DOM, rebuilt at any time |
| Styling | Page or clientlib CSS | CSS injected shadow DOM |

Any extension that mutates the DOM, parses `selectedHtml`, or holds the Editor
object *appears* to work for a moment and then break on the next rerender. The migration is
fundamentally *move from DOM-first to model-first*.

## Detect the Editor and bootstrap safely

The global `guides` object is the entry point for all new integrations:

```js
guides.editor    // editor interaction APIs
guides.util      // bundled utility libs (lodash, async)
guides.ready(cb) // fires once at app load (view system ready) — before any file is open
```

`guides.editor.version` reports the **currently open editor**, so it is only meaningful once a
file is actually open:

| `guides.editor.version` | Meaning |
|---|---|
| `2.0.0` | A MarkupEditor (ProseMirror) file is open |
| `1.0.0` | A legacy CKEditor file is open or no file is open yet |

>[!IMPORTANT]
>
> When the `guides.ready` event occurs, no file has yet opened, so `version` will report as `1.0.0` regardless of whether MarkupEditor is enabled. Do not use `version` to determine whether plugins get *registered* (view [Plugin Registration and Runtime Gating](#plugin-registration-and-runtime-gating)). Use it only to branch *runtime* behavior, and evaluate it at the point of execution (e.g., within a menu handler), where a file is guaranteed to be open.

### Plugin registration and runtime gating

- **Registration** (`registerPlugin`, one-time setup): run it **unconditionally** in `guides.ready`. It is a harmless no-op on the legacy editor: the legacy editor never reads the plugin registry, and your factory runs only when a MarkupEditor is actually constructed. It does **not** throw.

- **Runtime calls** (`runCommand`, `runUtil`, `addDecoration`, …): gate by `version === '2.0.0'` at
  call time. They don't throw on the legacy editor (they safely return `false`/`undefined`), but
  gating avoids no-op warnings and lets you keep a legacy fallback.

```js
guides.ready(() => {
  // Always register — inert on legacy, applied only when a MarkupEditor opens.
  guides.editor.registerPlugin(createMyPlugin);
});

function onMenuClick() {
  if (guides.editor.version === '2.0.0') {
    guides.editor.runCommand('surroundWithElement', 'sup'); // MarkupEditor path
  } else {
    // legacy path (or no-op)
  }
}
```

Pass a **factory** `() => ({ plugin, css })` — to `registerPlugin`, never a constructed plugin instance. A non-function is the only input it rejects (throws on both editors). Do not cache the editor instance; call `guides.editor.*` fresh each time.

**Hello world: a CSS-only highlight plugin**

The smallest useful extension ships **only CSS** a no-op ProseMirror plugin plus styles. This
highlights every `<note>` element with a yellow background inside the editor:

```js
guides.ready(() => {
  guides.editor.registerPlugin(() => ({
    plugin: new guides.editor.prosemirror.state.Plugin({}), // no behavior — CSS only
    css: `[data-xml-element="note"] { background: #fff3cd; outline: 1px solid #ffe08a; }`
  }));
});
```

- Every element renders as `data-xml-element="<tag>"`, so you can target any DITA element that way
  (`note`, `codeblock`, `section`, `table`, …).
- CSS **must** ship via the plugin: the editor lives in a shadow DOM, so page/clientlib CSS can't
  reach it.
- Open a DITA topic containing a `<note>` to see it applied. Registration is unconditional (§2.1),
  so this is safe even though `version` is still `1.0.0` at `guides.ready` time.


## Inventory your extension (grep checklist)

```bash
# DOM-first reads that will break
grep -rnE "rootDocument|rootElement|getSelection\(|selectedHtml|selectedText|\.xmlDoc|\.ancestors\b" src

# DOM/legacy writes that will break
grep -rnE "updateAttributes\(|setAttribute\(|classList\.|\.saveFile\(|resetDirty\(|validateRangeForInsertion\(" src

# The editor handle itself
grep -rn "tcx.curEditor" src

# Context-menu targeting + page CSS
grep -rnE "contextMenuWidget|dita_editor_menu|author_outline_element" src
grep -rn "dita_content_overrides" .
```

Every hit is a migration item. Classify each as: *context-menu surface*, *state read*, *content
write*, *global action*, *rendering-only*, or *CSS*.


## Common for both the Editors

The following behaviors and structures apply identically to both the Editors:

- **Registration:** `window.extension[id] = config` and/or `tcx.extension.register(id, config)` on
  the `tcx-loaded` event.
- **Config object shape:** `{ id, contextMenuWidget, view: { items }, controller }`.
- **App-shell context menus** keep their existing widget ids and the legacy behavior:

  | Surface | Widget id (unchanged) |
  |---|---|
  | Repository panel (file/folder) | `repository_panel` / `file_options` / `folder_options` |
  | Map viewer | `ditamap_viewer` / `map_view_options` |
  | Baseline / preset panels | `baseline_panel_menu` / `preset_item_menu` |

  Items targeting these surfaces need **no change** for the New Editor, do not move them to
  `markup_editor_menu`.

## Migrate context-menu items (Editor canvas)

This applies only to menus that targeted the **editor** (`dita_editor_menu`,
`author_outline_element`), i.e. the right-click / breadcrumb menu inside the editing surface.

### How it routes on the New Editor

```
window.extension[id]  ─►  filtered by contextMenuWidget == 'markup_editor_menu'
                      ─►  view.items rendered in the canvas menu
   (click) ───────────►  fires an extension event:
                          • eventid is a known global key  → run as a built-in editor command
                          • otherwise                       → your controller[eventid]() runs
```

### Add the new widget id (array keeps legacy working)

```js
// BEFORE
contextMenuWidget: 'dita_editor_menu',
// AFTER
contextMenuWidget: ['dita_editor_menu', 'markup_editor_menu'],
```

### Keep the expected shape

- Actionable items live under `view.items` with a `data.eventid`.
- Each `controller` method name **matches** its `eventid` exactly.

```js
view: {
  items: [{
    displayName: 'Edit Cross Reference',
    icon: 'link',
    data: { eventid: 'editCrossReference' },
    target: { key: 'displayName', value: 'Cut', viewState: 'prepend' }
  }]
},
controller: {
  editCrossReference() { /* runs on click */ }
}
```

### Re-anchor `target`

The new menu resolves `target` against the MarkupEditor's own menu items.

- `target.key`: `displayName | id | icon | eventid`
- `target.viewState`: `append | prepend | replace`
- Anchor to a stable native item such as **`Cut`**.
- If the anchor does not resolve, the item still appears but lands at the default position
  (not an error, fix the anchor).

### Choose the routing per item

```js
data: { eventid: 'AUTHOR_CUT' }          // built-in command → routed natively, no controller needed
data: { eventid: 'editCrossReference' }  // custom → runs controller.editCrossReference()
```

Add `readOnly: true` on an item that must stay enabled in read-only content.

### Rewrite the handler body

Handlers usually read the selection and mutate a node, migrate those off the DOM.

## Migrate reads (DOM → `runUtil`)

```js
// BEFORE — DOM selection / queries
const { editor } = tcx.curEditor;
const html = editor.selectedHtml;
const topicId = editor.rootDocument.querySelector('[data-tcx-tag="concept"]').id;

// AFTER — read from the document model
const selectedXml = guides.editor.runUtil('getSelectedXml');
const hasSel      = !!guides.editor.runUtil('hasSelection');
const topicId     = guides.editor.runUtil('getAttributeAtPosition', 0, 'id'); // root = position 0
```

Find a node by tag, match by id, read an XML attribute:

```js
let value = '';
for (const range of (guides.editor.runUtil('findPositionRanges', 'xref') || [])) {
  const id = guides.editor.runUtil('getAttributeAtPosition', range.from, 'id');
  if (String(id) !== String(targetId)) continue;
  value = guides.editor.runUtil('getAttributeAtPosition', range.from, 'placeholdertext') || '';
  break;
}
```

**Read utilities:** `getTextPos`, `getNodePosition`, `getSelectedXml`, `getSelectedPlainText`,
`hasSelection`, `getAncestorsNames`, `getAncestorsDetails`, `getAncestorXpaths`,
`findPositionRange`, `findPositionRanges`, `getAttributeAtPosition`, `getSerializableAttributes`.


## Migrate writes (DOM mutation → `runCommand`)

```js
// BEFORE
const root = editor.rootElement.findOne('[data-tcx-tag="concept"]');
editor.updateAttributes({ docOwner: 'Jane' }, root);

// AFTER — update the model; persists across rerenders
guides.editor.runCommand('setNodeXmlAttributes', 0, { docOwner: 'Jane' });
```

```js
// Set one attribute at a found position
guides.editor.runCommand('setNodeXmlAttribute', pos, 'placeholdertext', text);

// Wrap / insert / unwrap
guides.editor.runCommand('surroundWithElement', 'sup');
guides.editor.runCommand('insertXml', '<sup></sup>', undefined, { setCursorInContent: true });
guides.editor.runCommand('unwrapNode');
```

**Prerequisite**

```js
guides.editor.focus();
if (!guides.editor.canInsertXmlElement('xref')) {
  return tcx.util.showAlert('warning', 'xref is not allowed here');
}
if (guides.editor.canRunCommand('surroundWithElement', 'sup')) {
  guides.editor.runCommand('surroundWithElement', 'sup');
}
```

**Commands:** `setNodeXmlAttributes`, `setNodeXmlAttribute`, `surroundWithElement`, `insertXml`,
`unwrapNode`.

For xpath-based updates, use the facade method `guides.editor.updateAttributeByXpath(xpath, name, value)` (not a `runCommand`).


## Migrate global actions (save/focus → app events)

```js
// BEFORE
tcx.curEditor?.saveFile?.();
// AFTER
tcx.eventHandler.next(tcx.eventHandler.KEYS.AUTHOR_SAVE_KEY);
```
`resetDirty(...)` and `tcx.curEditor.html` have no MarkupEditor equivalent so drop them; saving
through the event handles dirty state centrally. Use `guides.editor.focus()` for focus.


## Migrate rendering-only logic (DOM paint → decorations)

Anything that added CSS classes, `data-*` attributes, or "display text" by mutating the DOM must
become a **decoration**, or it vanishes on rerender. Below are simple declarative cases:

```js
guides.editor.addDecoration('important-sections', 'section', {
  class: 'section-important',
  computeAttributes: (node, ctx) => ({ 'data-number-label': String(ctx.index + 1) }),
  filter: (node) => node.attrs?.xmlAttrs?.importance === 'high'
});

guides.editor.batchDecorations([
  { action: 'remove', id: 'legacy-numbering' },
  { action: 'add', id: 'division-numbering', selector: 'conbody', options: { class: 'division-numbering' } }
]);

guides.editor.removeDecoration('important-sections');
guides.editor.clearDecorations();
guides.editor.getDecorations();
```
Complex cases (custom state, broken-state via transaction meta, widget text): Register a
ProseMirror plugin once, using the exposed libraries:

```js
const createXrefPlugin = () => {
  const { Plugin, PluginKey } = guides.editor.prosemirror.state;
  const { Decoration, DecorationSet } = guides.editor.prosemirror.view;
  return {
    plugin: new Plugin({ key: new PluginKey('xrefDisplay'), props: { decorations(state) { /* … */ } } }),
    css: `.xref-broken { text-decoration: underline wavy red; }`
  };
};

guides.ready(() => guides.editor.registerPlugin(createXrefPlugin));
```

Register plugins at app load (once), not inside dialogs or repeatedly, the registry does not dedupe. `registerPlugin` accepts a **factory function only**, not a plugin instance.
`guides.editor.prosemirror` exposes: `state`, `model`, `view`, `transform`, `commands`, `keymap`,
`history`, `tables`, `dropcursor`, `collab`, `markdown`.


## Migrate CSS (page clientlib → shadow DOM)

The MarkupEditor renders inside a **shadow DOM**; page-level and AEM clientlib CSS do not reach it.

```js
guides.editor.registerPlugin(() => ({
  plugin: new guides.editor.prosemirror.state.Plugin({}),   // no-op, CSS only
  css: `[data-xml-element="codeblock"] { font-family: monospace; background: #f5f5f5; }`
}));
```
The legacy content clientlib category (`apps.guides.xml_editor.dita_content_overrides`) still
styles the legacy editor only, keep it if you support both, but know it is inert on MarkupEditor.

## API replacement reference

| Legacy (`tcx.curEditor…` / DOM) | New MarkupEditor |
|---|---|
| `tcx.curEditor.filePath` | `guides.editor.filePath` |
| `getSelection()` / `selectedHtml` / `selectedText` | `runUtil('getSelectedXml' / 'getSelectedPlainText' / 'hasSelection')` |
| `rootDocument.querySelector(tag)` | `runUtil('findPositionRange' / 'findPositionRanges', tag)` |
| element `.getAttribute` / `xmlDoc.attributes` | `runUtil('getAttributeAtPosition', pos, name)` / `getSerializableAttributes(xpath)` |
| root id (`querySelector('[concept]').id`) | `runUtil('getAttributeAtPosition', 0, 'id')` |
| `editor.ancestors` | `runUtil('getAncestorsDetails' / 'getAncestorXpaths')` |
| `editor.updateAttributes(attrs, root)` | `runCommand('setNodeXmlAttributes', 0, attrs)` |
| set attr on element | `runCommand('setNodeXmlAttribute', pos, name, value)` |
| wrap / insert / unwrap selection | `runCommand('surroundWithElement' / 'insertXml' / 'unwrapNode', …)` |
| `canInsertXmlElement` / `validateRangeForInsertion` | `canInsertXmlElement(tag)` / `canRunCommand(name, …)` |
| `editor.focus()` | `guides.editor.focus()` |
| `tcx.curEditor.saveFile()` | `tcx.eventHandler.next(KEYS.AUTHOR_SAVE_KEY)` |
| `setAttribute` / `classList` for styling | `addDecoration` / `batchDecorations` / `registerPlugin` |
| page/clientlib CSS for editor content | `registerPlugin({ css })` (shadow DOM) |
| `contextMenuWidget: 'dita_editor_menu'` | `['dita_editor_menu', 'markup_editor_menu']` |


## Common issues

- **Item doesn't appear in the New Editor menu**: `contextMenuWidget` is missing
  `markup_editor_menu`, or the config was registered *after* the editor opened (config is read
  once at editor construction register at app load).
- **Item appears in the wrong place**: `target` anchor doesn't resolve; anchor to an item that
  exists in the new menu (e.g. `Cut`).
- **Change "works" then disappears**: You mutated the DOM. Use a command (write) or a decoration
  (style) instead.
- **CSS has no effect**: It's page-level; the editor is in a shadow DOM. Use `registerPlugin({ css })`.
- **Unsafe guards throw**: Patterns like `if (!tcx.curEditor && !tcx.curEditor.editor)` evaluate
`.editor` on a falsy object. Guard on `guides.editor` capabilities instead:
`if (!guides?.editor) return;`.
- **Trying to migrate app-shell menus**: Repository/map/file menus are not the editor canvas;
  leave them on their legacy widget ids.

## Verification checklist

- Context-menu items appear in **both** the legacy and MarkupEditor menus.
- Items land in expected position.
- Custom `eventid` runs `controller[eventid]`; global keys fire the built-in command.
- State reads return correct values after typing/rerender (model, not stale DOM).
- Content writes *persist after save and reopen*.
- Decorations survive a rerender.
- Shadow-DOM CSS visibly applies inside the editor.
- Save fires via `AUTHOR_SAVE_KEY` and clears dirty state.
- `readOnly` items behave correctly in locked content.
- Preview or side-by-side; intentional read-only DOM work is left as-is.
- `grep -rn "tcx.curEditor" src` is clean (or only the documented, intentional remainder).
- Plugins registered exactly once, inside `guides.ready`.


## Suggested rollout sequence

1. **Bootstrap**: Wrap setup in `guides.ready`; register plugins unconditionally and add `version` gating around *runtime* actions only (For details, view [Plugin Registration and Runtime Gating](#plugin-registration-and-runtime-gating)).
2. **Context-menu surface**: Add `markup_editor_menu`, fix `target` anchors. Items now appear.
3. **Reads**: Migrate selection/attribute reads to `runUtil`.
4. **Writes**: Migrate mutations to `runCommand`; saves to app events.
5. **Rendering**: Move DOM styling to decorations / `registerPlugin`; move CSS to shadow DOM.
6. **Harden**: Fix unsafe guards, remove the editor handle, verify on both editors.

Migrate one surface at a time and keep the legacy paths working (arrays + version gating) so a
single extension build runs on both editors throughout the transition.