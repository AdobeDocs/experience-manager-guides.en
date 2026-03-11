---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2026.03.0 release
description: Learn about the bug fixes in the 2026.03.0 release of Adobe Experience Manager Guides as a Cloud Service.
---
# Fixed issues in the 2026.03.0 release 

This article covers the bugs fixed in various areas of the 2026.03.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2026.03.0 release](whats-new-2026-03-0.md).

Learn about [upgrade instructions for the 2026.03.0 release](upgrade-instructions-2026-03-0.md).

## Authoring

- When editing a Schematron (`*.sch`) file and using the Find and replace feature,  the Find and replace panel appears partially off-screen at the bottom, preventing access to its input fields and controls. (GUIDES-38412)

## Publishing

- When the same topic is reused across multiple maps with different conditional presets, publishing the latest map to Salesforce overwrites the topic content, resulting in incorrect data being displayed to users of previously published maps. (GUIDES-37806)
- When publishing a Native PDF for a map that includes conditional processing or certain nested maps, the `dc:title` defined in the map fails to appear on the PDF cover, resulting in a missing cover title. (GUIDES-37733)
- Generating AEM site output (using composite component mapping) for a map fails and results in an error when the `map_title` variable is present in the output path. (GUIDES-36968)
- When an output path with a trailing slash is specified in the Native PDF output preset, the UI automatically appends an additional trailing slash, resulting in a double‑slash path that causes the PDF upload to fail in certain scenarios. (GUIDES-34932)
- Publishing AEM Sites pages generated from DITA content through Quick Publish or Manage Publication unintentionally publishes the associated DITA assets. (GUIDES-27967)
- When publishing a map to AEM Sites (using legacy component mapping), cross-references (`xrefs`) with `scope = peer` that target sub-elements of a topic (such as paragraphs) in a different map do not resolve to the specific element ID and instead resolve only to the parent topic, causing the page to load at the start of the topic rather than scrolling to the intended section. (GUIDES-21802)


## Translation

- When an image initially managed as a language‑specific asset with a specific version (for example, under `/en/`) is moved out to a global folder with an updated version and baseline export is performed, the new baseline continues to reference outdated language‑specific versions of that image, leading to a failed baseline export. (GUIDES-39394)
- When processing translation projects created outside Experience Manager Guides, multiple error log messages are generated stating that *`fmTarget` property not found*. (GUIDES-37804)

## Baseline 

- When creating a dynamic baseline, the Editor sometimes becomes unresponsive due to multiple concurrent API requests, causing all the other operations to halt. (GUIDES-39054)

## Review

- When assigning a user to a review task, the dropdown lists all users instead of only those associated with the selected projects, resulting in invalid user options. (GUIDES-37781)

## Reports

- While opening a Report for a map, there is a delay in the loading of the Filters panel (GUIDES-39385)

## Known issues

Adobe has identified the following known issues for the 2026.03.0 release:

- A blank screen is loaded when creating a duplicate Knowledge Base preset for ServiceNow. (GUIDES-42732)
- The API for retrieving document state returns a null response for some files. (GUIDES-42561)
- Renaming an existing template does not update the name in the **Output templates** panel until the page is manually refreshed. (GUIDES-42528)
- An extra space added to the tab names present in the Map Dashboard causes automation failures. (GUIDES-42285)
- When a file is open in both the Editor and the Search panel, deleting it from the Explorer panel removes the file and refreshes the Explorer list, but refreshing the page continues to display the file in the Search panel. (GUIDES-41935)
- While updating an active review task, if a topic that is already part of the review is removed and then re‑added without clicking **Update**, the reviewer(s) information in the Reviewers tab is lost.   (GUIDES-38774)
- In the Assets UI, the **Move** button does not get enabled on the first attempt when more than 2 files or folders are selected. (GUIDES-42721) <br> **Workaround**:  After selecting more than two files or folders, wait for a few seconds before selecting the destination folder. 
- Selecting a topic in the Preview mode does not highlight it in the Map view if the topic is inside bookmap tags (frontmatter, chapter, part, or backmatter) or part of cyclic content. (GUIDES-42416)
- When you navigate to **User preferences** from the Editor and update the root map while Preview mode is open in the Editor, the map preview loads as a blank screen when you return to the Editor. (GUIDES-42412) <br> **Workaround**: Refreshing the preview using the **Refresh** icon available in the Preview mode resolves the issue. 










