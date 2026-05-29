---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 5.2.0 release
description: Learn about the bug fixes in the 5.2.0 release of Adobe Experience Manager Guides.

---
# Fixed issues in the 5.2.0 release (May 2026)

This article covers the bugs fixed in various areas of 5.2.0 release of Adobe Experience Manager Guides.

For more information about the new features and enhancements, view [What's new in the 5.2.0 release](whats-new-5-2-0.md).

Learn about [upgrade instructions for the 5.2.0 release](upgrade-instructions-5-2-0.md).


## Authoring

- If an empty `prop` element with no attributes or values is added to a DITAVAL file, then additional `prop` elements cannot be added. (GUIDES-33597)
- After upgrading Experience Manager Guides to 2025.08.0 version, the option to enable or disable the custom **Acrolinx** tab no longer appears in **Workspace settings**. (GUIDES-35261)
- Custom CSS applied at a folder-level profile for topics or maps is reverted to the default style in Preview mode upon browser refresh. (GUIDES-31098)
- **Undo** and **Redo** operations do not work as expected in the Source view of the Editor for DITA files. (GUIDES-24914, GUIDES-25034) 
- When referencing a DITA map in a topic using the `Xref` element, the file name of the referenced map is displayed instead of the title of the map. (GUIDES-21759)
- When adding multiple Schematron files for validation through the right panel of the Editor interface, an error **Schematron file(s) don't exist or have errors** is displayed even if the files added are valid and have no errors. (GUIDES-33731)
- Large or complex MathML equations fail to display in the Editor. (GUIDES-29095)
- When multiple DITA maps or topics are open and one of the topics is closed, the **>>** button which showcases all the open tabs gets overlapped with the remaining open tabs on the Tab bar. (GUIDES-31421)
- With the **Approval workflow** enabled, the **Start a New Release** button is not visible on the Editor toolbar if both the Left panel and the Content properties panel are open. (GUIDES-29093)
- When snippet names exceed the width of the snippet panel, they wrap incorrectly onto the next line, resulting in overlap with adjacent snippets and impacting readability. (GUIDES-22685)
- When you add the same reference multiple times to a DITA map, the **Map** view displays the title only for the last occurrence, while the previous ones show the UUID of the reference. (GUIDES-9699)
- The DITAVAL files remain editable,  even when they are locked by another user or when the server has **Disable edit without locking the file** enabled and the file is opened in read-only mode. (GUIDES-27754)
- Logs for missing nodes are being generated from internal cleanup jobs that are not required and are incorrectly marked as errors, resulting in cluttered log files. (GUIDES-31765)
- When editing a Schematron (`*.sch`) file and using the Find and replace feature,  the Find and replace panel appears partially off-screen at the bottom, preventing access to its input fields and controls. (GUIDES-38412)
- Unable to add multiple **Version labels** to a topic from the **Save as new version** dialog. (GUIDES-32716)
- When selecting an image in the Editor using the **Select file** dialog, only raster formats (such as JPG, PNG, and GIF) are displayed. Vector files (such as .ai and .eps) are not shown and cannot be selected. (GUIDES-45110)
- At the time of upgrade, the `tagsView` setting is turned off by default, even though its default value in `ui_config.json` is set to `true`. (GUIDES-44651)
- In the Editor, file references are displayed as GUIDs instead of file paths despite the `xmleditor.uuid` configuration. (GUIDES-42438)
- When Subject schemes with similar key values are applied in a DITA topic, they are highlighted with nearly identical colors, making it difficult to distinguish them and identify which scheme is applied. (GUIDES-38472)
- When editing a Subject Scheme map in the Author view, adding the `hasInstance` element automatically triggers the file selection dialog, requiring authors to insert an unwanted `href` pointing to an AEM asset. In addition, the **Content properties** panel fails to load for such maps, which prevents authors from updating element attributes in Author view and requires them to use Source view for updating attributes. (GUIDES-38164)
- When editing a `.ditaval` file, any XML comments added in the Source view are removed when you switch to Author view and then return to Source view. (GUIDES-33228)
- When updating an inline MathML equation using the Edit MathML option from the context menu, the updated value is not reflected until the page is refreshed. (GUIDES-38198)
- When a topic contains many reusable elements (those with IDs) added in the Reusable panel, some elements may not be accessible because of fixed container height. (GUIDES-37220)
- When inserting a cross-reference to a file, the icons for maps and topics are identical. (GUIDES-36662)
- When editing a map, special symbols in the `navtitle` are not displayed for `topichead` in the Author view. (GUIDES-35435)

## Asset management

- When you re-upload an edited image through the Experience Manager Guides UI, the image's original rendition gets updated but the associated DITA content continues to display the previous version of the image. (GUIDES-33693)
- When attempting to move two or more folders from their source location to a different location (using the Bulk Move Tool), the operation fails if the folder names start with the same string (e.g., Product and ProductImages). (GUIDES-29096)
- Deleting a searched asset from the Omnisearch Assets UI bypasses the **Force delete** warning dialog and deletes the asset directly, even when it's referenced in existing DITA content. (GUIDES-17232)
- Unable to remove Version labels from **Version history** panel in Assets UI. (GUIDES-38276)
- Creating a topic in a folder with spaces in its name incorrectly creates a duplicate folder where spaces are replaced by hyphens, and the topic is saved there instead of the original folder. (GUIDES-41938)
- During first-time translation of large maps, empty XML files are created for the destination language, leading to increased server load and slower performance. (GUIDES-41613)
- In the Assets search, sub-assets and metadata nodes (such as images and PDFs) are incorrectly included in the results. Additionally, for an output preset when DITAVAL filters are applied, the search returns internally generated DITAVAL files created from condition presets. (GUIDES-35418)
- When uploading assets with filename containing invalid characters, the asset fails to upload and displays an incorrect message **File is locked by other user** despite the asset being unlocked. (GUIDES-32680)

## Publishing

- When publishing a DITA map using baseline on AEM Sites (with legacy component mapping), the map elements with the attribute `processing-role = resource-only` are also getting published. (GUIDES-37649)
- In some cases, the `jcr:content/fmUuidOfSource` property is found missing in the AEM Sites output pages (with legacy component mapping), leading to newly created content pages not discoverable. (GUIDES-34242)
- Content filtering via DITAVal filters and conditional presets do not work for Salesforce publishing. (GUIDES-33515)
- Unable to create a Native PDF preset for a map if a folder with the same name exists in its content hierarchy. (GUIDES-33012)
- When Native PDF output is generated using a dynamic baseline, the term **PDFProject** is displayed as the PDF title instead of the actual map title. (GUIDES-31102)
- Generating Native PDF output with certain `print` attribute values in topic references do not work as expected. (GUIDES-31101)
- When a folder containing DITA maps is moved using the Assets UI or **Bulk move** option, existing map collections and bulk activation collections that reference those maps fail to load. (GUIDES-28355)
- When you move a folder containing a map with condition presets, the conditions are not applied in the generated output after the move. (GUIDES-28352)
- When you generate AEM Sites output using legacy component mapping, topics that use the `copy-to` attribute get published with the `copy-from` topic's name instead of the name set in the `copy-to` attribute. (GUIDES-22155)
- Activating one or more DITA maps from **Bulk publish dashboard** generates excessively large logs. (GUIDES-20746)
- When generating PDFs, the filtering rules in a DITAVAL file are ignored if any property name contains a period. (GUIDES-33229)
- Salesforce publishing displays a successful status on the UI even when a DITA map containing a `topichead` element fails to publish the topics within it. (GUIDES-32143)
- For HTML5 output preset, the search filter functionality is not working in AEM Assets for DITAVAL filtering, as the corresponding files are not being displayed when the DITAVAL filter is selected. (GUIDES-28231)
- When generating a Native PDF for a DITA map with multiple topics, if any topic contains a `fig` element within a `figgroup` along with a `title`, the `figgroup` title is incorrectly rendered as a chapter title in the Table of Contents. (GUIDES-23223)
- When duplicating PDF templates from the UI, the UUID is also duplicated, causing template files to be deleted and resulting in incorrect PDF outputs. (GUIDES-30456)
- When generating Native PDF for a DITA map, the title of `example` element is rendering as `h1` heading level, thereby leading to visual inconsistency and improper TOC structure. (GUIDES-19958)
- When the same topic is reused across multiple maps with different conditional presets, publishing the latest map to Salesforce overwrites the topic content, resulting in incorrect data being displayed to users of previously published maps. (GUIDES-37806)
- When publishing a Native PDF for a map that includes conditional processing or certain nested maps, the `dc:title` defined in the map fails to appear on the PDF cover, resulting in a missing cover title. (GUIDES-37733)
- Generating AEM site output (using composite component mapping) for a map fails and results in an error when the `map_title` variable is present in the output path. (GUIDES-36968)
- When an output path with a trailing slash is specified in the Native PDF output preset, the UI automatically appends an additional trailing slash, resulting in a double-slash path that causes the PDF upload to fail in certain scenarios. (GUIDES-34932)
- Publishing AEM Sites pages generated from DITA content through Quick Publish or Manage Publication unintentionally publishes the associated DITA assets. (GUIDES-27967)
- When publishing a map to AEM Sites (using legacy component mapping), cross-references (`xrefs`) with `scope = peer` that target sub-elements of a topic (such as paragraphs) in a different map do not resolve to the specific element ID and instead resolve only to the parent topic, causing the page to load at the start of the topic rather than scrolling to the intended section. (GUIDES-21802)
- When publishing a DITA map using baseline on AEM Sites (with legacy component mapping), the map elements with the attribute `processing-role = resource-only` are also getting published. (GUIDES-34298)
- When changes to an output preset in a Folder profile are applied to existing maps, the saved **Publish Context** for the AEM Sites preset is reset. (GUIDES-38377)
- The trademark symbol (&reg;) does not render on the cover page of the Native PDF output when the `tm` element is used within the title of a map or bookmap. (GUIDES-28832)
- When publishing a map using a Native PDF template, the **Map title** does not include content from the child elements used within the map `title`, and the corresponding content filtering is not applied to the title.(GUIDES-33730)
- Cross-map peer links in AEM Sites output fail to resolve when they point to a `topicref` that uses `chunk="to-content"`. (GUIDES-37873)
- During publishing, files associated with DITAVAL-based flagging are moved to a new system-generated folder instead of remaining in their expected relative location in the output. (GUIDES-37564)
- When multiple DITAVAL files with conflicting conditions are used, the Native PDF output fails. (GUIDES-37484)
- When creating or editing a topic that includes a citation, if the Author field is not added in the citation dialog, the PDF is not generated. (GUIDES-37934)
- When generating AEM Sites output, the map titles containing keywords and topic titles with `<ph>` element are not getting included in the published output. (GUIDES-36641)
- The CSS file (`rhdefault.css`) gets incorrectly applied to the PDF template despite no CSS being referenced, causing missing CSS file error logs.(GUIDES-31752)
- When downloading temporary files for a map with a baseline during publishing for a preset, the `metadata.xml` file incorrectly references the `versionPath` instead of the `dampath`.(GUIDES-29815)
- For Native PDF output, the `<alt>` element for images is ignored, preventing alternate text from being applied for accessibility. (GUIDES-29087)
- In Native PDF output, the `abbreviated-form` element displays the `glossterm` instead of the designated `glossSurfaceForm` or `glossAcronym`. (GUIDES-26393)
- When performing bulk activation, the package creation adds filters for all paths listed under the `fileReference` property of a page, including external and peer paths. (GUIDES-24887)
- When publishing using a custom preset with content that contains links to PDFs without the scope set as external, the process fails to complete. (GUIDES-21708)
- Salesforce publishing fails with an application error, when a topic with the same name and URL already exists. (GUIDES-32390)
- Auto-hyphenation is not being applied in Native PDF output, even when the **Use automatic hyphenation** setting is enabled for the output preset. (GUIDES-19703)

## Translation

- When zooming in the screen of Translation UI, the **Send for Translation** button moves under the ellipsis and becomes enabled even without any asset being selected. (GUIDES-33720)
- When selecting files with **Out of Sync** status on the Translation UI, and the screen width is constrained due to open Left and Right panels, the **Send for translation** label gets truncated. (GUIDES-33692)
- When an image initially managed as a language‑specific asset with a specific version (for example, under `/en/`) is moved out to a global folder with an updated version and baseline export is performed, the new baseline continues to reference outdated language‑specific versions of that image, leading to a failed baseline export. (GUIDES-39394)
- When processing translation projects created outside Experience Manager Guides, multiple error log messages are generated stating that *`fmTarget` property not found*. (GUIDES-37804)

## Baseline 

- When creating a dynamic baseline, the Editor sometimes becomes unresponsive due to multiple concurrent API requests, causing all the other operations to halt. (GUIDES-39054)
- Topic references within a map are incorrectly shown as indirect when using a custom DITA-OT, even though they are directly referenced. This issue has been resolved with the new baseline experience. (GUIDES-19286)
- References with `scope="peer"` are incorrectly included in the baseline context, causing publishing to take longer than expected. This issue has been resolved with the new baseline experience. (GUIDES-41823)


## Review

- When assigning a user to a review task, the dropdown lists all users instead of only those associated with the selected projects, resulting in invalid user options. (GUIDES-37781)
- When a reviewer completes a review task or initiator updates review task without entering comments, the notification email sent displays the most recent previous comment. (GUIDES-33590)

## Reports

- While opening a Report for a map, there is a delay in the loading of the Filters panel (GUIDES-39385)
- The Broken list report is incorrectly including external links, valid `keyrefs` and keywords that are properly resolved within scope of current map. (GUIDES-27774)

## Platform

- Error logs that are generated while uploading an asset via the Assets UI or creating a new file from the Editor interface, incorrectly use the term `predecessor` instead of `successor` in the log message. (GUIDES-35607)
- Using `scope="external"` for a reference to DAM content within a topic or map causes the asset's relative path to be substituted with a GUID. (GUIDES-38783)
- When a topic contains a large number of references linked from folders with many files, the Author instance may become slow or unresponsive, in some cases requiring a restart of the instance. (GUIDES-43547)
- When attempting to save a topic or map, the operation may intermittently fail with a **Failed to save file** error, particularly during intensive asset processing tasks or translation workflows running in the background. (GUIDES-37837)


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

### Authoring

- When uploading flagged images in DITAVAL files, the images break after a browser refresh when the `Enable UUIDs` setting is disabled. (GUIDES-45853)
- In the Editor, `.ditval` and `.md` files files become non-editable when *Approval Workflow* is enabled. (GUIDES-42037)
- Selecting a topic in the Preview mode does not highlight it in the Map view if the topic is inside bookmap tags (frontmatter, chapter, part, or baatter) or part of cyclic content. (GUIDES-42416)
- When a file is open in both the Editor and the Search panel, deleting it from the Explorer panel removes the file and refreshes the Explorer list, but refreshing the page continues to display the file in the Search panel. (GUIDES-41935)

### Asset management

- In the Assets UI, the **Move** button does not get enabled on the first attempt when more than 2 files or folders are selected. (GUIDES-42721) <br> **Workaround**:  After selecting more than two files or folders, wait for a few seconds before selecting the destination folder. 

### Review

- While updating an active review task, if a topic that is already part of the review is removed and then re‑added without clicking Update, the reviewer(s) information in the Reviewers tab is lost. (GUIDES-38774)
- When an in-review topic is removed from an ongoing review task, its document state continues to remain **In Review**, even though the topic is no longer part of any review task. (GUIDES-38709)<br>**Workaround**: Change the document state of the topic from **In Review** to the appropriate state from the Properties page or File properties panel.

### Editor 2.0 

- Copy-pasting content in the same topic into an invalid location in the Editor inserts an unintended foreign tag. (GUIDES-45378)
- Copying and pasting `<keywords>` inside `<topicmeta>` within `<keydef>` or `<topicref>` inserts unintended foreign tags. (GUIDES-45800)
- When content is copied from a map or topic using the Copy option in the context menu and then pasted, unexpected extra `<data>` tags are inserted into the pasted content. (GUIDES-45703)
- On Windows, copying and pasting a table row adds unwanted attributes to the table, resulting in markup errors and preventing the document from being saved. (GUIDES-45784)
- Drag selection around a table or simpletable does not work as expected. (GUIDES-45406)
- Pasting images from external sources does not insert them into the topic. (GUIDES-45983)
- MathML content referenced through `conref` does not render correctly. (GUIDES-46601)
- Incomplete attribute rendering for MathML and SVG elements breaks custom CSS classes and condition attribute handling. (GUIDES-46371)
- MathML equations wrapped inside `foreign` and `equation-block` tags introduce unwanted spaces and disrupt editing behavior. (GUIDES-46606)
- Dragging and dropping an element that contains a key reference converts the `keyref` into an absolute path. (GUIDES-45701)
- In the Map editor, `Ctrl+click` on a broken link triggers an application error. (GUIDES-45544)
