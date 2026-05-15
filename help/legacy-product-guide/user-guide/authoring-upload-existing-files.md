---
title: Upload files
description: Learn how to upload your files to the AEM repository and handle errors. Know assets console user interface, AEM desktop app, asset bulk ingestor, and use FrameMaker for bulk upload.
feature: Content Management
role: User
hide: true
exl-id: fcb2cc43-6a36-42f2-a695-7a50ae1031a0
TQID: https://experienceleague.adobe.com/Kcxzs3D9Vcp7hhgttmCx7jdetS8NWR8YTP85UY0DlJU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Upload files {#id176FF000JUI}

Most likely you would have a repository of existing DITA content that you would like to use with AEM Guides. For such existing content, you can use any of the following approaches to bulk upload your content into AEM repository:

>[!IMPORTANT]
>
> See [Add digital assets to Adobe Experience Manager as a Cloud Service Assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html) for detailed information in the supported content upload methods in AEM.

## Assets Console user interface 

You can select content on your desktop and drag on the AEM user interface \(web browser\) to the destination folder. For more details, see [Upload assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html#upload-assets) in AEM documentation.

## AEM desktop app 

Use AEM desktop app if you are a creative professional, and want to manage the assets on your local desktop. You can open and edit these assets with your desktop applications. You can also maintain versions and share your files with other users. For more details, see [AEM desktop app](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html).

## Asset bulk ingestor 

If you have large-scale migrations and occasional bulk ingestions, use Asset bulk ingestor to upload your content. Using this tool, you can upload bulk content from supported datastores like Azure or S3. For more details, see [Asset bulk ingestor](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/add-assets.html?lang=en#asset-bulk-ingestor).

## Use FrameMaker for bulk upload 

Adobe FrameMaker comes with a powerful AEM connector that allows you to easily upload your existing DITA and other FrameMaker documents \(`.book` and `.fm`\) into AEM. You can use various file upload functionalities such as uploading a single file, uploading a complete folder with or without dependencies \(like content references, cross-references, and graphics\).

For more details about using bulk upload feature in FrameMaker, see the section *Create a CRX folder and upload files* in FrameMaker User Guide.

## Error handling while uploading content {#id201MI0I04Y4}

In case of any failure to upload one or more files, a prompt is displayed at the end of the upload process with a list of files that failed to upload:

![](images/uuid-files-failed-to-upload_cs.png){width="650" align="center"}

For more details about how the various file uploading scenarios, see [Upload DITA content](authoring-file-management.md#).

 In case you use a tool like AEM desktop app or Asset bulk ingestor, then the action to perform on a duplicate file is controlled by a setting in the AEM server. Contact your system administrator to know about this configuration.

**Parent topic:**[Manage content](authoring.md)
