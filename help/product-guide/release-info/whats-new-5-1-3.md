---
title: Release Notes | What's New in Adobe Experience Manager Guides 5.1.0 Service Pack 3 release
description: Learn about the new and enhanced features in the 5.1.0 Service Pack 3 release of Adobe Experience Manager Guides
role: Leader
exl-id: 1b2e45a8-bea6-4b78-bd2e-cc02df86f40a
TQID: https://experienceleague.adobe.com/dXXQ1YvVduT11vvF5qyXHLqnuo1xMKkAb5I-EoD2JAA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
---
# What's new in the 5.1.0 Service Pack 3 release (December 2025)

This article covers the new and enhanced features introduced with version 5.1.0 Service Pack 3 of Adobe Experience Manager Guides.

For the list of issues that have been fixed in this release, view  [Fixed issues in the 5.1.0 Service Pack 3 release](fixed-issues-5-1-0-sp3.md).

Learn about [upgrade instructions for the 5.1.0 Service Pack 3 release](../release-info/upgrade-instructions-5-1-0-sp3.md).


## Configure custom image renditions for specific output presets

You can now configure different image renditions for individual output presets under the same output type by using the `outputName` attribute in `renditionmapping.xml`. This enhancement gives you greater flexibility when publishing content that requires varying image resolutions for different scenarios. For example, you might want a high-resolution image for your main HTML5 output while using a smaller thumbnail for a lightweight preset.

For more details, view [Handle image rendition in output generation](../install-guide/conf-output-generation.md#handle-image-rendition-during-output-generation).
