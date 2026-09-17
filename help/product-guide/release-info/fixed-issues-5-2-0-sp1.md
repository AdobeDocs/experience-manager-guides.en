---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 5.2.0 Service Pack 1 release
description: Learn about the bug fixes in the 5.2.0 Service Pack 1 release of Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
---
# Fixed issues in the 5.2.0 Service Pack 1 release (September 2026)


This article covers the bugs fixed in various areas of 5.2.0 Service Pack 1 release of Adobe Experience Manager Guides.

Learn about [upgrade instructions for the 5.2.0 Service Pack 1 release](upgrade-instructions-5-2-0-sp1.md).

## Authoring

- On low-resolution screens, the Insert Keyword dialog fails to appear when inserting a keyword from the toolbar, while it opens as expected when using the **More** option. (GUIDES-48304)
- Inserting a cross-reference using the **Web link** option adds a `scope=local` link and modifies the `href` value, instead of inserting a `scope=external` link as expected. (GUIDES-48457)
- Saving a referencing map results in a broken reference instead of resolving to the correct map when one author moves the referenced map while another author is concurrently adding a reference to it in an unsaved map. (GUIDES-47467)
- Alphanumeric terms added to the dictionary are still flagged by the AEM spell checker instead of being ignored. (GUIDES-48587)
- When toggling focus between the **Width** and **Height** fields in the image properties dialog using unit-based sizes such as `in`, `mm`, or `px`, the values keep incrementally increasing instead of remaining stable. (GUIDES-45929)
- In the Editor, file references are displayed as GUIDs instead of file paths despite the xmleditor.uuid configuration. (GUIDES-42438)

## Editor 2.0

- Whitespace entered immediately before an inline tag within a table cell `<entry>` is deleted. (GUIDES-49144)
- Inserting an element at the `tgroup` position displays a **#text is not allowed here** warning, preventing a normal table from being inserted at that position. (GUIDES-47446)
- Copying a table from an Excel spreadsheet and pasting it into the New Editor places all copied cell content into a single table cell instead of distributing it across the corresponding cells. (GUIDES-47435)
- A custom **Export as PDF** button configured through `editor_toolbar.json` renders and remains clickable in Preview mode, but does not perform any action when clicked. (GUIDES-47402)
- Opening certain topics containing tables adds an unexpected `<foreign>` tag with two new columns, even when no changes were made to the topic. (GUIDES-46748)
- When a MathML equation is inserted as a `conref`, it does not render correctly. (GUIDES-46601)
- MathML and SVG elements do not render their complete set of attributes, causing custom CSS classes and conditional attributes applied to these elements to break. (GUIDES-46371)
- The **Scale** attribute does not apply to images in Author view. (GUIDES-45996)
- Applying a `scale` attribute to a table does not render the table at the configured size in Author and Preview modes. (GUIDES-45984)
- Pasting images copied from external sources such as Paint or the Snipping Tool does not insert the image into the topic. (GUIDES-45983)
- Copying and pasting `<keywords>` inside `<topicmeta>` within a `<keydef>` or `<topicref>` results in the keywords being inserted inside unwanted foreign tags. (GUIDES-45800)
- In the Tag view of a table, pressing the up arrow key when the cursor is positioned at the cell directly below a collapsed entry tag skips over the collapsed tag and moves the cursor to the beginning of the document. (GUIDES-45408)
- Performing any operation from the table contextual toolbar closes the toolbar unexpectedly, interrupting subsequent table operations. (GUIDES-45405)
- The **Edit MathML** option is incorrectly displayed in read-only mode or when a file is checked out by another user, allowing users to update MathML content even though the file should not be editable. (GUIDES-45172)
- After using **Insert After** or **Insert Before** from the Outline view or breadcrumb, the cursor moves to an arbitrary position instead of inside the newly added tag. (GUIDES-45147)
- When performing a drag-and-drop with Tag view enabled, selecting content along with partial XML or DITA tags leaves behind unwanted orphan tags, resulting in incorrect content or view. (GUIDES-28191)

## Asset management

- The version purge utility fails to complete in several scenarios, including certain file types, assets with missing metadata, and large reports, instead of completing the purge and generating an accurate report. (GUIDES-43453)

## Publishing

- Non-English filenames in the generated page names are replaced with hyphens, making it difficult to identify the topic or file it is associated with, when publishing AEM Sites output using legacy component mapping. (GUIDES-48387)
- Vulnerable `jackson-databind` JARs (version 2.9.8) bundled with AEM Guides in the DITA-OT package are identified. (GUIDES-43081)

## Review

- Opening the **side-by-side** view in the Comments panel displays the working copy alongside the commented version, but the panes do not scroll in sync horizontally, and clicking a comment does not move the cursor to the corresponding text. (GUIDES-44083)

## Platform

- Using `scope="external"` for a reference to DAM content within a topic or map causes the asset’s relative path to be substituted with a GUID. (GUIDES-35605)
- For content created before UUID migration, downloading a map with the **Retain file hierarchy** and **Use actual file name** options selected incorrectly converts the `href` values of `topicref`, `xref`, and `conref` elements with `scope="external"` to GUID-based filenames instead of retaining the original relative filepaths. As a result, the external references are broken. (GUIDES-46526)
- When uploading assets through Assets UI, the upload status is not shown. (GUIDES-7207)

## Known issues

- When changing a `keyref` value in the Source view of the New Editor, a **key not found** error is incorrectly displayed, even when the specified key is valid. (GUIDES-49998)
- When performing a review operation inside a code block, an **Operation not allowed** warning is displayed on the first attempt, but the operation succeeds when repeated. (GUIDES-56749)
- Code block or `<pre>` content is displayed on a single line, without line breaks, in the Review UI. (GUIDES-56105)
- Selecting a processing instruction (PI) element in Outline view highlights the entire parent tag instead of just the PI element. (GUIDES-48318)
- Content deletion issues in the New Editor including unexpected cursor behavior when deleting image maps, Prolog elements, content with empty formatting tags, and non-mergeable blocks. (GUIDES-46756)
- MathML equation wrapped inside `foreign`/`equation-block` causes unwanted spaces and editing issues. (GUIDES-46756)
- With **Display tags** enabled and **Display attributes** disabled, placing the cursor inside a `topicref` within a reltable incorrectly highlights the `topicmeta` element. (GUIDES-46565)
- In the New Editor, deleting the display text of an `xref` using Backspace incorrectly displays a read-only warning near reusable content and can delete the character preceding the `xref`. (GUIDES-45049)
- In the New Editor, the breadcrumb does not update immediately after renaming an inline element and requires moving inside the tag or switching views to reflect the change. (GUIDES-44993)
- In Full Tags view, conditions applied to an element such as `bodydiv` visually overflow into the next tag. (GUIDES-44971)

