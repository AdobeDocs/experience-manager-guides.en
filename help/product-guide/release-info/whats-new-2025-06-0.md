---
title: Release Notes | What's New in Adobe Experience Manager Guides 2025.06.0 release
description: Learn about the new and enhanced features in the 2025.06.0 release of Adobe Experience Manager Guides
role: Leader
exl-id: 48f27aa6-d870-4228-8e62-db81699a25f7
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

![](assets/download-map-dialog-new.png){width="300" align="left"}


## Enhanced `navref` handling in the Editor

The latest enhancements to the Editor improve the handling of `navref` elements in a DITA map. Now, when you add a `navref` element to a map, the **Select path** dialog opens, allowing you to easily choose the map references to include as navigation links in your map. Once added, the title of the added map is displayed in both Author view and Layout view, providing better visibility of the included navigation during authoring.  Additionally, the added `navref` element resolves automatically to display the referred map in the Editor.

For more details, view [Add navigation references](../user-guide/map-editor-other-features.md#add-navigation-references).

## Performance enhancements in AI Assistant

The release introduces enhancements to the AI Assistant backend engine, offering improved performance and greater stability. To enable this update and continue using AI Assistant Help:

- Update the `chat.url` configuration to reflect the new end point URL.
- Add a new environment variable `GUIDES_AI_SITE_ID` in Cloud Manager.

For details, view [Configure the AI Assistant](../cs-install-guide/conf-smart-suggestions.md).

