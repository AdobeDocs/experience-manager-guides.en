---
title: Changes in the extension framework with the new Editor
description: Learn how change in the extension framework with the new Editor
feature: Web Editor Configuration
role: Admin
level: Experienced
---

# Changes in the extension framework with the new Editor

The move to **Editor 2.0** introduces a much-needed shift in how extensions interact with the Editor. Instead of relying on the rendered DOM and editor-specific APIs, the new framework is built around a **ProseMirror backed document model**, accessed through commands and utilities.

This change addresses many long-standing issues,fragility, inconsistent behavior across modes, and non-persistent updates while making extension code more predictable and maintainable.


## Updating XML attributes (root element)

Instead of traversing the DOM, XML attributes are set directly on the root node using a MarkupEditor command. Since the root element is always at a known position in ProseMirror, updates are reliable, persist across rerenders, work независимо of DOM state, and avoid coupling to legacy editor APIs.

**Legacy approach**

- Locate the root element in DOM (`editor.rootElement.findOne('[data-tcx-tag="concept"]')`)
- Call legacy mutation API `editor.updateAttributes(...)` per key

```ts
export const updateAttributes = ({ editor, attributeProps }) => {
  const rootElement = editor.rootElement.findOne('[data-tcx-tag="concept"]')

  attributeProps &&
    Object.keys(attributeProps).forEach((key) => {
      const attribute = {};
      attribute[key] = attributeProps[key];
      editor.updateAttributes(attribute, rootElement);
    });
};
```

**New approach**

- Do not traverse DOM.
- Set `xml` attributes on the root node using a MarkupEditor command.
- In ProseMirror, the root element is accessed at a known position.

```ts
export const updateAttributes = ({ editor, attributeProps }) => {
  // MarkupEditor: no DOM/rootElement access; update root node xmlAttrs via commands.
  // Keep the `editor` arg for call-site compatibility, but do not depend on legacy APIs.
  if (!attributeProps) {
    return false;
  }

  // Root element is at position 0 in ProseMirror.
  return guides.editor.runCommand("setNodeXmlAttributes", 0, attributeProps);
};
```

## Saving after metadata update

Saving is a global editor lifecycle action and should be routed through the app's event system rather than a specific editor instance. Since `tcx.curEditor` may not always be present or active, an event-driven approach ensures saves are centralized, consistent, and easier to manage across modes.

**Legacy approach**

```ts
if (hasUpdateAttributeSuccess) {
  tcx.curEditor?.saveFile?.();
}
```

**New approach**

```ts
if (hasUpdateAttributeSuccess) {
  tcx.eventHandler.next(tcx.eventHandler.KEYS.AUTHOR_SAVE_FILE);
}
```

## Updating cross-reference display text for selected `xref`

One of the more fragile areas in the legacy system is updating cross-reference display text. The new approach reads directly from the document model rather than the rendered DOM, ensuring accuracy regardless of how the content is displayed. This approach works reliably in preview or hybrid modes where DOM selection may be unreliable, and is based on stable semantics like the `xref` node, its `id`, and associated `XML attributes`.

This often results in changes that appear temporarily but get lost after re-rendering.

**Legacy approach**

- Grab `const { editor } = tcx.curEditor;`
- Use `editor.rootDocument.getSelection()` and crawl the DOM from the anchor node
- Read a DOM attribute like `data-xref-display`

```ts
const { editor } = tcx.curEditor;
const showXrefSelection =
  editor?.rootDocument?.getSelection()?.anchorNode?.parentNode;
const placeHolderText =
  "Xref Placeholder Text: " +
  showXrefSelection?.getAttribute("data-xref-display") ||
  showXrefSelection?.parentElement?.getAttribute("data-xref-display");
this.setValue("selectedXrefPlaceholderText", placeHolderText);
```

**New approach**

- Find `xref` nodes via `findPositionRanges("xref")`
- Match by `id`
- Read `xmlAttrs.placeholdertext` (or `placeholdertext`) via `getAttributeAtPosition`

```ts
let placeholderTextValue = "";
try {
  const xrefRanges =
    guides?.editor?.runUtil?.("findPositionRanges", "xref") || [];

  for (const range of xrefRanges) {
    const xmlAttrs = guides.editor.runUtil(
      "getAttributeAtPosition",
      range.from,
      "xmlAttrs"
    ) as Record<string, any> | undefined;

    const resolvedId = guides.editor.runUtil(
      "getAttributeAtPosition",
      range.from,
      "id"
    ) as string | undefined;

    const xrefId = resolvedId || xmlAttrs?.id;
    if (xrefId !== selectedXrefId) continue;

    placeholderTextValue =
      (xmlAttrs?.placeholdertext as string | undefined) ||
      (guides.editor.runUtil(
        "getAttributeAtPosition",
        range.from,
        "placeholdertext"
      ) as string | undefined) ||
      "";
    break;
  }
} catch (e) {
  console.warn(
    "[cross_reference_dialog:init] Unable to read xref placeholder text (continuing).",
    e
  );
}

this.setValue(
  "selectedXrefPlaceholderText",
  "Xref Placeholder Text: " + (placeholderTextValue || "-")
);
```

## Determine the source `topic id`

Accessing the root element no longer depends on querying the DOM or relying on rendering-specific markers like `data-tcx-tag`. Instead, the ProseMirror root node is always present at a stable position, allowing it to be accessed directly without assumptions about DOM structure or rendering state.

**Legacy approach**

```ts
if (tcx.curEditor && tcx.curEditor.editor && tcx.curEditor.editor.rootDocument) {
  sourceTopicID =
    tcx.curEditor.editor.rootDocument.querySelector('[data-tcx-tag="concept"]').id;
}
```

**New approach**

Read the root element id from ProseMirror:

```ts
// Root element is at position 0.
const resolvedRootId = guides.editor.runUtil(
  "getAttributeAtPosition",
  0,
  "id"
) as string | undefined;

const rootXmlAttrs = guides.editor.runUtil(
  "getAttributeAtPosition",
  0,
  "xmlAttrs"
) as Record<string, any> | undefined;

sourceTopicID = resolvedRootId || (rootXmlAttrs?.id as string) || "";

```

## Updating display text of `xref` when saving

**Legacy approach (DOM mutation based)**

- Used `editor.selectedHtml` and parsed it.
- Mutated DOM attributes (`data-xref-display`) on selected elements.
- Read DOM selection (`editor.rootDocument.getSelection()`).

This is the classic ProseMirror trap: changing DOM does **not** mean you changed the document. It might look right for a moment, then the editor rerenders and your change is gone.

**New approach (model mutation via command)**

On save:

- Find the xref position by matching `id` in the document.
- Update the XML attribute `placeholdertext` using `setNodeXmlAttribute`.

```ts
const findXrefPosById = (): number | null => {
  const xrefId = this.getValue("xrefId");
  if (!xrefId) return null;

  const ranges = guides.editor.runUtil?.("findPositionRanges", "xref") || [];
  for (const range of ranges) {
    const idAtPos = guides.editor.runUtil?.(
      "getAttributeAtPosition",
      range.from,
      "id"
    );
    if (idAtPos && String(idAtPos) === String(xrefId)) {
      return range.from;
    }
  }
  return null;
};

const xrefPos = findXrefPosById();
if (xrefPos !== null) {
  guides.editor.runCommand(
    "setNodeXmlAttribute",
    xrefPos,
    "placeholdertext",
    updatedXrefText
  );
} else {
  console.warn(
    "[crossReferenceDialog/saveCrossref] Could not locate xref position to update placeholdertext"
  );
}
```