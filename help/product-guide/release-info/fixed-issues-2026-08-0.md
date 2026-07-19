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

**Map collections and bulk activation**

The following issues have been fixed with the [New map collection](../user-guide/generate-output-use-new-map-collection-output-generation.md#use-new-map-collection-for-output-generation-beta) feature available in the 2020.08.0 release of Experience Manager Guides:

- Unable to load a map collection with more than 100 map entries due to a network error. (GUIDES-34007)
- Unable to select multiple maps at once from a folder in the Map Collection UI. (GUIDES-29581)
- Unable to search or filter map collections in the Map Collections UI. (GUIDES-27723)
- Unable to close the Bulk Publish/Activation dashboard or navigate back to **Tools** or the homepage without using the browser's back button. (GUIDES-26797)
- Inability to easily manage map collections with a large number of maps or languages. (GUIDES-21735)
- Unable to view or publish generated output directly from the Map Collection or Bulk Activation Dashboard interfaces. (GUIDES-18712)
- Unable to use a single collection to both generate and activate maps, since Map Collections and the Bulk Activation Dashboard manage separate sets of collections. (GUIDES-12730)

## Review

- In the Review UI, the tagging list displays all users in the review task, which makes it difficult to select the correct user in a comment or reply. (GUIDES-33420)
- Opening the **side-by-side** view in the Comments panel displays the working copy alongside the commented version, but the panes do not scroll in sync horizontally, and clicking a comment does not move the cursor to the corresponding text. (GUIDES-44083)

## Database 

- `DatabaseConfiguratorService` throws an error in the logs even when the `GUIDES_ENABLE_DATABASE` flag is not set. (GUIDES-43481)

## Known issues

Adobe has identified the following known issues for the 2026.08.0 release:

## Editor 2.0

- Closing a DITAVAL file that has been moved to a different location results in an `ERROR IN FETCHING VERSION DETAILS` error message. (GUIDES-51420)
- Conflict API fails and leads to an application error when the repository folder path ends with a forward slash. (GUIDES-51006)
- Alphanumeric terms added to the user dictionary are still flagged by the spell checker instead of being ignored. (GUIDES-48587)
- Selecting a processing instruction element in the Outline view highlights the entire parent tag instead of the selected element. (GUIDES-48318)
- The map preview in the Editor takes a long time to load, and the preview screen sometimes remains blank. (GUIDES-46500)
- Editing a keyword within a `keyref` in the source view breaks the keyword when the view is switched to any other view. (GUIDES-49998)
- A MathML equation wrapped inside a `foreign` and `equation` block results in unwanted spacing, and typing inside the equation causes issues even after adjusting indentation. (GUIDES-46606)
- Unable to place a cursor inside a `topicref` within a `reltable` when the **Show tags** option is enabled and the **Display attributes** option is disabled in the Editor settings. (GUIDES-46565) 
- Dragging and dropping a reference into an empty `keydef` adds a `topicref` element instead of updating the reference. (GUIDES-45068)

## Publishing

- Selecting **View output** after generating Edge Delivery Services output opens an `hlx.live` URL that returns a 403 Forbidden error instead of the `aem.live` URL. (GUIDES-51572)
- Invalid components are displayed on the `common.plt` page on adding an image, hyperlink, or iframe from a template's toolbar. (GUIDES-51165)
- Publishing a map that references a topic using the `copy-to` attribute removes the peer scope link from the corresponding topic in the source map. (GUIDES-50701)
- When a PDF is referenced as an `xref` with scope set to Peer, it is published on the AEM site (using legacy component mapping) instead of being sourced from the cross map. (GUIDES-50213)
- Starting a translation with the **Create structure only** option returns an error. (GUIDES-51261)

**Map collections**

- Deleting a map collection sometimes fails if you switch tabs (such as Repository or Overview) and then return to the Map Collection page before deleting it. (GUIDES-50997)
- Generating the same preset while a previous generation is in progress no longer shows a message indicating the earlier generation is in progress. (GUIDES-50523)
- The last generation timestamp is not shown or updated in the Map Collection UI after a map is generated, and re-adding a preset that was previously removed causes its generation history to be lost again. (GUIDES-50511)
- Publishing from the Generation History always publishes the latest output of a preset instead of the selected generation. (GUIDES-50508)
- The publishing status does not automatically refresh for newly created map collections. (GUIDES-50367)

## Review

- Performing a strikethrough using a keyboard shortcut over text that includes hidden conditional content also strikes through the hidden content. (GUIDES-49837)


