---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2026.11.0 release
description: Learn about the bug fixes in the 2026.11.0 release of Adobe Experience Manager Guides as a Cloud Service.

---

# Fixed issues in the 2026.11.0 release

This article covers the bugs fixed in various areas of the 2026.11.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2026.11.0 release](./whats-new-2026-11-0.md).

Learn about [upgrade instructions for the 2026.11.0 release](./upgrade-instructions-2026-11-0.md).

## Editor 2.0

- When a table row is selected using the breadcrumbs in the Editor and the **Delete** option is selected from the context menu, only the cell contents are removed instead of deleting the entire row. (GUIDES-56759)
- When a table is pasted from Microsoft Word, the header row cells are created but their content is lost. (GUIDES-49847)
- Tracked changes in files created before moving to Editor 2.0 do not appear in the **Track changes** panel. (GUIDES-44777)
- When code is pasted into a `codeblock` element, from Microsoft Word or similar text editors, by using Ctrl+V, line breaks and leading spaces are lost and the code is flattened into a single line. (GUIDES-33247)

## Authoring

- When the unified shell is enabled, the Adobe Experience Manager Guides header also appears in the Editor and the Map console. (GUIDES-56812)
- In the Assets UI, DITA-specific actions such as **View source**, **Edit topics** and **Share UUID Link** appear for non-DITA assets. In addition, **Share UUID Link** generates an invalid link for assets that do not have a UUID. (GUIDES-47043)
- In the Subject scheme panel, the display title is picked only from the `navtitle` attribute. The `navtitle` element is ignored even when both are present. (GUIDES-37722)
- In the **Title view** of the Repository panel, the ellipsis is not initially visible for files with long names. Upon right-clicking such a file, the ellipsis and the context menu appear far to the right of the file, sometimes partly off-screen. (GUIDES-37118)
- In the Conditions panel, conditions are sorted alphabetically based on their values rather than their labels. (GUIDES-14593)
- In Output templates, the **New Style** (+) button is not displayed in the Styles panel when a stylesheet, such as layout.css, is opened. (GUIDES-49448)

## Asset management

- In a UUID-based Experience Manager Guides as a Cloud Service environment, when you upload a modified file using the **Overwrite existing file** option, the upload appears to complete if the existing file has no Guides UUID and is stored in a folder listed under **Ignored Paths for Post Processing**. However, the existing file is not overwritten, and no new version is created. (GUIDES-55866)
- In a bookmap, when a `booktitle` element contains multiple sub-elements, such as `booklibrary` and `mainbooktitle`, extra whitespace is added between their values in the `dc:title` metadata. (GUIDES-28877)

## Publishing

- In the Map console, after output is generated for one map, the **Generate** button is disabled when another map is opened. Refreshing the browser enables the button again. (GUIDES-54591)
- Publishing certain maps to an AEM Site with component mapping fails with an error while the table of contents is being created. (GUIDES-53807)
- Publishing a map to an AEM Site with component mapping fails when the map contains a `topicref` element with a `navtitle` attribute and no `href` attribute. Subsequent attempts also fail, even after the element is removed, until the generated site nodes are deleted. (GUIDES-53707)
- In the AEM Site output with component mapping, Markdown headings of levels 2 to 6 are rendered as level 1 headings. (GUIDES-51134)
- For AEM Site output with component mapping, the prolog metadata, such as author, keywords, and resource ID, appears in the page body of the published output. (GUIDES-44087)
- Native PDF and AEM Site outputs with component mapping do not resolve keys that are referenced by using key scopes. (GUIDES-42260)
- When a topic is published to ServiceNow, the article body includes the short description and prolog of the topic. (GUIDES-47868)
- When a topic that is already published in ServiceNow is published again, a new article is created in the Draft state instead of the existing article being overwritten. (GUIDES-37872)
- When condition presets exclude topic references during publishing to Salesforce, the output generation is reported as failed, even though the remaining topics are published successfully. (GUIDES-37807)
- Publishing a large map to Salesforce fails with a gateway timeout error. (GUIDES-33722)
- Publishing a map to Salesforce fails with a limit exceeded error when a request contains more than 25 operations. (GUIDES-33721)
- In the Map Dashboard (Old), **Add all** in an existing condition preset does not pick up condition values that were added or changed after the preset was created. (GUIDES-45940)
- Logs in the **Output history** page containing warnings are shown with a green icon, which does not indicate that warnings are present. (GUIDES-27000)
- The glossary is not included in the output when no term in the map content refers to a glossary entry. (GUIDES-52964)
- Topics from a submap that is referenced in an appendix are rendered as chapters instead of appendix content. (GUIDES-52775)
- Some Simplified Chinese characters are rendered with a Japanese font when the output language is set to Chinese (Simplified). (GUIDES-48094)
- Index entries lose the text of child elements, such as `keyword`, `ph`, and `sup`. As a result, some index labels are incomplete or empty. (GUIDES-40902)
- Spaces around the inline `option` elements are not retained, leading to the adjacent text appearing joined together. (GUIDES-40900)

## Translation

- On the Translation page, searching and sorting by **Title** use the localized metadata value instead of the title that is displayed in the column. (GUIDES-45396)

## Review

- On the **Reviewers** page, during the creation or editing of a review task, the **Clear Selection**, **Add Reviewers**, **Remove Reviewers**, and **Re-assign Reviewers** buttons are enabled by default, even when no rows are selected. (GUIDES-35125) 
- In the AEM inbox, notifications related to review tasks, such as task assignment, feedback received, mentions, and due or overdue reminders, are displayed without any project name. (GUIDES-10912)
- In the Side-by-side view of a topic in a review task, content marked with strikethrough appears with different formatting in the two views. (GUIDES-56079)
- Opening a review task created in the 2026.08.0 or 2026.09.0 release may result in application errors. (GUIDES-56583) <br>**Workaround:** Complete or close all review tasks created in these releases before upgrading to the 2026.11.0 release.

## Learning content

- Generating a SCORM output for a large course, typically 300 MB to 600 MB, takes more than 30 minutes and fails without error details in the logs. (GUIDES-56101)
- The completion criteria for a SCORM output cannot be set in Experience Manager Guides. (GUIDES-55520)
- Images in AVIF format are displayed in the editor but are missing in the published output. (GUIDES-55515)
- The `href` attribute is removed from anchor tags in the published output, so links are not clickable. (GUIDES-55514)

## Platform

- When a user is assigned as an Admin User in a folder profile but is not a member of the administrators group, they cannot successfully add other Admin Users. Although a success message appears, the newly added users disappear after refreshing the page. (GUIDES-50144)

## Known issues

Adobe has identified the following known issues for the 2026.11.0 release:

## Authoring

- When you create a map from a template containing dependent topics or submaps, map creation may intermittently fail with an error, particularly when the server is under heavy load. (GUIDES-58715)

### Editor 2.0

- The **Refresh navigation title attribute** option does not add the `@navtitle` attribute to existing `topicref` elements in a DITA map. (GUIDES-54348) 

**Track changes**

When **Track changes** is turned on:

- Nested deletions by the same user are not always merged into a single entry when the element containing the deleted content is renamed or formatted. (GUIDES-58429)
- The **Track Changes** panel sometimes shows incomplete content for the parent element when a nested deletion is made by a different user. (GUIDES-58428)
- The red gutter marker does not appear on the left when you delete content within an insertion made by another user. (GUIDES-58418)

### Publishing

- In Native PDF output, superscript and subscript formatting is not preserved in index entries. (GUIDES-58349)
- When you use the same global preset to generate output for different maps, the topic selection from the previous map may affect the output of the new map. (GUIDES-58346) 
- When a book map contains a chapter with a valid `href` and a nested topic reference, publishing the map to AEM Sites results in a blank page. (GUIDES-58266)
- When you navigate to the **Output history** tab from a preset with unsaved changes, the **Save** and **Generate output** buttons remain visible. (GUIDES-57989)
- When a post-publishing workflow is configured for a preset, the publishing duration shown in **Output history** does not include the time taken by the workflow. (GUIDES-57856)
- You cannot cancel Native PDF output generation from the **Output history** page. (GUIDES-57821)

