---
title: Auto-generate element IDs
description: Learn how to Auto-generate element IDs
feature: Web Editor Configuration
role: Admin
level: Experienced

---
# Extension Framework API

This document covers all APIs added to `guides.editor` (and `guides`) as part of the extension framework for the MarkupEditor (ProseMirror-based editor). These APIs allow external extensions to interact with the editor without direct DOM manipulation or internal implementation knowledge.

## Overview

The global `guides` object is the entry point for all extension integrations:

```js
guides.editor    // Editor interaction APIs
guides.util      // Utility libraries (lodash, async)
guides.ready(cb) // Lifecycle hook — fires when the editor is fully loaded
```

All `guides.editor` APIs are safe to call from extension controllers, toolbar handlers, and dialog logic.

## Lifecycle

`guides.ready(callback)`: Registers a callback to execute once the page view manager has fully loaded. Use this before registering plugins or performing any editor setup.

**Signature:**

```ts
guides.ready(callback: () => void): void
```

**Example:**

```js
guides.ready(() => {
  // Safe to access guides.editor APIs here
  guides.editor.registerPlugin(createMyPlugin);
});
```

## Editor state properties

- `guides.editor.filePath`: Returns the file path of the currently active document.

  **Type:** `string | undefined`

  **Example: reading file path for a metadata API call:**

  ```js
  const filePath = guides.editor.filePath;
  if (filePath) {
  tcx.api.getMetadata(filePath).subscribe((metadata) => {
    // use metadata...
    });
  }
  ```

  **Example: conditional logic based on file location**

    ```js
    const filePath = guides.editor.filePath;
    if (filePath?.endsWith(".ditamap")) {
      // ditamap-specific handling
    }
    ```

- `guides.editor.version`: Returns the version string of the currently loaded editor.

  | Value   | Editor                             |
  |---------|------------------------------------|
  | `1.0.0` | Legacy CKEditor (`xml_author_view`) |
  | `2.0.0` | MarkupEditor (ProseMirror-based)   |

  **Type:** `string`

  **Example:**

  ```js
  if (guides.editor.version === '2.0.0') {
    // MarkupEditor-specific logic
  }
  ```

- `guides.editor.appState(keyName)`: Reads a value from the application model by key name.

  **Signature:**

  ```ts
  guides.editor.appState(keyName: string): unknown
  ```

  **Example:**

  ```js
  const editorMode = guides.editor.appState('editorMode');
  ```

## Editor interaction

- `guides.editor.focus()`: Sets focus to the active editor. Call this before executing commands that require the editor to have focus.

  **Signature:**

  ```ts
  guides.editor.focus(): boolean
  ```

  **Example: focus before inserting content**

  ```js
  guides.editor.focus();
  const hasSelection = !!guides.editor.runUtil('hasSelection');
  // ...proceed with wrap or insert
  ```

- `guides.editor.canInsertXmlElement(tagName, insertAfter?)`: Checks whether a given XML element can be inserted at the current cursor position.

  **Signature:**

  ```ts
  guides.editor.canInsertXmlElement(tagName: string, insertAfter?: boolean): boolean
  ```

  **Example: guard before inserting `<xref>`**

  ```js
  const canInsert = guides.editor.canInsertXmlElement("xref");
  if (!canInsert) {
    return tcx.util.showAlert("warning", "xref is not allowed here");
  }
  ```

  **Example: guard before inserting `<sup>` / `<sub>`**

  ```js
  const canInsert = guides.editor.canInsertXmlElement("sup");
  if (!canInsert) {
    return tcx.util.showAlert("warning", "superscript is not allowed here");
  }
  ```

- `guides.editor.selectCurrentBlockElement()`: Selects the current block-level element in the editor.

  **Signature:**

  ```ts
  guides.editor.selectCurrentBlockElement(): boolean
  ```

  **Example:**

  ```js
  guides.editor.selectCurrentBlockElement();
  ```

- `guides.editor.getValidElementNamesForInsertion(args)`: Returns a list of valid XML element names that can be inserted at the current position.

  **Signature:**

  ```ts
  guides.editor.getValidElementNamesForInsertion(args: {
    insertMode?: 'after' | 'before' | 'rename',
    strict: boolean
  }): string[] | false
  ```

  **Example:**

  ```js
  const validElements = guides.editor.getValidElementNamesForInsertion({
    insertMode: 'after',
    strict: true
  });
  ```

- `guides.editor.updateAttributeByXpath(args)`: Updates a specific XML attribute on a node identified by its XPath. Delegates to the active editor's `updateAttributeByXpath` method.

  **Signature:**

  ```ts
  guides.editor.updateAttributeByXpath(args: UpdateXpathArgs): any
  ```

## Command Execution

- `guides.editor.runCommand(commandName, ...args)`: Executes a named command on the MarkupEditor. Returns `true` if the command succeeded, `false` otherwise.

  **Signature:**

  ```ts
  guides.editor.runCommand(commandName: string, ...args: any[]): boolean
  ```

  **Available Commands**

  | Command | Arguments | Description |
  |---|---|---|
  | `setNodeXmlAttributes` | `position: number, attrs: Record<string, unknown>` | Sets multiple XML attributes on the node at `position` |
  | `setNodeXmlAttribute` | `position: number, attrName: string, value: string` | Sets a single XML attribute on the node at `position` |
  | `surroundWithElement` | `tagName: string, attrs?: Record<string,unknown>, replaceTextWithEmptyNode?: boolean` | Wraps the current selection with the given element |
  | `insertXml` | `xml: string, position?: number, options?: InsertXmlOptions` | Inserts raw XML at the cursor or given position |
  | `unwrapNode` | _(none)_ | Removes the current node's wrapper element, keeping its content |

  - **Example: Set multiple attributes on a node**

    ```js
    guides.editor.runCommand(
      "setNodeXmlAttributes",
      rootRange.from,
      { createdDate: "2024-01-01", author: "Jane Doe" }
    );
    ```

  - **Example: Set a single attribute on a node**
  
    ```js
    guides.editor.runCommand(
      "setNodeXmlAttribute",
      range.from,
      "placeholdertext",
      "Chapter 3 — Safety Requirements"
    );
    ```

  - **Example: Wrap selection with an element and set attributes**

    ```js
    const didWrap = guides.editor.runCommand(
      "surroundWithElement",
      "ph",
      { outputclass: "highlight" },
      true   // replace text content with empty node
    );
    ```

  - **Example: Wrap selection in `<sup>` (toggle superscript on)**

    ```js
    const didWrap = guides.editor.runCommand('surroundWithElement', 'sup');
    if (!didWrap) {
      tcx.util.showAlert("warning", "superscript is not allowed here");
    }
    ```

  - **Example: Unwrap current node (toggle superscript off)**
  
    ```js
    const didUnwrap = guides.editor.runCommand('unwrapNode');
    ```

  - **Example: Insert XML at cursor with caret placed inside**

    ```js
    guides.editor.runCommand(
      'insertXml',
      '<sup></sup>',
      undefined,
      { setCursorInContent: true, focusEditor: true, selectInsertedXml: false }
    );
    ```



- `guides.editor.canRunCommand(commandName, ...args)`: Checks whether a named command can currently be executed, without actually running it.

  **Signature:**

  ```ts
  guides.editor.canRunCommand(commandName: string, ...args: any[]): boolean
  ```

  **Example:**

  ```js
  if (guides.editor.canRunCommand('surroundWithElement', 'sup')) {
    guides.editor.runCommand('surroundWithElement', 'sup');
  }
  ```

## Utility Functions

- `guides.editor.runUtil(utilName, ...args)`: Invokes a named utility from the MarkupEditor's utility registry. Returns the utility's result, or `undefined` if the utility is not found.

  **Signature:**

  ```ts
  guides.editor.runUtil(utilName: string, ...args: any[]): any
  ```

  **Available Utilities**

  | Utility | Arguments | Returns | Description |
  |---|---|---|---|
  | `getTextPos` | _(none)_ | `number` | Current cursor position in the ProseMirror document |
  | `getAncestorsNames` | `position?: number` | `string[]` | XML tag names of ancestor nodes at `position` |
  | `getAncestorsDetails` | _(none)_ | `{ currNode: string, ancestors: Array<{tagName:string}> }` | Current node and ancestor details |
  | `getAncestorXpaths` | `includeId?: boolean` | `AncestorXpathItem[]` | XPath strings for all ancestor nodes |
  | `findPositionRange` | `tagName: string` | `{ from: number, to: number } \| undefined` | Finds the ProseMirror range of the first element with the given tag |
  | `findPositionRanges` | `tagName: string` | `Array<{ from: number, to: number }>` | Finds all ProseMirror ranges for elements matching `tagName` |
  | `getAttributeAtPosition` | `position: number, attrName: string` | `unknown` | Reads an XML attribute value from the node at `position` |
  | `getSerializableAttributes` | `xpath: string` | `Record<string, unknown>` | Returns all serializable XML attributes for the node at `xpath` |
  | `getSelectedXml` | _(none)_ | `string` | Returns the currently selected content as an XML string |
  | `getSelectedPlainText` | _(none)_ | `string` | Returns the currently selected content as plain text |
  | `hasSelection` | _(none)_ | `boolean` | Returns `true` if there is an active text/node selection |
  | `getNodePosition` | _(none)_ | `number` | Returns the document position of the currently selected/focused node |

  **Example: get cursor position and ancestor names**

  ```js
  const textPos = guides.editor.runUtil("getTextPos");
  const ancestorNames = guides.editor.runUtil(
    "getAncestorsNames",
    typeof textPos === "number" ? textPos : undefined
  );
  ```

  **Example: find all `<xref>` elements and read their attributes**

  ```js
  const xrefRanges = guides.editor.runUtil("findPositionRanges", "xref") || [];
  xrefRanges.forEach((range) => {
    const id = guides.editor.runUtil("getAttributeAtPosition", range.from, "id");
    const placeholderText = guides.editor.runUtil(
      "getAttributeAtPosition",
      range.from,
      "placeholdertext"
    );
  });
  ```

  **Example: find the root element range and read its attributes**

  ```js
  const rootRange = guides.editor.runUtil("findPositionRange", "concept"); // or "topic"
  if (rootRange) {
    const createdDate = guides.editor.runUtil(
      "getAttributeAtPosition",
      rootRange.from,
      "createdDate"
    );
    const author = guides.editor.runUtil(
      "getAttributeAtPosition",
      rootRange.from,
      "author"
    );
  }
  ```

  **Example: check selection and validate ancestor context before an operation**

  ```js
  const ancestorsDetails = guides.editor.runUtil('getAncestorsDetails');
  const selectedText = guides.editor.runUtil('getSelectedPlainText');
  const hasSelection = !!guides.editor.runUtil('hasSelection');

  const firstAncestor = ancestorsDetails?.currNode || ancestorsDetails?.ancestors?.[0]?.tagName;
  if (firstAncestor === 'ph') {
    tcx.util.showAlert("warning", "Operation is not allowed inside this element type.");
    return;
  }
  ```

  **Example: get element IDs from ancestor XPaths**

  ```js
  const ancestorItems = guides.editor.runUtil('getAncestorXpaths', true);
  for (const item of ancestorItems) {
    const attrs = guides.editor.runUtil('getSerializableAttributes', item.xpath);
    if (attrs?.id) { /* use element ID */ }
  }
  ```

---

## Decoration API

The Decoration API provides a higher-level alternative to writing full ProseMirror plugins for common visual customizations. Instead of managing `Plugin`, `PluginKey`, and `DecorationSet` manually, you describe *what* to decorate and *how*, and the editor's central decoration manager handles the ProseMirror state internally.

Decorations are identified by a string `id` so they can be updated or removed independently at any time.

>[!NOTE]
>
> **MarkupEditor only** These APIs are no-ops on the legacy editor (`version === '1.0.0'`).

- `guides.editor.addDecoration(id, selector, options)`: Adds or replaces a decoration rule. All nodes matching `selector` in the current document will be decorated according to `options`. The decoration is re-applied automatically on every document change.

  **Signature:**

  ```ts
  guides.editor.addDecoration(
    id: string,
    selector: string,
    options: DecorationOptions
  ): boolean
  ```

  **`DecorationOptions` fields:**

  | Field | Type | Description |
  |---|---|---|
  | `class` | `string` | CSS class name(s) added to matching nodes |
  | `computeAttributes` | `(node, context) => Record<string, string>` | Function returning dynamic `data-*` or other HTML attributes per node |
  | `filter` | `(node) => boolean` | Optional predicate — only nodes where this returns `true` are decorated |

  The `context` object passed to `computeAttributes` includes:
  - `index` — 0-based position of the node among siblings matching the selector

  **Example: add a CSS class to all `<section>` elements**

  ```js
  guides.editor.addDecoration('highlight-sections', 'section', {
    class: 'my-section-highlight'
  });
  ```

  **Example: add a computed `data-number-label` attribute to each section**

  ```js
  guides.editor.addDecoration('section-numbers', 'section', {
    computeAttributes: (node, context) => ({
      'data-number-label': String(context.index + 1)
    })
  });
  ```

  **Example: decorate only sections that have `importance="high"` attribute**

  ```js
  guides.editor.addDecoration('important-sections', 'section', {
    class: 'section-important',
    filter: (node) => node.attrs?.xmlAttrs?.importance === 'high'
  });
  ```

  **Example: combine class and computed attributes**

  ```js
  guides.editor.addDecoration('numbering-mode', 'conbody', {
    class: 'legacy-numbering'
  });

  guides.editor.addDecoration('section-numbers', 'section', {
    computeAttributes: (node, context) => ({
      'data-number-label': String(context.index + 1)
    })
  });
  ```

- `guides.editor.removeDecoration(id)`: Removes a previously added decoration by its ID.

  **Signature:**

  ```ts
  guides.editor.removeDecoration(id: string): boolean
  ```

  **Example:**

  ```js
  guides.editor.removeDecoration('section-numbers');
  ```

- `guides.editor.batchDecorations(changes)`: Applies multiple add/remove decoration changes in a single ProseMirror dispatch. Use this when toggling several decorations at once to avoid multiple re-renders.

  **Signature:**

  ```ts
  guides.editor.batchDecorations(changes: DecorationBatchChange[]): boolean

  type DecorationBatchChange =
    | { action: 'add', id: string, selector: string, options: DecorationOptions }
    | { action: 'remove', id: string }
  ```

  **Example: switch between two numbering modes atomically**

  ```js
  guides.editor.batchDecorations([
    { action: 'remove', id: 'legacy-numbering' },
    {
      action: 'add',
      id: 'division-numbering',
      selector: 'conbody',
      options: { class: 'division-numbering' }
    }
  ]);
  ```

  **Example: clear one decoration and add two new ones**

  ```js
  guides.editor.batchDecorations([
    { action: 'remove', id: 'old-highlights' },
    {
      action: 'add',
      id: 'section-labels',
      selector: 'section',
      options: {
        computeAttributes: (node, ctx) => ({ 'data-section-index': String(ctx.index) })
      }
    },
    {
      action: 'add',
      id: 'note-style',
      selector: 'note',
      options: { class: 'styled-note' }
    }
  ]);
  ```

---

- `guides.editor.clearDecorations()`: Removes all active decorations managed by the decoration manager.

  **Signature:**

  ```ts
  guides.editor.clearDecorations(): boolean
  ```

  **Example:**

  ```js
  guides.editor.clearDecorations();
  ```

- `guides.editor.getDecorations()`: Returns the IDs of all currently active decorations.

  **Signature:**

  ```ts
  guides.editor.getDecorations(): string[]
  ```

  **Example:**

  ```js
  const active = guides.editor.getDecorations();
  console.log('Active decorations:', active);
  // e.g. ['section-numbers', 'numbering-mode', 'note-style']
  ```


### Decoration API vs `registerPlugin`

| Scenario | Use |
|---|---|
| Apply a CSS class or `data-*` attributes to matching elements | `addDecoration` |
| Toggle or update styling based on runtime state (metadata, user action) | `addDecoration` / `removeDecoration` / `batchDecorations` |
| Complex plugin logic: custom state, key bindings, widget decorations, event handlers | `registerPlugin` |
| Injecting CSS into the shadow DOM | `registerPlugin` with `css` field |


## ProseMirror Plugin Registration

- `guides.editor.registerPlugin(factory)`: Registers a ProseMirror plugin factory to be included in every MarkupEditor instance. Only factory functions are accepted, direct plugin instances are rejected. The factory is called once per editor instance, ensuring isolated plugin state.

  **Signature:**

  ```ts
  guides.editor.registerPlugin(factory: () => PluginConfig): void

  interface PluginConfig {
    plugin: ProseMirrorPlugin | ProseMirrorPlugin[]
    css?: string  // Injected into editor's shadow DOM
  }
  ```

  **Example: register plugins after the editor is ready**

  ```js
  guides.ready(() => {
    guides.editor.registerPlugin(createNumberingPlugin);
    guides.editor.registerPlugin(createXrefPlugin);
  });
  ```

  **Example: inline factory with CSS**

  ```js
  guides.editor.registerPlugin(() => ({
    plugin: new guides.editor.prosemirror.state.Plugin({
      key: new guides.editor.prosemirror.state.PluginKey("myPlugin"),
      props: {
        decorations(state) {
          // return DecorationSet...
        }
      }
    }),
    css: `.my-decoration { background: yellow; }`
  }));
  ```

  > [!NOTE]
  >
  > CSS passed via `css` is injected into the editor's shadow DOM. Regular page-level stylesheets do not apply inside the editor.


## ProseMirror Libraries

- `guides.editor.prosemirror`: Exposes ProseMirror packages directly for use in plugin development. This avoids the need to bundle ProseMirror separately in extension code.

  | Property | Package |
  |---|---|
  | `state` | `prosemirror-state` |
  | `model` | `prosemirror-model` |
  | `view` | `prosemirror-view` |
  | `transform` | `prosemirror-transform` |
  | `commands` | `prosemirror-commands` |
  | `keymap` | `prosemirror-keymap` |
  | `history` | `prosemirror-history` |
  | `tables` | `prosemirror-tables` |
  | `dropcursor` | `prosemirror-dropcursor` |
  | `collab` | `prosemirror-collab` |
  | `markdown` | `prosemirror-markdown` |

  **Example: create a node decoration plugin**

  ```js
  const myPluginKey = new guides.editor.prosemirror.state.PluginKey("myPlugin");

  const createMyPlugin = () => {
    const { Plugin } = guides.editor.prosemirror.state;
    const { Decoration, DecorationSet } = guides.editor.prosemirror.view;

    return {
      plugin: new Plugin({
        key: myPluginKey,
        state: {
          init() { return { enabled: true }; },
          apply(tr, value) {
            const meta = tr.getMeta(myPluginKey);
            return meta ? { ...value, ...meta } : value;
          }
        },
        props: {
          decorations(state) {
            const decorations = [];
            state.doc.descendants((node, pos) => {
              if (node.type.name === "section") {
                decorations.push(
                  Decoration.node(pos, pos + node.nodeSize, { class: "my-section" })
                );
              }
            });
            return DecorationSet.create(state.doc, decorations);
          }
        }
      }),
      css: `.my-section { border-left: 3px solid #ccc; padding-left: 8px; }`
    };
  };
  ```

  **Example: create a widget decoration plugin (inline display text)**

  ```js
  const xrefPluginKey = new guides.editor.prosemirror.state.PluginKey("xrefDisplay");

  const createXrefPlugin = () => {
    const { Plugin } = guides.editor.prosemirror.state;
    const { Decoration, DecorationSet } = guides.editor.prosemirror.view;

    return {
      plugin: new Plugin({
        key: xrefPluginKey,
        props: {
          decorations(state) {
            const decorations = [];
            state.doc.descendants((node, pos) => {
              if (node.type.name.includes("xref")) {
                const display = node.attrs?.xmlAttrs?.placeholdertext;
                if (display) {
                  decorations.push(
                    Decoration.widget(pos + 1, () => {
                      const el = document.createElement("span");
                      el.textContent = `[${display}]`;
                      el.setAttribute("contenteditable", "false");
                      return el;
                    }, { key: `xref-${pos}` })
                  );
                }
              }
            });
            return DecorationSet.create(state.doc, decorations);
          }
        }
      }),
      css: `.xref-display-text { color: #0074d9; pointer-events: none; }`
    };
  };
  ```

## Injecting CSS into the Editor

The Guides DITA editor loads its author-mode content styles from a clientlib with category `apps.guides.dita_editor.content`. That clientlib has an `embed` declaration that automatically pulls in any clientlib registered under the category:

```
apps.guides.xml_editor.dita_content_overrides
```

To inject custom CSS into the editor's content area, create an AEM clientlib node with this category. No additional wiring is needed, Guides picks it up automatically when the editor page loads.

**AEM clientlib node structure (`/apps/my-extension/clientlibs/editor-content-overrides/.content.xml`)**

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:cq="http://www.day.com/jcr/cq/1.0"
          xmlns:jcr="http://www.jcp.org/jcr/1.0"
    jcr:primaryType="cq:ClientLibraryFolder"
    categories="[apps.guides.xml_editor.dita_content_overrides]"/>
```

Place your CSS file (`css.txt` + your `.css` file) inside this folder. It will be embedded into the editor's content stylesheet automatically.

**Example: override section heading styles in author mode**

```css
/* /apps/my-extension/clientlibs/editor-content-overrides/css/content.css */

/* Increase section title font size in author mode */
.section > title {
  font-size: 1.4em;
  font-weight: bold;
  color: #333;
}

/* Highlight note blocks */
.note {
  border-left: 4px solid #0074d9;
  padding-left: 12px;
  background: #f0f7ff;
}
```

> [!NOTE]
>
>This CSS targets the legacy CKEditor-based author surface only. It has no effect inside the MarkupEditor (ProseMirror), which uses a shadow DOM.


### New MarkupEditor: `css` in `registerPlugin`

The MarkupEditor renders inside a **shadow DOM**, which isolates it from all page-level styles, including AEM `clientlibs`. To inject CSS into the MarkupEditor's author surface, pass a `css` string as part of the `PluginConfig` returned by your plugin factory.

The CSS is injected as a `<style>` tag directly inside the editor's shadow root each time an editor instance is created.

**Example: inject styles alongside a decoration plugin**

```js
guides.ready(() => {
  guides.editor.registerPlugin(() => ({
    plugin: createMyPlugin(), // your ProseMirror plugin
    css: `
      /* Styles scoped to the MarkupEditor shadow DOM */
      .section > .title-node {
        font-size: 1.4em;
        font-weight: bold;
        color: #333;
      }

      .note-node {
        border-left: 4px solid #0074d9;
        padding-left: 12px;
        background: #f0f7ff;
      }
    `
  }));
});
```

**Example: CSS-only plugin (no decoration logic)**

```js
guides.ready(() => {
  guides.editor.registerPlugin(() => ({
    plugin: new guides.editor.prosemirror.state.Plugin({}), // no-op plugin
    css: `
      /* Custom author-mode typography */
      [data-xml-element="codeblock"] {
        font-family: monospace;
        background: #f5f5f5;
        padding: 8px;
        border-radius: 4px;
      }
    `
  }));
});
```

>[!NOTE]
>
> This CSS only applies inside the MarkupEditor shadow DOM. It has no effect on the rest of the page or on the legacy editor.


## Context Menu Extensions (`contextMenuWidget`)

Extensions can add items to the editor's right-click / breadcrumb context menu by declaring a `contextMenuWidget` field in their extension config. This tells the framework which editor's menu to target.

### Widget IDs

| Widget ID | Editor |
|---|---|
| `dita_editor_menu` | Legacy CKEditor author surface (breadcrumb + element context menu) |
| `markup_editor_menu` | New MarkupEditor (ProseMirror) breadcrumb & element context menu |

Both widgets are mounted on the page simultaneously. The framework matches each extension to the correct menu based on this field.

> Extensions can also target both editors by passing an array: `contextMenuWidget: ["dita_editor_menu", "markup_editor_menu"]`

---

### Legacy editor: `dita_editor_menu`

Use this for extensions that should appear in the legacy CKEditor context menu.

```js
const myContextMenuExtension = {
  id: "dita_author_view_menu",
  contextMenuWidget: "dita_editor_menu",
  view: {
    items: [
      {
        displayName: "My Custom Action",
        data: { eventid: "myCustomAction" },
        icon: "textSpaceAfter",
        target: {
          key: "displayName",
          value: "Wrap Element",   // insert after this existing menu item
          viewState: "append",
        },
      },
    ],
  },
  controller: {
    myCustomAction() {
      console.log("Custom action triggered");
    },
  },
};
```

---

### New MarkupEditor: `markup_editor_menu`

Use this for extensions that should appear in the MarkupEditor context menu (breadcrumbs and right-click on elements). The controller receives events via `handleExtensionEvent`, which routes local handlers to the `markup_editor_menu` controller and dispatches global events through the app event handler.

```js
const myMarkupContextMenu = {
  id: "dita_author_view_menu",
  contextMenuWidget: "markup_editor_menu",
  view: {
    items: [
      {
        displayName: "Edit Cross Reference",
        data: { eventid: "editCrossReference" },
        icon: "link",
        target: {
          key: "displayName",
          value: "Cut",
          viewState: "prepend",
        },
      },
      {
        displayName: "Remove Cross Reference",
        data: { eventid: "removeCrossReference" },
        icon: "deleteOutline",
        target: {
          key: "displayName",
          value: "Edit Cross Reference",
          viewState: "append",
        },
      },
    ],
  },
  controller: {
    editCrossReference() {
      // Use guides.editor APIs to read context
      const ancestorXpaths = guides.editor.runUtil("getAncestorXpaths", true);
      // open dialog or take action...
    },
    removeCrossReference() {
      guides.editor.runCommand("unwrapNode");
    },
  },
};
```

---

## Utility Libraries

- `guides.util.lodash`:The lodash utility library, same instance bundled with the editor.

  ```js
  const uniqueIds = guides.util.lodash.uniq(ids);
  ```

- `guides.util.async`: Async utility library for extension use.

  ```js
  guides.util.async.parallel([task1, task2], callback);
  ```

## Complete API Reference

| API | Description |
|---|---|
| `filePath` | Get the active document's file path |
| `version` | Get the loaded editor version string |
| `appState(key)` | Read a value from the application model |
| `focus()` | Focus the active editor |
| `canInsertXmlElement(tag, insertAfter?)` | Check if an element can be inserted at cursor |
| `selectCurrentBlockElement()` | Select the current block element |
| `getValidElementNamesForInsertion(args)` | List valid element names for insertion |
| `updateAttributeByXpath(args)` | Update an attribute by XPath |
| `runCommand(name, ...args)` | Execute a named editor command |
| `canRunCommand(name, ...args)` | Check if a command can execute |
| `runUtil(name, ...args)` | Invoke a named editor utility |
| `addDecoration(id, selector, options)` | Add or replace a named decoration rule on matching elements |
| `removeDecoration(id)` | Remove a decoration rule by ID |
| `batchDecorations(changes)` | Apply multiple add/remove decoration changes in one dispatch |
| `clearDecorations()` | Remove all active decoration rules |
| `getDecorations()` | Get IDs of all currently active decorations |
| `registerPlugin(factory)` | Register a ProseMirror plugin factory (also the mechanism for shadow DOM CSS injection) |
| `prosemirror.state` | `prosemirror-state` package |
| `prosemirror.model` | `prosemirror-model` package |
| `prosemirror.view` | `prosemirror-view` package |
| `prosemirror.transform` | `prosemirror-transform` package |
| `prosemirror.commands` | `prosemirror-commands` package |
| `prosemirror.keymap` | `prosemirror-keymap` package |
| `prosemirror.history` | `prosemirror-history` package |
| `prosemirror.tables` | `prosemirror-tables` package |
| `prosemirror.dropcursor` | `prosemirror-dropcursor` package |
| `prosemirror.collab` | `prosemirror-collab` package |
| `prosemirror.markdown` | `prosemirror-markdown` package |

