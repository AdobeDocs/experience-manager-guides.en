---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 4.6.0 release
description: Learn about the bug fixes in the  4.6.0 release of Adobe Experience Manager Guides
role: Leader

---

# Fixed issues in the 4.6.0 release (August 2024)


This article covers the bugs fixed in various areas of 4.6.0 release of Adobe Experience Manager Guides.


## Authoring

- The **Find** option isn't working in the **Source** view. (18610)
- **Check out** and **Check in** icons appear together when `autocheckout` is configured in xmleditor. (18088)
- The **Layout** view switches with delays when opening the map for the first time in Experience Manager Guides. (17590)
- Error messaging type for duplicate image IDs in the topics does not appear as a warning. (17528)
- The copy and paste operation of topics exceeding 15KB fails with an unexpected error. (17171)
- The functionality to change the document state from the **File Properties** panel isn’t working correctly and changes to the *Draft* state. (17088)
- When changing the XML editor settings using a custom folder profile, the `ui_config.json` gets updated with an incorrect file. (17011)
- In the **Repository** panel, the **Filter** search doesn’t retain the value of **Checked out by** field when reopening the **Advanced filter** dialog box. (16935)
- Linked images from the topics fail to appear in the baseline after version creation. (16931)
- Reusable content panels don’t list elements when the **User preferences** are set to view files by **Filename**. (16896)
- Subelements within the table title element fail to render in the **Preview** mode of Experience Manager Guides. (16691)
- Execution of postprocess script fails due to **FileNotFoundException** exception. (16517)
- **Special characters** written with escape characters are removed from the topic after being uploaded to Experience Manager Guides.(16495)
- Vimeo videos don’t support fullscreen functionality in Experience Manager Guides. (15996)
- Pasting long preformatted text sequences in `<pre>` or `<codeblock>` elements leads to truncated text. (15859)
- Content deletion occurs due to duplicate GUIDs when templates are installed via code but remain unprocessed. (15858)
- Experience Manager Guides fail to adhere to the **Processing Role** attribute in **Preview** mode. (15787)
- The Editor intermittently deletes extra text beyond the selected area. (15708)
- Thumbnails generated from **Dynamic Media** for video files fail to persist in the published output. (15656)
- Inability to copy and paste large tables from Word documents or HTML into the Web Editor. (15369)
- The **Copy** function fails for empty folders in Experience Manager Guides as a Cloud Service. (15353)
- Lack of APIs or events to capture attribute addition to an element or insertion of a new element. (15351)
- Inability to add `<data>` tag within `<ol>` tag in the Web Editor. (15161)
- When Unified Shell is enabled, the **Version Label Management** dialog box incorrectly displays **Main Content** for versions without labels. (15039)
- The **Element** placeholder component causes the UI to freeze. (14957)
- The Web Editor is unable to upload .pptx files. (14837)
- While finding a text in the Web Editor, the cursor returns to the first occurrence of the searched text, on pressing the Enter key. (14820)
- Autosave causes multiple issues, it repositions the cursor, and requires manual clicks in the document. (14253)
- Pressing the **Enter** key in a table cell within the text does not split the paragraph as expected. (14251)
- Large files don't load in the Web Editor and cause the browser to freeze. (13227)
- The search results are disabled after opening a file found through global **Find and Replace**. (12142)
- In the source view, `</conbody>` is occasionally inserted in incorrect locations. (11305)
- The component path `/libs/fmdita/components/versions` is hardcoded and the users can't overlay it. (8779)

## Publishing

- Cross-reference to the key is not getting resolved in the Native PDF output. (18087)
- The **duplicate_value** error intermittently occurs when republishing an existing article in Salesforce. (17932)
- Salesforce connection validation fails with the lightning URL. (17797)
- Metadata properties are not propagated in the Native PDF output. (17283)
- Condition filtering in Native PDF output isn't working as expected compared to DITA-OT. (17095)
- TOC does not honor `<sub>` or `<sup>` tags in the Native PDF output. (17028)
- Native PDF generation fails on ARM64 architecture in Experience Manager Guides as a Cloud Service. (16968)
- Crossmap linking fails to display all parent maps in the publishing context settings for a link that has the `peer @scope`. (16700)
- AEM Site generation and incremental publish API isn't working as expected. (16666)
- AEM Site output generation fails when the **Delete Orphan Site** option is enabled. (15896)
- The old attributes are retained in the **Condition Presets** when adding or removing any new or existing attributes. (15890)
- The edit functionality isn't working when adding files to the Map Collection. (15813)
- In the JSON output, metadata from DITA map or topics fails to propagate to the JSON output files. (15713)
- The RTL language content isn’t handled correctly in the Native PDF publishing output. (15709)
- Native PDF publishing fails when the preset is renamed. (15662)
- The **sourcePath** property is incorrect on the published AEM site output. (15502)
- The selection and customization of language variables are not working properly in the Native PDF Output Preset. (15399)
- Native PDF generation fails when using a large stylesheet or layout template. (15344)
- Content isn’t rendered properly in the published output if `<conref>` is used with an absolute path. (15222)
- AEM Sites URL shortening isn't working due to conflicts between the `fmdita rewriter` and `ResourceResolver`. (14793)
- Native PDF generation fails with an error related to getting dependencies for Node.js. (14445)
- The **processing-role=“resource-only”**, **search=“no”**, and **chunk=“to-content”** attributes appear irrespectively in AEM Sites output. (14442)
- `<Conref>` doesn't appear when publishing the Native PDF output from the **Preview** mode of the Web Editor. (17827)
- In Native PDF, nested DITA topics are displayed incorrectly in the Table of Contents (TOC). (16742)


## Management

- The referenced PDF isn't activated from the **Bulk Publish Dashboard** during the Bulk Activation of published content. (17793)
- InDesign to DITA conversion has a hardcoded configuration path so the custom config files are not picked. (16891)
- Unclosed **Resource Resolvers** cause increasing session count and `PathNotFoundException` errors post the October 2023 release of Experience Manager Guides as a Cloud Service. (15604)
- The feature flag **fmdita.useapproval** isn't working as expected. (15310)
- Error in installing Guides packages in large repositories. (15160)
- If a folder that contains 2k maps is set in the folder path inside any folder profile, the changes applied to the output preset fail. (14852)
- Creating a baseline using the Java API does not work with the June 2023 release of Experience Manager Guides as a Cloud Service. (14787)
- The `/bin/fmdita/import` API remains stuck in pending request indefinitely when the uploading assets exceed 500 MB. (14743)
- Editing an existing baseline and selecting a specific version triggers application errors. (14451)
- Opening a DITA topic or map in a new tab for editing freezes the selection navigation in the Assets UI.(4992)


## Review

- Fetching the user list while creating a review task fails if the user count exceeds 25. (17329)
- Deleting review nodes disrupts the ability to open and view comments in Adobe Experience Manager Guides. (15366)
- In the Web Editor, the Review panel loads slowly. (14680)

## Translation

- The references of translated assets are not updated. (18086)
- Unable to create XLIFF projects with human translation. (16964)
- The title with `<conref>` doesn't display in the baseline dashboard and other views of the Web Editor. (16961)
- Dynamic titles fail to appear in Manage Translation. (16879)
- Translation projects fail to add new language jobs to Adobe Experience Manager 6.5 SP18 with the October 2023 release of Experience Manager Guides. (15398)
- **Accept Translation** fails to complete the translation of temporary files. (14665)
- Adding an updated topic in an active translation project results in a duplicate topic and the process fails. (7688)

### Editor

- The **Preview** feature for `<conref>` is not working. (17794)
- The Experience Manager DITA Guide fails to trigger the Save function after using the auto-indent feature. (16482)
- Review topics don’t appear in the correct order. (16319)
- The tooltip feature fails to update the Source field in the XML Editor. (15847)
- The **Share UUID Link** feature isn't working for the images in Adobe Experience Manager. (15598)
- In the **Author** view, a copy-and-paste issue occurs when using non-breaking spaces and results in overflowing of text. (15541)
- Overlapping text issues occur in `<reltable>` and `<fig>` tags. (15238)
- Flickering issues occur in the **Attributes** panel. (15237)
- In `<othermeta>` element within `<topicmeta>`, on adding a `<conref>` to another DITA map, the map ID is also appended along with the ID of the element. (15226)
- The cursor jumps between the block elements when deleting a character or word within the content. (15224)
- File checked out by "" error message displays incorrectly when editing files are moved from another tab, when tokens are expired, or when the user is logged out. (15223)
- The `<conref>` cannot be updated from the **Attributes** panel when making changes. (15209)
- The entire cell is selected when selecting an image within a table cell. (15188)
- The **Attributes** panel isn't displayed in the Source view of the Web Editor. (14387)
- `<Topicref>` added using `<keyref>` doesn't display in Native PDF. (11974)
- Unwanted, non-breaking spaces get added while editing at the end of a tag in the Web Editor. (11786)
- Content gets deleted while correcting the spelling errors in DITA files. (11610)

## Cloud Service

- The DITA version incorrectly displays the username in the Assets UI. (17580)
- Adobe Experience Manager Tools navigation is unresponsive. (17118)
- Build Transform phase in Cloud Services deployment fails with errors from the DITA codebase. (14432)

## Reports

- Dynamic titles with `<conkeyref>` don't appear in the Report topic list. (16967)
- The inaccurate **Topic List** counts in Experience Manager Guides UI due to unpatched properties when copying DITA assets impact the reports generated for a DTIA map. (15529)
- Topics containing external references with %20 in the URL display broken file references. (15347)


## API

- Topic regeneration fails due to the OOTB Regenerate Topic or incremental publish API failure. (18452)

## General

- The condition preset doesn't fetch updated attributes after upgrading from 4.3.0 to 4.4.0 release of Experience Manager Guides.
