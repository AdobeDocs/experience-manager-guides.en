---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2025.08.0 release
description: Learn about the bug fixes in the 2025.08.0 release of Adobe Experience Manager Guides as a Cloud Service.

---
# Fixed issues in the 2025.08.0 release 

This article covers the bugs fixed in various areas of the 2025.08.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2025.08.0 release](whats-new-2025-08-0.md).

Learn about [upgrade instructions for the 2025.08.0 release](upgrade-instructions-2025-08-0.md).

## Authoring

- **CSS** and **Page layout** files in Native PDF templates exhibit inconsistent file locking behavior, allowing edits even when the files are locked. (GUIDES-26688)
- Refreshing the page after adding custom buttons to the left panel creates duplicate tabs. (GUIDES-30899)
- When XML content containing angular brackets (such as </ or />) is added within a `code block` element in a topic, the code block element appears blank in the final output. (GUIDES-31007)
- The values of global variables `canCheckIn` and `canCheckOut` are not being set correctly when a file is checked out and checked in from the Editor toolbar.(GUIDES-29890)
- When opening a DITA map with the unified shell enabled, the Editor refreshes intermittently.(GUIDES-26919)
- When a DITA map is selected in Map view, the selection count is displayed incorrectly at first because the child nodes of the map are not selected. The correct selection count and inclusion of all child nodes are only reflected upon subsequent selection. (GUIDES-25663)
- Markdown files are not retrieved when searched in the Repository panel using the **DITA topic** filter. Also, the **Find and Replace** do not work for Markdown files and related content. (GUIDES-27133)
- Unable to customize the **Show**, **Hide**, and **Add New** options present in the **Menu** dropdown of the Editor toolbar using extension framework. (GUIDES-28748) 

## Asset management

- Copying a folder with a large number of assets from the Assets UI leads to an API timeout. The operation continues to run in the backend and completes after some time, but no success or failure message, or notification is shown in the UI. (GUIDES-30900)
- Copy-paste operation performed on a folder in the Assets UI fails due to post-processing errors. (GUIDES-30840)
- Copy-paste operation fails for folders containing compound assets (assets with subassets)in the Assets UI. (28107)
- Folders with a large number of assets fail to load properly in the Respository. (GUIDES-32500)
- Folder node names are incorrectly displayed in place of folder titles in the Editor. (GUIDES-32402)
- Error occurs on uploading assets with unsupported or forbidden characters in the filenames. (GUIDES-28845)

## Publishing

- In the Native PDF output, the List of Index (LOI) appears in a non-alphabetical order and nested index terms are not grouped properly, making the index difficult to navigate. (GUIDES-29090)
- The **Map page template** and **Topic page template** dropdown list in the AEM Sites component mapping output preset page appears blank when the destination path contains a variable with a colon. (GUIDES-28119)
- When a DITA map contains different types of topic references such as Concept, Reference or Task, and it is merged using the `chunk=to-content` attribute to generate single page output on AEM Sites with component mapping, the content does not get published properly due to publishing errors. (GUIDES-28118)

## Baseline

- Copying a DITA map from the Assets UI also copies its attached Baseline to the new map. (GUIDES-11227)

## Home page 

- The Home page goes blank when one of the files listed in the **Recent files** widget is based on a template whose source template does not include a thumbnail. (GUIDES-31506)


 