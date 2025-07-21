---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2025.08.0 release
description: Learn about the bug fixes in the 2025.08.0 release of Adobe Experience Manager Guides as a Cloud Service.
exl-id: 0744e821-5aee-432b-a6c8-7ed6538935db
---
# Fixed issues in the 2025.08.0 release 

This article covers the bugs fixed in various areas of the 2025.08.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2025.08.0 release](whats-new-2025-08-0.md).

Learn about [upgrade instructions for the 2025.08.0 release](upgrade-instructions-2025-08-0.md).

## Authoring

- **CSS** and **Page layout** files in Native PDF templates exhibit inconsistent file locking behavior, allowing edits even when the files are locked. (26688)
- Refreshing the page after adding custom buttons to the left panel creates duplicate tabs. (30899)

## Asset management

- Copying a folder with a large number of assets from the Assets UI leads to an API timeout. The operation continues to run in the backend and completes after some time, but no success or failure message, or notification is shown in the UI. (GUIDES-30900)
- Copy-paste operation performed on a folder in the Assets UI fails due to post-processing errors. (GUIDES-30840)
- Copy-paste operation fails for folders containing compound assets (assets with subassets)in the Assets UI. (28107)

## Review

- Attempts to create review tasks through the AEM workflow consistently fail because the review node is not created. (GUIDES-28214)

## Publishing

- In the Native PDF output, the List of Index (LOI) appears in a non-alphabetical order order and nested index terms are not grouped properly, making the index difficult to navigate. (29090)

Code quality error occurs when deploying the AEM Sites publishing components package `guides-components.all-1.3.0.zip` through Cloud Manager. (GUIDES-28873)
- Publishing a DITA map with `chunk=to-content` attribute creates duplicate JCR nodes in the new AEM Sites output, leading to redundant content structure in AEM Sites. (GUIDES-28104)
- When publishing a DITA map using the new AEM Sites output, if a topic has the `chunk =to-content` attribute and the output is set to use topic titles as page names, the generated page name incorrectly displays the word **chunk** instead of retaining the original topic name. (GUIDES-28102)
- The `cq:template` property set in the AEM Guides topic template for new AEM Sites publishing displays an incorrect value, affecting template structure and content rendering. (GUIDES-27789)


## Platform

- Performance issues like longer loading times and intermittent timeouts are observed when working with large collections. (GUIDES-29065, GUIDES-28793)
- Vulnerabilities associated with the deprecated Guava library being used in the AEM Guides components uploaded on Experience Manager Guides.(GUIDES-27402)

## Known issues

Adobe has identified the following known issues for the 2025.07.0 release:

- When working with Markdown topics, a **Topic reference** button appears in the Editor toolbar, but it does not function. (GUIDES-31038)
- When folders with uppercase names are uploaded using Adobe Experience Manager desktop app, the casing is not retained and the names appear in lowercase in the Editor. (GUIDES-30909)
- In the **Merge** dialog, the dropdown list incorrectly displays **Main content** instead of showing the available versions of the selected topic. (GUIDES-30820)
- When opening a DITA map with the unified shell enabled, the editor refreshes intermittently.(GUIDES-26919)
