---
title: Release Notes | Fixed issues in the 2024.12.0 release of Adobe Experience Manager Guides
description: Learn about the bug fixes in the 2024.12.0 release of Adobe Experience Manager Guides as a Cloud Service.
exl-id: 04a57e1a-6e74-46f6-acde-5045d3dcacdc
---
# Fixed issues in the 2024.12.0 release

This article covers the bugs fixed in various areas of the 2024.12.0 release of Adobe Experience Manager Guides as a Cloud Service.

Learn about [upgrade instructions for the 2024.12.0 release](./upgrade-instructions-2024-12-0.md).

## Authoring

- DITA map creation on a UUID instance fails when `xmleditor.uniquefilenames` is enabled in `XMLEditorConfig`. (21201)
- When closing a file, comments and labels added in the **Save Changes and Unlock File** dialog box are not getting saved in the Version History with the new version. This is specific to a use case where **Ask for Check-in on Close** or **Ask for New Version on Close** is enabled in `XMLEditorConfig`. (20065)
- Document state marked as **Done** reverts back to **Draft** before saving a new version, resulting in the **Done** state not persisting in any document versions. (20006)
- Unable to add a PDF file as an image reference in a topic in the Web Editor. (21206)
- Selecting a DITA file in the Assets UI shows the **Open in FrameMaker** option, even when disabled in the configuration. (20082)

## Publishing

- In the Native PDF output, chapter titles are missing from the TOC, leading to an incorrect hierarchy. (21840)

 
## Management

- Resource leaks occur due to **Unclosed ResourceResolver** errors in logs. (18488)
- When creating a new or duplicate baseline, labels are displayed in a random order. (19307)


## Baseline

- Editing and then saving a baseline on a cloud setup timesout after 1 minute if the baseline has large number of topics or maps. (19558)

## Translation

- Map translation using baseline becomes slow and eventually fails to load the list of all the associated topics and maps files. (19733)

## Known issues with workaround

Adobe has identified the following known issues in the 2024.12.0 release of Adobe Experience Manager Guides as a Cloud Service.

**Project creation fails while processing content translation**  

While sending content for translation, the project creation fails with the following log errors:

`com.adobe.cq.wcm.translation.impl.TranslationPrepareResource` Error while processing Translation project

`com.adobe.cq.projects.api.ProjectException`: Unable to create the project

Caused by: `org.apache.jackrabbit.oak.api.CommitFailedException`: `OakAccess0000`: Access denied


**Workaround**: To resolve this issue, perform the following workaround steps:

1. Add a repoinit file. In case, the file does not exist, create the file by performing the [sample repoinit config creation steps](https://experienceleaguecommunities.adobe.com/t5/adobe-experience-cloud-questions/repoinit-configuration-for-property-set-on-aem-as-cloud-service/m-p/438854). 
2. Add the following line in the file and deploy the code:

    ```
    { "scripts": [ "set principal ACL for translation-job-service\n allow jcr:all on /home/users/system/cq:services/internal/translation\nend" ] }

    ```

3. Test the translation after deployment. 
 