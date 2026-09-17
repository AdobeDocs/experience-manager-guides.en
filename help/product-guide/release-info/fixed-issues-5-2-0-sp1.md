---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 5.1.0 Service Pack 1 release
description: Learn about the bug fixes in the 5.1.0 Service Pack 1 release of Adobe Experience Manager Guides
role: Leader
exl-id: 4b51085b-1f71-41e2-b0a9-88a12990fc97
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
# Fixed issues in the 5.1.0 Service Pack 1 release (October 2025)


This article covers the bugs fixed in various areas of 5.1.0 Service Pack 1 release of Adobe Experience Manager Guides.

Learn about [upgrade instructions for the 5.1.0 Service Pack 1 release](upgrade-instructions-5-1-0-sp1.md).


## Platform

- When migrating from non-UUID to UUID and upgrading to the latest version (5.0+), if you move referred images between folders and then revert the DITA files (where these images were referred) to previous versions, it results in broken image references. (GUIDES-34315)

## Publishing

- When publishing a DITA map using baseline on AEM Sites (with legacy component mapping), the map elements with the attribute `processing-role = resource-only` are also getting published. (GUIDES-34298)
