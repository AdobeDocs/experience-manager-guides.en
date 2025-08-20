---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 5.1.0 release
description: Learn about the bug fixes in the 5.1.0 release of Adobe Experience Manager Guides.
exl-id: dcc97f9b-f1c0-45bc-84eb-8c0c1a857b6a
---
# Fixed issues in the 5.1.0 release (September 2025)

This article covers the bugs fixed in various areas of 5.1.0 release of Adobe Experience Manager Guides.


For more information about the new features and enhancements, view [What's new in the 5.1.0 release](whats-new-5-1-0.md).

Learn about [upgrade instructions for the 5.1.0 release](upgrade-instructions-5-1-0.md).


## Authoring

- **CSS** and **Page layout** files in Native PDF templates exhibit inconsistent file locking behavior, allowing edits even when the files are locked. (GUIDES-26688)
- Refreshing the page after adding custom buttons to the left panel creates duplicate tabs. (GUIDES-30899)
- When XML content containing angular brackets (such as </ or />) is added within a `code block` element in a topic, the code block element appears blank in the final output. (GUIDES-31007)
- The values of global variables `canCheckIn` and `canCheckOut` are not being set correctly when a file is checked out and checked in from the Editor toolbar.(GUIDES-29890)
- When opening a DITA map with the unified shell enabled, the Editor refreshes intermittently.(GUIDES-26919)
- When a DITA map is selected in Map view, the selection count is displayed incorrectly at first because the child nodes of the map are not selected. The correct selection count and inclusion of all child nodes are only reflected upon subsequent selection. (GUIDES-25663)
- Markdown files are not retrieved when searched in the Repository panel using the **DITA topic** filter. Also, the **Find and Replace** do not work for Markdown files and related content. (GUIDES-27133)
- Unable to customize the **Menu dropdown** of Editor toolbar using the extension framework. As a result, you can not hide or show any existing buttons or add new buttons in the Menu dropdown. (GUIDES-28748) 
- When an XML comment is added within an element in the Source view, the leading and trailing spaces around the comment are lost upon switching views. (GUIDES-29781)
- Multimedia options do not work when present inside the ellipsis icon (the **More** menu) in the toolbar. (GUIDES-29583)
- When creating a new topic through the Assets UI or Editor, the topic does not automatically open in the Editor if the `xmleditor.uniquefilenames` setting is set to true in `XMLEditorConfig`. (GUIDES-28171)
- Spaces added within a MathML equation in the Source view are not retained upon switching the Editor views. (GUIDES-26111)
- Failing to close JCR session connections while updating or creating topics result in memory leaks and service downtime. (GUIDES-26282)
- Dragging the columns changes their width from percentage to pixel values, which results in distorted or misaligned tables.(GUIDES-23128)
- When content is pasted into a `code block` or when spaces are added in the `code block` and the view is switched, the spacing is lost. (GUIDES-27478)
- When adding a map to the `bookmap`, it gets stored in `fmditatopicrefs` instead of `fmditamaprefs`. (GUIDES-25480)
- The **Insert image** dialog fails to render correctly on a high-resolution or zoomed-out screens causing the figure title and alternate text fields to disappear. (GUIDES-26459)
- Special character insertion box in the Editor fails to load for German locale. (GUIDES-24537) 
- Comments and labels added while saving a new version of a DITAVAL file are not getting saved in the Version History with the new version. (GUIDES-24076)
- The outgoing and incoming references under **File properties** in the right panel do not refresh properly when switching between map files. This issue occurs specifically when the map files contain a large number of references. (GUIDES-23344)
- The Repository filter does not retain the order of custom filters defined in the `ui_config.json`. (GUIDES-21193)
- Deleting multiple lines of text in a `codeblock` element creates an empty space which can not be removed from Author view. (GUIDES-20672)
- New ids fail to generate for elements when such elements are added via snippets or created via templates, even when the **auto generate ID** option is enabled in `XMLEditorConfig`. (GUIDES-21734)
- Creating a new DITA asset from DITA templates copies the replication properties from corresponding DITA templates. (GUIDES-25145) 
- Unable to access file properties from the repository panel if the parent folder name includes "&" character. (GUIDES-25762)
- Closing a topic file allows it to be saved as a new version, even when the topic is locked. This issue occurs specifically when the **Ask for new version on close** option is enabled in `XMLEditorConfig`. (GUIDES-23875)
- The current maximum width of the repository panel hides topic and map titles when the content hierarchy is deeply nested. (GUIDES-27751)

## Asset management

- Copying a folder with a large number of assets from the Assets UI leads to an API timeout. The operation continues to run in the backend and completes after some time, but no success or failure message, or notification is shown in the UI. (GUIDES-30900)
- Copy-paste operation performed on a folder in the Assets UI fails due to post-processing errors. (GUIDES-30840)
- Copy-paste operation fails for folders containing compound assets (assets with subassets)in the Assets UI. (GUIDES-28107)
- Folders with a large number of assets fail to load properly in the Respository. (GUIDES-32500)
- Folder node names are incorrectly displayed in place of folder titles in the Editor. (GUIDES-32402)
- Error occurs on uploading assets with unsupported or forbidden characters in the filenames. (GUIDES-28845)
- When opening a topic in Author view after a browser refresh, previously applied tags in the File Properties panel are not retained, and adding new tags overwrites the existing ones, particularly when a large number of tags are available for selection. (GUIDES-29078)
- When generating a Metadata report for a DITA map containing a large number of assets, the **Manage** button becomes unresponsive or exhibits a delayed response. (GUIDES-28443)

## Review

- Attempts to create review tasks through the AEM workflow consistently fail because the review node is not created. (GUIDES-28214)
- The document view in the Review UI does not wrap the content for some screen sizes, requiring users to scroll horizontally to view the full content. (GUIDES-25292)
- Updating the details of a review task in the Review dashboard does not confirm whether the update was successful or unsuccessful. (GUIDES-8051) 

## Translation

- Translations submitted through Experience Manager Guides do not include the attached assets, causing the **Start** button for translation job to become unavailable to users. (GUIDES-28237)

## Publishing

- In the Native PDF output, the List of Index (LOI) appears in a non-alphabetical order and nested index terms are not grouped properly, making the index difficult to navigate. (GUIDES-29090)
- The **Map page template** and **Topic page template** dropdown list in the AEM Sites component mapping output preset page appears blank when the destination path contains a variable with a colon. (GUIDES-28119)
- When a DITA map contains different types of topic references such as Concept, Reference or Task, and it is merged using the `chunk=to-content` attribute to generate single page output on AEM Sites with component mapping, the content does not get published properly due to publishing errors. (GUIDES-28118)
- Code quality error occurs when deploying the AEM Sites publishing components package `guides-components.all-1.3.0.zip` through Cloud Manager. (GUIDES-28873)
- Publishing a DITA map with `chunk=to-content` attribute creates duplicate JCR nodes in the new AEM Sites output, leading to redundant content structure in AEM Sites. (GUIDES-28104)
- When publishing a DITA map using the new AEM Sites output, if a topic has the `chunk =to-content` attribute and the output is set to use topic titles as page names, the generated page name incorrectly displays the word **chunk** instead of retaining the original topic name. (GUIDES-28102)
- The `cq:template` property set in the AEM Guides topic template for new AEM Sites publishing displays an incorrect value, affecting template structure and content rendering. (GUIDES-27789)
- Native PDF publishing continues indefinitely, if the DITA content has a weblink without having scope as `external`. (GUIDES-26434) 
- Publishing of Native PDFs and AEM sites stalls and gets queued, when there are errors in the content. (GUIDES-26516)
- When creating a new baseline with a large number of labels, it prevents all the labels from being fetched. (GUIDES-16232)
- When generating AEM Site pages with titles that include multiple words separated by spaces, the map title displays hyphens instead of spaces. (GUIDES-27903)
- For Native PDF, an invalid metadata property name is not getting resolved and is displayed as `unresolved property name` in **document properties**. (GUIDES-25680)
- Multi-line text within `codeblock` causes text overflow issues during PDF generation. (GUIDES-15541)
- When adding maps to the map collection, assets other than maps (likes topics etc.) are displayed, and the translated map languages are also not properly sorted.(GUIDES-25085)
- In the legacy AEM Sites output, section links within nested topics of a map do not resolve correctly when manually set in Source mode or the content is imported from an external source. Instead of navigating to the intended section, they redirect to the main topic that contains the nested topic. (GUIDES-26103)
- If the `scope=external` attribute is missing from external links in a DITA topic, HTML5 publishing fails without indicating the files where this attribute is missing in the error logs, especially when the microservice is enabled. (GUIDES-25969) 
- Unable to embed video links in Native PDF even when the **Embed Multimedia Files** option is enabled in the PDF preset. (GUIDES-9989)
- Unable to pass the metadata properties to map landing pages generated using new AEM Sites publishing. (GUIDES-27288) 

## Baseline

- Copying a DITA map from the Assets UI also copies its attached Baseline to the new map. (GUIDES-11227)

## Home page 

- The Home page goes blank when one of the files listed in the **Recent files** widget is based on a template whose source template does not include a thumbnail. (GUIDES-31506)

## Management 

- Document state from the working copy of a topic is displayed against all the versions of that topic in the Translation and Baseline UI. (GUIDES-20674) 

## Platform

- Performance issues like longer loading times and intermittent timeouts are observed when working with large collections. (GUIDES-29065, GUIDES-28793)
- Vulnerabilities associated with the deprecated Guava library being used in the AEM Guides components uploaded on Experience Manager Guides.(GUIDES-27402)

