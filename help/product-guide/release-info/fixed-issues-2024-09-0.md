---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2024.09.0 release
description: Learn about the bug fixes in the 2024.09.0 release of Adobe Experience Manager Guides as a Cloud Service.
exl-id: 608e5b2c-72af-4498-9b63-935e698231d4
---
# Fixed issues in the 2024.09.0 release 

This article covers the bugs fixed in various areas of the 2024.09.0 release of Adobe Experience Manager Guides as a Cloud Service.



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

## Publishing

- The condition preset doesn't fetch updated attributes after upgrading Experience Manager Guides. (18174)
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
- The referenced PDF isn't activated from the **Bulk Publish Dashboard** during the Bulk Activation of published content. (17793)
- Content references are not correctly resolved for Native PDF output if the file containing key definitions is not in the same folder as the DITA map. (15062)

## Management

- The fmditaMaprefs and fmditakeydefrefs properties display relative paths, despite setting absolute paths for the DITA map and topics. (18353)
- The path for the Overlay functionality is hard-coded for the Korean language file and is not correctly selected. (17089)
- Dynamic titles with `<conkeyref>` don't appear in the Report topic list. (16967)
- InDesign to DITA conversion has a hardcoded configuration path so the custom config files are not picked. (16891)
- Error in installing Guides packages in large repositories. (15160)

### Review

- Fetching the user list while creating a review task fails if the user count exceeds 25. (17329)

## Translation

- The references of translated assets are not updated. (18086)
- References are not correctly filtered as Direct or Indirect while translating into multiple languages. (17891)
- Unable to create XLIFF projects with human translation. (16964)
- The title with `<conref>` or `<conkeyref>` doesn't resolve in the Baseline and Translation dashboards of the Web Editor. (16961, 16879)
- Adding an updated topic in an active translation project results in a duplicate topic and the process fails. (7688)


