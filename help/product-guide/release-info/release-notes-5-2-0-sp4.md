---
title: Release Notes | Release notes of Adobe Experience Manager Guides 5.2.0 Service Pack 4 release
description: Learn about the upgarde process and bug fixes in the 5.2.0 Service Pack 4 release of Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
---
# Release notes for the 5.2.0 Service Pack 4 release (November 2026)

This article provides information about the upgrade instructions, Java SDK compatibility, fixed issues and known issues in the 5.2.0 Service Pack 4 release of Adobe Experience Manager Guides.

## Java SDK resources

Use the following resources when developing custom Java plugins or integrations with Experience Manager Guides. Ensure that the SDK version matches your installed Experience Manager Guides release. 

|Release|Java SDK version|Maven Central|Java API reference|
|---|---|---|----|
|5.2.0 Service Pack 4 (UUID)|5.2.2|[AEM Guides SDK API 5.2.2](https://central.sonatype.com/artifact/com.adobe.aem/aem-guides-sdk-api/5.2.2/)|[Javadoc 5.2.2](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api/latest/index.html)|

For more details, view [Configure and use the API JAR from Maven Central repository](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/api-reference/introduction).

## Upgrade to 5.2.0 Service Pack 4 release of Experience Manager Guides

Learn how to install the Experience Manager Guides 5.2.0 Service Pack 4 release.

>[!NOTE]
>
>This release is available for AEM 6.5 LTS only. The supported service pack is AEM 6.5 LTS Service Pack 2.

### Prerequisites

Before you start the Experience Manager Guides 5.2.0 Service Pack 4 upgrade process, ensure that you are using version 5.2.0 Service Pack 1.

### Upgrade process 5.2.0 Service Pack 4 release

1. Download the Experience Manager Guides package version 5.2.0 Service Pack 4.
1. Upload the package to your instance by using Package Manager (`/crx/packmgr`).
1. Install the package. Then verify that the `fmdita` bundles have returned to the **Active** state. You can check the bundle state at `/system/console/bundles`.
1. Clear your browser cache.

## Fixed issues

The bugs fixed in various areas are listed below:

### Authoring

- When you drag and drop an asset into a map from Explorer panel that has not been refreshed after another author moved that asset, a broken reference is added to the map. (GUIDES-57869)

### Asset management

- When you overwrite an existing non-DITA asset, such as an image, using the **Overwrite existing files** option, the new version for uploaded image is not created. As a result, output generated using baseline contains the older asset. (GUIDES-59287)

- When a non-DITA asset, such as an image, that was migrated from a non-UUID setup to a UUID setup is reverted or branched to another version, its UUID changes. Existing references to the asset no longer resolve, and the image appears broken in the topics that reference it. (GUIDES-58414)

### Publishing

- When publishing a map while other maps are being exported, the output intermittently uses a lower-quality image format instead of the original vector image. (GUIDES-55221)

## Known issues

Adobe has identified the following known issue in the 5.2.0 Service Pack 4 release:

- When you drag and drop an element at an invalid location, the Editor moves it to the nearest valid position, during which the reference may retain its repository path. Similarly, when you replace an existing reference in a DITA map using drag and drop, the new reference may retain its repository path. (GUIDES-60688)