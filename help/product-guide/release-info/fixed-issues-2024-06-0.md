---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2024.06.0 release
description: Learn about the bug fixes in the 2024.06.0 release of Adobe Experience Manager Guides as a Cloud Service.
---

# Fixed issues in the 2024.06.0 release 

This article covers the bugs fixed in various areas of the 2024.06.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2024.06.0 release](whats-new-2024-06-0.md).

Learn about [upgrade instructions for the 2024.06.0 release](upgrade-instructions-2024-06-0.md).

## Authoring

- The copy and paste operation of topics exceeding 15KB fails with an unexpected error. (17171)
- The functionality to change the document state from the  **File Properties** panel isn't working correctly and changes to the *Draft* state. (17088)
- When changing the XML editor settings using a custom folder profile, the `ui_config.json` gets updated with an incorrect file. (17011)
- In the Web Editor, the **Filter** search doesn't show the earlier selected values when reopening the **Advanced filter** dialog box in the **Repository** panel search. (16935)
- Linked images from the topics fail to appear in the baseline after bulk **Save as New Version and Unlock** is selected.(16931)
- Reusable content panels don't list elements when the **User preferences** are set to view files by **Filename**.(16896)
- Subelements within the table title element fail to render in the **Preview** mode of Experience Manager Guides. (16691)
- Execution of postprocess script fails due to **FileNotFoundException** exception. (16517)
- Vimeo videos don't support fullscreen functionality in Experience Manager Guides. (15996)
- Pasting long preformatted text sequences in `<pre>` or `<codeblock>` elements leads to truncated text. (15859)
- Content deletion occurs due to duplicate GUIDs when templates are installed via code but remain unprocessed. (15858)
- Experience Manager Guides fail to adhere to the **Processing Role** attribute in **Preview** mode. (15787)
- The Editor intermittently deletes extra text beyond the selected area.  (15708)
- Inability to copy and paste large tables from Word documents or HTML into the Web Editor. (15369)
- The **Copy** function fails for empty folders in Experience Manager Guides as a Cloud Service. (15353)
- Lack of APIs or events to capture attribute addition to an element or insertion of a new element. (15351)
- Inability to add `<data>` tag within `<ol>` tag in the Web Editor. (15161)
- When Unified Shell is enabled, the **Version Label Management** dialog box incorrectly displays **Main Content** for versions without labels. (15039)
- Large files load slowly in the Web Editor, with a delay of a few seconds. (14958)
- Performance issues occur while authoring large files in the Web Editor. (14957)
- Pressing the **Enter** key in a table cell within the text does not split the paragraph as expected. (14251)
- The Experience Manager DITA Guide fails to trigger the **Save** function after using the auto-indent feature. (16482)
- Review topics don't appear in the correct order. (16319)
- In the **Author** view, a copy-and-paste issue occurs on using non-breaking spaces and results in overflowing of text. (15541)

- On adding a `<conref>` in a DITA map , the Map ID of the parent map is also appended along with the ID.(15226)
- The `<conref>` cannot be updated from the **Attributes** panel when making changes. (15209)
- When selecting an image within a table cell, the entire cell is selected. (15188)

## Publishing


- Crossmap linking fails to display all parent maps in the publishing context settings for a link that has the `peer @scope`. (16700)
- On adding any new or removing any existing attributes, the old attributes are retained in the **Condition Presets**. (15890)
- The RTL language content isn't handled  correctly in the Native PDF publishing output. (15709)
- The first PDF is not versioned when a Native PDF output is generated. (10305)
- In Native PDF, nested DITA topics  are displayed incorrectly in the Table of Contents (TOC). (16742) 
- Thumbnails generated from Dynamic Media for video files fail to persist in the published output. (15656)
- Output generation fails for Native PDF Publishing on AEM64 processor.(16968)

## Management

- Editing an existing baseline and selecting a specific version triggers application errors. (14451)

## Translation

- Translation projects fail to add new language jobs to Adobe Experience Manager 6.5 SP18 with the October 2023 release of Experience Manager Guides. (15398)

## Cloud Service

- Adobe Experience Manager Tools navigation is unresponsive. (17118)
- Build Transform phase in Cloud Services deployment fails with errors  from the DITA codebase. (14432)

## Reports

- The inaccurate **Topic List** counts in Experience Manager Guides UI due to unpatched properties when copying DITA assets impact the reports generated for a DTIA map. (15529)
- Topics containing external references with *%20* in the URL display broken file references. (15347)

