---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 4.6.0 release
description: Learn about the bug fixes in the  4.6.0 release of Adobe Experience Manager Guides
role: Leader

---

# Fixed issues in the 4.6.0 release (September 2024)


This article covers the bugs fixed in various areas of 4.6.0 release of Adobe Experience Manager Guides.


For more information about the new features and enhancements, view [What's new in  the 4.6.0 release](whats-new-4-6.md).

Learn about [upgrade instructions for the 4.6.0 release](../release-info/upgrade-instructions-4-6-0.md).

## Authoring

- The **Find** option isn't working in the **Source** view. (18610)
- **Check out** and **Check in** icons appear together when `autocheckout` is configured in xmleditor. (18088)
- Large DITA maps load slowly and take time in switching to the **Layout** view.  (17590)
- Errors for duplicate image IDs in the topics restrict the user from saving or authoring a topic. (17528)
- The copy and paste operation of topics exceeding 15KB fails with an unexpected error. (17171)
- The functionality to change the document state from the **File Properties** panel isn’t working correctly and changes to the *Draft* state. (17088)
- When changing the XML editor settings using a custom folder profile, the `ui_config.json` gets updated with an incorrect file. (17011)
- Reusable content panels don’t list elements when the **User preferences** are set to view files by **Filename**. (16896)
- Subelements within the table title element fail to render in the **Preview** mode of Experience Manager Guides. (16691)
- **Special characters** written with escape characters are removed from the topic after being uploaded to Experience Manager Guides. (16495)
- Vimeo videos don’t support fullscreen functionality in Experience Manager Guides. (15996)
- Pasting long preformatted text sequences in `<pre>` or `<codeblock>` elements leads to truncated text. (15859)
- Content deletion occurs due to duplicate GUIDs when templates are installed via code but remain unprocessed. (15858)
- Experience Manager Guides fail to adhere to the **Processing Role** attribute in **Preview** mode. (15787)
- The Editor intermittently deletes extra text beyond the selected area. (15708)
- Inability to copy and paste large tables from Word documents or HTML into the Web Editor. (15369)
- Lack of APIs or events to capture attribute addition to an element or insertion of a new element. (15351)
- Inability to add `<data>` tag within `<ol>` tag in the Web Editor. (15161)
- The **Element** placeholder component causes the UI to freeze. (14957)
- The Web Editor is unable to upload .pptx files. (14837)
- While finding a text in the Web Editor, the cursor returns to the first occurrence of the searched text, on pressing the Enter key. (14820)
- Autosave causes multiple issues, it repositions the cursor, and requires manual clicks in the document. (14253)
- Pressing the **Enter** key in a table cell within the text does not split the paragraph as expected. (14251)
- Large files don't load in the Web Editor and cause the browser to freeze. (13227)
- The search results are disabled after opening a file found through global **Find and Replace**. (12142)
- In the source view, `</conbody>` is occasionally inserted in incorrect locations. (11305)
- The component path `/libs/fmdita/components/versions` is hardcoded and the users can't overlay it. (8779)
- `<conref>` for a topic referenced within a DITA map isn't getting reflected in the preview within the editor. (17794)
- The Experience Manager DITA Guide fails to trigger the Save function after using the auto-indent feature. (16482)
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
- Opening a DITA topic or map in a new tab for editing freezes the selection navigation in the Assets UI. (4992)
- Deleting review nodes disrupts the ability to open and view comments in Adobe Experience Manager Guides. (15366)
- The DITA version incorrectly displays the username in the Assets UI. (17580)
- The `<title>` element is automatically added when the `<fig>` element is inserted as a snippet. (18562)
- Issues occur while uploading a large number of files with dense datasets to Experience Manager Guides.(17008)
- The Web Editor fails to display the correct keyword by default, especially if the keyword is defined differently in child maps. (14748)
- The **Document State** is not displayed when editing the properties of more than 50 files in bulk from the Map view of the Web Editor. (14574)
- The behavior of the Close button is inconsistent when using the Auto Save functionality. (10996)
- Validation issues occur in MathML elements when inserting any new element or modifying equations. (10624)
- The Track Changes functionality does not work with text that begins with Korean characters. (14538)



## Publishing

- Cross-reference to the key is not getting resolved in the Native PDF output. (18087)
- The **duplicate_value** error intermittently occurs when republishing an existing article in Salesforce. (17932)
- Salesforce connection validation fails with the lightning URL. (17797)
- When selecting the **Use metadata added in the topicmeta** option, the metadata properties are not propagated in the document proprieties of the Native PDF output.(17283)
- Condition filtering in Native PDF output isn't working as expected compared to DITA-OT. (17095)
- TOC does not honor `<sub>` or `<sup>` tags in the Native PDF output. (17028)
- Crossmap linking fails to display all parent maps in the publishing context settings for a link that has the `scope="peer"` . (16700)
- AEM Site generation and incremental publish API isn't working as expected. (16666)
- AEM Site output generation fails when the **Delete Orphan Site** option is enabled. (15896)
- The old attributes are retained in the **Condition Presets** when adding or removing any new or existing attributes. (15890)
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
- `<Conref>` doesn't get resolved in the `Preview` mode of the Web Editor and the Native PDF output. (17827)
- In Native PDF, nested DITA topics are displayed incorrectly in the Table of Contents (TOC). (16742)
- Thumbnails generated from **Dynamic Media** for video files fail to persist in the published output. (15656)
- The referenced PDF isn't activated from the **Bulk Publish Dashboard** during the Bulk Activation of published content. (17793)
- If a folder that contains 2k maps is set in the folder path inside any folder profile, the changes applied to the output preset fail. (14852)
- Topic regeneration fails due to the OOTB Regenerate Topic or incremental publish API failure. (18452)
- The condition preset doesn't fetch updated attributes after upgrading Experience Manager Guides. (18174)
- Content references are not correctly resolved for Native PDF output if the file containing key definitions is not in the same folder as the DITA map. (15062)


## Management


- InDesign to DITA conversion has a hardcoded configuration path so the custom config files are not picked. (16891)
- Unclosed **Resource Resolvers** cause increasing session count and `PathNotFoundException` errors post the 4.3.1 release of Experience Manager Guides. (15604)
- Error in installing Guides packages in large repositories. (15160)
- Creating a baseline using the Java API does not work with  Experience Manager Guides. (14787)
- The `/bin/fmdita/import` API remains stuck in pending request indefinitely when the uploading assets exceed 500 MB. (14743)
- Editing an existing baseline and selecting a specific version triggers application errors. (14451)
- Execution of postprocess script fails due to **FileNotFoundException** exception. (16517)
- Dynamic titles with `<conkeyref>` don't appear in the Report topic list. (16967)
- The inaccurate **Topic List** counts occur in Experience Manager Guides Reports UI due to the unpatched properties when copying DITA assets. (15529)
- Topics containing external references with %20 in the URL display broken file references. (15347)
- The fmditaMaprefs and fmditakeydefrefs properties display relative paths, despite setting absolute paths for the DITA map and topics. (18353)
- The path for the Overlay functionality is hard-coded for the Korean language file and is not correctly selected. (17089)
- The default time in the Baseline creation in the Web Editor is displayed as 00:00 instead of the current time. (15215)

## Review

- Fetching the user list while creating a review task fails if the user count exceeds 25. (17329)
- Review topics don’t appear in the correct order. (16319)
- In the Web Editor, the Review panel loads slowly. (14680)
- Reviewers cannot add, highlight, or strike out spaces when performing a document review in Experience Manager Guides. (14752)
- When a user updates a Review task, not all assigned reviewers receive a notification about the update. (9496)

## Translation

- The references of translated assets are not updated. (18086)
- Unable to create XLIFF projects with human translation. (16964)
- The title with `<conref>` or `<conkeyref>` doesn't resolve in the Baseline and Translation dashboards of the Web Editor. (16961, 16879)
- Translation projects fail to add new language jobs to Adobe Experience Manager 6.5 SP18 with the 4.3.1 release of Experience Manager Guides. (15398)
- **Accept Translation** fails to complete the translation of temporary files. (14665)
- Adding an updated topic in an active translation project results in a duplicate topic and the process fails. (7688)
- References are not correctly filtered as Direct or Indirect while translating into multiple languages. (17891)
- XLIFF-based translation fails with error for "Non-admin" users.(17296)
- The title of translated files reverts to English after the second translation, even though the content has been translated. (15200)
- When selecting a translation project with the **Translation Status** as **In progress**, an incorrect page opens. (13248)
- The translation projects created by selecting the **Create structure only** option don't have UUIDs assigned. (18980)


## Known issues

Adobe has identified the following known issues for the 4.6.0 release:
- Opening an **AEM Sites** preset (non-legacy) marks the topic as dirty.
- The selected panel isn't getting retained on browser refresh from the **Output** tab.
- Unable to drag and drop topics between two `topicrefs` in the **Author** view.
- Condition filtering applied in the preset isn't getting applied via **Download as PDF**.
- Single topic generation from the map panel generates all topics selected in the **AEM Sites** preset (non-legacy).
- The topic’s reference appears broken in the user interface when inserted from the top toolbar of the DITA map.
- Native PDF generation fails for a DITA map if it has missing references.
- Once a topic’s document state is updated to **Done**, the **Start a New Release** icon is only available on the **Preview** mode of the topic.
 - When selecting a DITA asset in the Asset UI, the option **Open in FrameMaker** appears, even though it is disabled in the configuration settings.



