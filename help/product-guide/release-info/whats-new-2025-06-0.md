---
title: Release Notes | What's New in Adobe Experience Manager Guides 2025.06.0 release
description: Learn about the new and enhanced features in the 2025.06.0 release of Adobe Experience Manager Guides
role: Leader
exl-id: 48f27aa6-d870-4228-8e62-db81699a25f7
TQID: https://experienceleague.adobe.com/Lu9Ebb7OEpxiRmjkho1KnXiry5Kz5kDwfAYbXJD8-uI
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
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
---
# What's new in the 2025.06.0 release (June 2025)

This article covers the new and enhanced features introduced with the 2025.06.0 release of Adobe Experience Manager Guides as a Cloud Service.

For the list of issues fixed in this release, view [Fixed issues in the 2025.06.0 release](fixed-issues-2025-06-0.md).

Learn about [upgrade instructions for the 2025.06.0  release](../release-info/upgrade-instructions-2025-06-0.md).

## Session timeout prompt to prevent accidental content loss

A pop-up message now notifies you when your Adobe Experience Manager session expires and you are logged out due to inactivity. This message is triggered when you attempt to edit content in Experience Manager Guides after the session has ended. The feature helps reduce the risk of losing unsaved work and enhances the overall reliability and fluidity of the experience, even during periods of inactivity.

![](assets/sign-out-prompt.png)

Learn more about [session timeout prompt](../user-guide/session-timeout-prompt.md) in Experience Manager Guides. 

## Enhanced map download options in the Editor

Experience Manager Guides introduces a new **Use actual file names** option in the **Download map** dialog. Now, when you download map files, you can choose to keep their original filenames instead of default UUIDs, making it much easier to recognize and manage your files. This option is only available if you select **Retain file hierarchy** and is disabled when you choose **Flatten file hierarchy**, giving you more flexibility in organizing your downloaded maps.

For more details, view [Download files](../user-guide/authoring-download-assets.md#download-a-dita-map-file-from-the-editor).

![](assets/download-map-dialog-new.png){width="300"}


## Enhanced `navref` handling in the Editor

The latest enhancements to the Editor improve the handling of `navref` elements in a DITA map. Now, when you add a `navref` element to a map, the **Select path** dialog opens, allowing you to easily choose the map references to include as navigation links in your map. Once added, the title of the added map is displayed in both Author view and Layout view, providing better visibility of the included navigation during authoring.  Additionally, the added `navref` element resolves automatically to display the referred map in the Editor.

For more details, view [Add navigation references](../user-guide/map-editor-other-features.md#add-navigation-references).

## Performance enhancements in AI Assistant

The release introduces enhancements to the AI Assistant backend engine, offering improved performance and greater stability. To enable this update and continue using AI Assistant Help:

- Update the `chat.url` configuration to reflect the new end point URL.
- Add a new environment variable `GUIDES_AI_SITE_ID` in Cloud Manager.

For details, view [Configure the AI Assistant](../cs-install-guide/conf-smart-suggestions.md).

