---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 5.2.0 Service Pack 4 release
description: Learn about the bug fixes in the 5.2.0 Service Pack 4 release of Adobe Experience Manager Guides
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
# Fixed issues in the 5.2.0 Service Pack 4 release (November 2026)

This article covers the bugs fixed in various areas of 5.2.0 Service Pack 4 release of Adobe Experience Manager Guides.

Learn about [upgrade instructions for the 5.2.0 Service Pack 4 release](upgrade-instructions-5-2-0-sp4.md).

## Editor 2.0

- When you drag and drop an asset into a map from Explorer panel that has not been refreshed after another author moved that asset, a broken reference is added to the map. (GUIDES-57869)

## Asset management

- When you overwrite an existing non-DITA asset, such as an image, using the **Overwrite existing file(s)** option, the new version in the version history retains the previous file so the output generated from a baseline that references that version shows the older image. (GUIDES-59287)

- When a non-DITA asset, such as an image, that was migrated from a non-UUID setup to a UUID setup is reverted or branched to another version, its UUID changes. Existing references to the asset no longer resolve, and the image appears broken in the topics that reference it. (GUIDES-58414)

## Publishing

- Publishing a map while other maps are being exported, the output intermittently uses a lower-quality SVG image instead of the original vector image. (GUIDES-55221)