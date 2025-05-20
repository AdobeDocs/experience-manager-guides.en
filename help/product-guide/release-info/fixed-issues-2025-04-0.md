---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2025.04.0 release
description: Learn about the bug fixes in the 2025.04.0 release of Adobe Experience Manager Guides as a Cloud Service.
exl-id: ad3e95b5-4903-4387-8e4d-c4b9ba77fee2
---
# Fixed issues in the 2025.04.0 release 

This article covers the bugs fixed in various areas of the 2025.04.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2025.04.0 release](whats-new-2025-04-0.md).

Learn about [upgrade instructions for the 2025.04.0 release](upgrade-instructions-2025-04-0.md).

## Authoring

- Special character insertion box in the Editor fails to load for German locale. (24537) 
- Comments and labels added while saving a new version of a DITAVAL file are not getting saved in the Version History with the new version. (24076)
- The outgoing and incoming references under **File properties** in the right panel do not refresh properly when switching between map files. This issue occurs specifically when the map files contain a large number of references. (23344)
- The Repository filter does not retain the order of custom filters defined in the `ui_config.json`. (21193)
- Deleting multiple lines of text in a `codeblock` element creates an empty space which can not be removed from Author view. (20672)
- New ids fail to generate for elements when such elements are added via snippets or created via templates, even when the **auto generate ID** option is enabled in `XMLEditorConfig`. (21734)
- Creating a new DITA asset from DITA templates copies the replication properties from corresponding DITA templates. (25145) 
- Unable to access file properties from the repository panel if the parent folder name includes "&" character. (25762)
- Closing a topic file allows it to be saved as a new version, even when the topic is locked. This issue occurs specifically when the **Ask for new version on close** option is enabled in `XMLEditorConfig`. (23875)
- The current maximum width of the repository panel hides topic and map titles when the content hierarchy is deeply nested. (27751)

## Publishing

- In the legacy AEM Sites output, section links within nested topics of a map do not resolve correctly when manually set in Source mode or the content is imported from an external source. Instead of navigating to the intended section, they redirect to the main topic that contains the nested topic. (26103)
- If the `scope=external` attribute is missing from external links in a DITA topic, HTML5 publishing fails without indicating the files where this attribute is missing in the error logs, especially when the microservice is enabled. (25969) 
- Unable to embed video links in Native PDF even when the **Embed Multimedia Files** option is enabled in the PDF preset. (9989)
- Unable to pass the metadata properties to map landing pages generated using new AEM Sites publishing. (27288) 

## Management 

- Document state from the working copy of a topic is displayed against all the versions of that topic in the Translation and Baseline UI. (20674) 


## Review

- Updating the details of a review task in the Review dashboard does not confirm whether the update was successful or unsuccessful. (8051) 

## Translation

- Translations submitted through Experience Manager Guides do not include the attached assets, causing the **Start** button for translation job to become unavailable to users. 

## Known Issues

Adobe has identified the following known issues for the 2025.04.0 release:

- The reference count in the Baseline UI does not update upon editing the Baseline. It only updates when the changes are saved. (28015)
- When multiple tabs are open in the Editor, performing an **Undo** operation in the **Source** view of a file reverts the last edit but also switches to the previously opened tab. (27891)
- The **AEM Spell Check** option appears in the **Menu** dropdown list, even when the **Browser spell check** option is enabled in the Editor settings. (27993)
- An additional version is created and shown in the **Version History** panel when you edit an image in the Assets UI and save it. (28001) 
- An empty line is automatically inserted when pasting new content into a new line within a `codeblock` element.(27842)
- Switching between presets that use the same Baseline deactivates the **Save** button for the current preset. (28025) 
- A topic within a DITA map fails to publish in the AEM Sites output when it is being used as both `keydef` and `topicref` within its submaps. (22269)
- An application error occurs when multiple topics of a map are edited and then closed using the **Close all** option, with the **Ask on save version on close** setting enabled.(27931)

Adobe has identified the following known issues with a workaround:

+++In AEM Sites output, images break when Baseline is not applied while publishing. (28043)
***Workaround:*** You can publish such assets from **Assets UI**, post which the link becomes operational.
+++