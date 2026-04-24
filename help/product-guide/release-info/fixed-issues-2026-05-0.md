---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2026.05.0 release
description: Learn about the bug fixes in the 2026.05.0 release of Adobe Experience Manager Guides as a Cloud Service.

---
# Fixed issues in the 2026.05.0 release 

This article covers the bugs fixed in various areas of the 2026.05.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2026.05.0 release](whats-new-2026-05-0.md).

Learn about [upgrade instructions for the 2026.05.0 release](upgrade-instructions-2026-05-0.md).

## Authoring

- When selecting an image in the Editor using the **Select file** dialog, only raster formats (such as JPG, PNG, and GIF) are displayed. Vector files (such as .ai and .eps) stored in DAM are not shown and cannot be selected. (GUIDES-45110)
- XML or DITA tags are turned off by default in the Editor, requiring authors to manually enable them in every session. (GUIDES-44651)
- In the Editor, file references are displayed as GUIDs instead of file paths despite the `xmleditor.uuid` configuration. (GUIDES-42438)
- When multiple subject schemes with similar key values are applied in a DITA topic, they are highlighted with nearly identical colors, making it difficult to distinguish them and identify which scheme is applied. (GUIDES-38472)
- When editing a Subject Scheme map in the Author view, adding the `hasInstance` element automatically triggers the file selection dialog and inserts unwanted `href` and `type` attributes. In addition, the **Content properties** panel fails to load for such maps, preventing authors from defining or updating key values through the UI. (GUIDES-38164)
- When editing a `.ditaval` file, any XML comments added in the Source view are removed when you switch to Author view and then return to Source view. (GUIDES-33228)
- Navtitles containing special characters are not escaped correctly when used in a `topichead` in Author view. (GUIDES-35435)

## Asset management

- Creating a topic in a DAM folder with spaces in its name incorrectly creates a duplicate folder where spaces are replaced by hyphens, and the topic is saved there instead of the original folder. (GUIDES-41938)
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

- Topic references within a map are incorrectly shown as indirect when using a custom DITA-OT, even though they are directly referenced. This issue has been resolved with the new baseline experience. 

## Platform

- When large topics or maps are opened, the Author instance becomes unresponsive, requiring a restart in some cases. (GUIDES-43547)

## Learning 

- After enabling a new language from the **Configure languages** dialog, values from another language are displayed for the selected language in the dropdown list under **Language variables**. (GUIDES-38854)

## Resolved issues available with Editor 2.0

The following issues have been fixed, and no longer occur when using Editor 2.0:

- When two or more columns are deleted from a table, the table structure becomes inconsistent or corrupted. (GUIDES-35438)
- When a column is deleted from a table that contains merged cells, a new blank column is added. (GUIDES-30147)
- When a new row is inserted in an existing table from the breadcrumbs menu, the table structure changes unexpectedly, resulting in missing borders and an extra column. (GUIDES-24372, GUIDES-29194)
- When a section element selected using mouse drag in Author mode is copied and pasted, it is converted into paragraph `(<p>)` elements instead of retaining the section structure. (GUIDES-30023)
- When highlighted text inside elements such as step or uicontrol is edited, the selected text is not replaced correctly and is appended or prepended instead, resulting in validation errors. (GUIDES-24371)
- When a table column width is set using relative values, the remaining columns render incorrectly, resulting in a misaligned table layout. (GUIDES-26109)
- When a copied topic title is pasted with tags disabled, the first paste applies incorrect styling and assigns the type as topic instead of title. (GUIDES-28838)
- When large sections of content are edited, unintended scroll movement causes the Editor view to jump away from the active content. (GUIDES-35436)
- When Backspace is used on elements, the Editor scrolls to the top of the topic regardless of the cursor position. (GUIDES-32520)
- When the left or right arrow key is used to move out of inline tags, the cursor jumps unexpectedly on the first attempt. (GUIDES-26363)
- When switching between Author and Source views in long topics, the cursor position is lost. (GUIDES-21164)
- AEM Spellcheck works only for the default en-US language and does not honor other locales. (GUIDES-14731)
- When large DITA topics are unlocked in the Editor, the same topic reopens in a duplicate tab. Additionally, a tag-limit warning is triggered where `NaN` is displayed instead of the actual tag count. (GUIDES-34008)
- When a read-only document is unlocked in the Editor, the selection controls in the **Content properties** panel remain disabled. Because Acrolinx depends on those fields to become interactive again, Acrolinx checks cannot run.  (GUIDES-29614)
- When switching between Author and Source views in long topics, the cursor position is not retained and the Editor scrolls back to the top of the topic. (GUIDES-18114)
- When creating a new `reltable` without a header row in Author view, the table layout changes after a topic is added to the first cell, causing the next column to collapse and making it difficult to place related topics. (GUIDES-19555)
- When an `xref` link is added to a small table cell in Author mode, the link does not stay contained within the cell and appears across adjacent cells in the same row. (GUIDES-5489)

## Known issues

Adobe has identified the following known issues for the 2026.05.0 release:

- When a map contains an external `topicref` pointing to a non-DITA resource (such as `.html` or `.htm`), its preview is not displayed  in the Assets UI. (GUIDES-45409)
- In the Assets UI, the content referenced through `conref` is not displayed for some topics, even though the preview appears correctly in the Editor. (GUIDES-45505)
- When `xmleditor.uniquefilenames` property is enabled, new topics created using a template do not include the topic title. (GUIDES-44737)

