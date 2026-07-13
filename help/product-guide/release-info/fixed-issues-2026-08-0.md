---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2026.08.0 release
description: Learn about the bug fixes in the 2026.08.0 release of Adobe Experience Manager Guides as a Cloud Service.

---
# Fixed issues in the 2026.08.0 release 

This article covers the bugs fixed in the various areas of the 2026.08.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2026.08.0 release](whats-new-2026-08-0.md).

Learn about [upgrade instructions for the 2026.08.0 release](upgrade-instructions-2026-08-0.md).

## Authoring 

- Topics fail to open in the Editor when accessed from the Map Dashboard. (GUIDES-45277)


## Editor 2.0

- When a MathML equation is inserted as a `conref`, it does not render correctly. (GUIDES-46601)
- Copying and pasting `<keywords>` inside `<topicmeta>` within a `<keydef>` or `<topicref>` results in the keywords being inserted inside unwanted foreign tags. (GUIDES-45800)
- Using `Ctrl+click` on a broken link in a Map editor triggers an application error. (GUIDES-45544)
- Copying a table from an Excel spreadsheet and pasting it into the New Editor places all copied cell content into a single table cell instead of distributing it across the corresponding cells. (GUIDES-47435)
- A custom **Export as PDF** button configured through `editor_toolbar.json` renders and remains clickable in Preview mode, but does not perform any action when clicked. (GUIDES-47402)
- MathML and SVG elements do not render their complete set of attributes, causing custom CSS classes and conditional attributes applied to these elements to break. (GUIDES-46371)
- Opening certain topics containing tables adds an unexpected `<foreign>` tag with two new columns, even when no changes were made to the topic. (GUIDES-46748)
- The **Scale** attribute does not apply to images in Author view. (GUIDES-45996)
- Dragging and dropping an element containing a `keyref` converts the `keyref` value into an absolute path. (GUIDES-45701)
- Inserting an element at the `tgroup` position displays a **#text is not allowed here** warning, preventing a normal table from being inserted at that position. (GUIDES-47446)
- Custom editor extensions built for the New Editor do not work correctly in some cases, affecting integrations such as cursor positioning, table alignment, and context menu behavior. (GUIDES-46524)


## Asset management

- Bulk asset processing incorrectly includes Content Fragment assets, causing error logs and failures in the processing reports. (GUIDES-47085)
- In the Map Panel, child topics fail to load and the expand icon disappears when the map checkbox is selected and unselected repeatedly. (GUIDES-43546)

## Publishing

**AEM Sites**

When publishing AEM Sites output using composite component mapping:

- A blank **Topic list** is displayed when a new baseline is used in the AEM Sites preset with composite component mapping. (GUIDES-46480)
- Cross-reference (`xref`) links to non-DITA assets such as PDF, ZIP, DOCX, and image files do not resolve correctly, resulting in broken links on the generated page. (GUIDES-44108)

When publishing AEM Sites output using legacy component mapping:

- Publishing fails when using DITA-OT 4. (GUIDES-28024)
- Non-English filenames in the generated page names are replaced with hyphens, making it difficult to identify the topic or file it is associated with. (GUIDES-48387)

**Native PDF**

- In Native PDF output, topic references marked with `toc="no"` attribute are still included in the TOC, resulting in a lengthy and cluttered table of contents. (GUIDES-37940, GUIDES-20156)

## Review

- In the Review UI, the tagging list displays all users in the review task, which makes it difficult to select the correct user in a comment or reply. (GUIDES-33420)
- Opening the **side-by-side** view in the Comments panel displays the working copy alongside the commented version, but the panes do not scroll in sync horizontally, and clicking a comment does not move the cursor to the corresponding text. (GUIDES-44083)

## Database 

- `DatabaseConfiguratorService` throws an error in the logs even when the `GUIDES_ENABLE_DATABASE` flag is not set. (GUIDES-43481)
