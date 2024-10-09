---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2024.10.0 release
description: Learn about the bug fixes in the 2024.10.0 release of Adobe Experience Manager Guides as a Cloud Service.
---
# Fixed issues in the 2024.10.0 release 

This article covers the bugs fixed in various areas of the 2024.10.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2024.10.0 release](whats-new-2024-10-0.md).

Learn about [upgrade instructions for the 2024.10.0 release](upgrade-instructions-2024-10-0.md).


## Authoring

- The **Find** option isn't working in the **Source** view. (18610)
- The `<title>` element is automatically added when the `<fig>` element is inserted as a snippet. (18562)
- Topic regeneration fails due to the OOTB Regenerate Topic or incremental publish API failure. (18452)
- Experience Manager Guides instance becomes unstable and the error logs increase in size upto 30-40 GB after accessing the Assets UI. (18414)
- **Check out** and **Check in** icons appear together when `autocheckout` is configured in xmleditor. (18088)
- Copy-paste of images from the Author view is not working in 2024.06.0 release of Adobe Experience Manager Guides as a Cloud Service.(18062)
- `<conref>` for a topic referenced within a DITA map isn't getting reflected in the preview within the editor. (17794)
- Large DITA maps load slowly and take time in switching to the **Layout** view. (17590)
- The DITA version incorrectly displays the username in the Assets UI. (17580)
- Errors for duplicate image IDs in the topics restrict the user from saving or authoring a topic. (17528)
- Issues occur while uploading a large number of files with dense datasets to Experience Manager Guides.(17008)
- Intermittent failures occur with the PDF rendering functionality in Experience Manager Guides as a Cloud Service. (16966)
- While creating a DITA map based on a template, the OOTB DXML workflow causes process interruptions and leads to 503 unserviceable errors. (16529)
- **Special characters** written with escape characters are removed from the topic after being uploaded to Experience Manager Guides. (16495)
- File checked out by "" error message displays incorrectly when editing files are moved from another tab, when tokens are expired, or when the user is logged out. (15223)
- Large files don't load in the Web Editor and cause the browser to freeze. (13227)
- `<Topicref>` added using `<keyref>` doesn't display in Native PDF. (11974)
- The component path `/libs/fmdita/components/versions` is hardcoded and the users can't overlay it. (8779)
- Opening a DITA topic or map in a new tab for editing freezes the selection navigation in the Assets UI. (4992)
- Downloading a DITA map with large video files triggers out-of-memory error in the logs and fail on the UI. (18884)
- When inserting a MathML equation containing the "<" symbol, an **Invalid character** error is generated. (18742)
- Incorrect UUID generation during the content ingestion process leads to broken submap references in the ingested map. (18308)
- In some cases, delays in processing a new DITA topic is observed when created from the web editor. (16836)
- Searching files in the **Repository** inside the web editor takes too long and sometimes fails to load the results. (16837)

## Publishing

- Cross-reference to the key is not getting resolved in the Native PDF output. (18087)
- The **duplicate_value** error intermittently occurs when republishing an existing article in Salesforce. (17932)
- Styling and content formatting in customer templates change automatically when layout includes metadata fields, causing incorrect formatting in published PDFs. (17900)
- Salesforce connection validation fails with the lightning URL. (17797)
- The referenced PDF isn't activated from the **Bulk Publish Dashboard** during the Bulk Activation of published content. (17793)
- Bulk Activation of published content isn't working for localized maps. (17638)
- When selecting the **Use metadata added in the topicmeta** option, the metadata properties are not propagated in the document proprieties of the Native PDF output. (17283)
- Condition filtering in Native PDF output isn't working as expected compared to DITA-OT. (17095)
- TOC does not honor `<sub>` or `<sup>` tags in the Native PDF output. (17028)
- AEM Site generation and incremental publish API isn't working as expected. (16666)
- Native PDF generation fails with an error related to getting dependencies for Node.js. (14445)
- `<Conref>` doesn't get resolved in the `Preview` mode of the Web Editor and the Native PDF output. (17827)
- Content references are not correctly resolved for Native PDF output if the file containing key definitions is not in the same folder as the DITA map. (15062)
- When a DITA map contains heading levels up to 7 or higher, the level 7 heading is incorrectly treated as a level 1 heading in the Native PDF output. (19698)
- When a content piece (text) is wrapped inside an element, the spaces before and after the text do not show in the Preview or Output formats. (19308)
- Post generation workflows triggered manually fails due to an NULL POINTER EXCEPTION in the workflow, leading to the content being uploaded 11 times. (18880)
- **Bulk Publish Dashboard** shows blank for maps that are still in the translation process. (19352)


## Management

- The path for the Overlay functionality is hard-coded for the Korean language file and is not correctly selected. (17089)
- Changes/customization made to the **Save Version** dialog do not reflect when using Guides Extension Framework. (17828)
- InDesign to DITA conversion has a hardcoded configuration path so the custom config files are not picked. (16891)
- Complete references/assets do not download when a DITA map containing large dependencies/references is downloaded using Baseline. (19099)


### Review

- Fetching the user list while creating a review task fails if the user count exceeds 25. (17329)
- If a task-topic contains `<cmd>` tag in one or more steps, the review panel displays the attribute `importance` as a prefix in all the steps containing the tag. (19699)

## Translation

- The references of translated assets are not updated. (18086)
- References are not correctly filtered as Direct or Indirect while translating into multiple languages. (17891)
- Unable to create XLIFF projects with human translation. (16964)
- Adding an updated topic in an active translation project results in a duplicate topic and the process fails. (7688)
- The translation projects created by selecting the **Create structure only** option don’t have UUIDs assigned. (18980)
- When selecting a translation project with the **Translation Status** as **In progress**, an incorrect page opens. (13248)
- The title with `<conref>` doesn’t resolve in the Baseline and Translation dashboards of the Web Editor. (16961)


