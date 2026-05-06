---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2026.05.0 release
description: Learn about the bug fixes in the 2026.05.0 release of Adobe Experience Manager Guides as a Cloud Service.

---
# Fixed issues in the 2026.05.0 release 

This article covers the bugs fixed in various areas of the 2026.05.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2026.05.0 release](whats-new-2026-05-0.md).

Learn about [upgrade instructions for the 2026.05.0 release](upgrade-instructions-2026-05-0.md).

## Authoring

- When selecting an image in the Editor using the **Select file** dialog, only raster formats (such as JPG, PNG, and GIF) are displayed. Vector files (such as .ai and .eps) are not shown and cannot be selected. (GUIDES-45110)
- At the time of upgrade, the `tagsView` setting is turned off by default, even though its default value in `ui_config.json` is set to `true`. (GUIDES-44651)
- In the Editor, file references are displayed as GUIDs instead of file paths despite the `xmleditor.uuid` configuration. (GUIDES-42438)
- When Subject schemes with similar key values are applied in a DITA topic, they are highlighted with nearly identical colors, making it difficult to distinguish them and identify which scheme is applied. (GUIDES-38472)
- When editing a Subject Scheme map in the Author view, adding the `hasInstance` element automatically triggers the file selection dialog, requiring authors to insert an unwanted `href` pointing to an AEM asset. In addition, the **Content properties** panel fails to load for such maps, which prevents authors from updating element attributes in Author view and requires them to use Source view for updating attributes. (GUIDES-38164)
- When editing a `.ditaval` file, any XML comments added in the Source view are removed when you switch to Author view and then return to Source view. (GUIDES-33228)


## Asset management

- Creating a topic in a folder with spaces in its name incorrectly creates a duplicate folder where spaces are replaced by hyphens, and the topic is saved there instead of the original folder. (GUIDES-41938)
- During first-time translation of large maps, empty XML files are created for the destination language, leading to increased server load and slower performance. (GUIDES-41613)
- In DB-based environments, valid internal DITA links appear as broken links in **Asset Properties**, even though they work correctly in the Editor and in published output. (GUIDES-35048)

## Publishing 

- When changes to an output preset in a Folder profile are applied to existing maps, the saved **Publish Context** for the AEM Sites preset is reset. (GUIDES-38377)
- The trademark symbol (&reg;) does not render on the cover page of the Native PDF output when the `tm` element is used within the title of a map or bookmap. (GUIDES-28832)
- When publishing a map using a Native PDF template, the **Map title** does not include content from the child elements used within the map `title`, and the corresponding content filtering is not applied to the title.(GUIDES-33730)
- Cross-map peer links in AEM Sites output fail to resolve when they point to a `topicref` that uses `chunk="to-content"`. (GUIDES-37873)
- During publishing, files associated with DITAVAL-based flagging are moved to a new system-generated folder instead of remaining in their expected relative location in the output. (GUIDES-37564)
- When multiple DITAVAL files with conflicting conditions are used, the Native PDF output fails. (GUIDES-37484)

## Baseline

- Topic references within a map are incorrectly shown as indirect when using a custom DITA-OT, even though they are directly referenced. This issue has been resolved with the new baseline experience. (GUIDES-19286)
- References with `scope="peer"` are incorrectly included in the baseline context, causing publishing to take longer than expected. This issue has been resolved with the new baseline experience. (GUIDES-30048)

## Platform

- When large topics or maps are opened, the Author instance becomes unresponsive, requiring a restart in some cases. (GUIDES-43547)

## Resolved issues available with Editor 2.0

The following issues have been fixed, and no longer occur when using Editor 2.0 (aka New Editor):

- When two or more columns are deleted from a table, the table structure becomes inconsistent or corrupted. (GUIDES-35438)
- When a column is deleted from a table that contains merged cells, a new blank column is added. (GUIDES-30147)
- When a new row is inserted in an existing table from the breadcrumbs menu, the table structure changes unexpectedly, resulting in missing borders and an extra column. (GUIDES-29194)
- In the Author view, copying and pasting a table row places the content outside the table instead of inserting it as a new row within the table. (GUIDES-24372)
- When a section element selected using mouse drag in Author mode is copied and pasted, it is converted into paragraph `(<p>)` elements instead of retaining the section structure. (GUIDES-30023)
- When highlighted text inside elements such as step or uicontrol is edited, the selected text is not replaced correctly and is appended or prepended instead, resulting in validation errors. (GUIDES-24371)
- When a table column width is set using relative values, the remaining columns do not adjust proportionally, causing a misaligned table layout. (GUIDES-26109)
- When a copied topic title is pasted with tags disabled, the first paste applies incorrect styling and assigns the type in Content properties as topic instead of title. (GUIDES-28838)
- When large sections of content are edited, unintended scroll movement causes the Editor view to jump away from the active content. (GUIDES-35436)
- When Backspace is used on elements, the Editor scrolls to the top of the topic regardless of the cursor position. (GUIDES-32520)
- When the left or right arrow key is used to move out of inline tags, the cursor jumps unexpectedly on the first attempt. (GUIDES-26363)
- AEM Spellcheck works only for the default en-US language and does not honor other locales. (GUIDES-14731)
- When large DITA topics are unlocked in the Editor, the same topic reopens in a duplicate tab. Additionally, a tag-limit warning is triggered where `NaN` is displayed instead of the actual tag count. (GUIDES-34008)
- Acrolinx suggestions are not highlighted correctly in the Editor for read-only or locked topics. (GUIDES-29614)
- When creating a new `reltable` without a header row in Author view, the table layout changes after a topic is added to the first cell, causing the next column to collapse and making it difficult to place related topics. (GUIDES-19555)
- When an `xref` link is added to a small table cell in Author mode, the link does not stay contained within the cell and appears across adjacent cells in the same row. (GUIDES-5489)
- When switching from Author to Source view,  the cursor position is not retained, and the Editor scrolls back to the top. Additionally, in long topics, the cursor position is lost and randomly jumps to the middle or top when toggling between Author and Source views. (GUIDES-18114, GUIDES-21164)
- Pressing *Enter* inside an `<li>` element creates a new `<li>`, but navigating back to a previous `<li>` and pressing *Enter* incorrectly converts the current item's content into a `<p>` element, breaking the list structure. (GUIDES-27505)

## Known issues

Adobe has identified the following known issues for the 2026.05.0 release:

- When a map contains an external `topicref` pointing to a non-DITA resource (such as `.html` or `.htm`), its preview is not displayed  in the Assets UI. (GUIDES-45409)
- In the Assets UI, content referenced using `conref` fails to appear for DITA topics, even though it renders correctly in the Editor preview. (GUIDES-45505)<br>**Workaround**: For such content, you can use Editor's preview.
- When `xmleditor.uniquefilenames` property is enabled, new topics created using a template do not include the topic title. (GUIDES-44737)

