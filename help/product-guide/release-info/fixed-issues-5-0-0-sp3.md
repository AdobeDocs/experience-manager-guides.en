---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 5.0.0 Service Pack 3 release
description: Learn about the bug fixes in the 5.0.0 Service Pack 3 release of Adobe Experience Manager Guides
role: Leader
exl-id: ba915d58-4de8-4c4f-b338-29b64451d60d
TQID: https://experienceleague.adobe.com/qENxN8e84lkLpfHhXwIDcAGINdcqqs4eOZhpiV3DKxA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
---
# Fixed issues in the 5.0.0 Service Pack 3 release (February 2026)


This article covers the bugs fixed in various areas of 5.0.0 Service Pack 3 release of Adobe Experience Manager Guides.

Learn about [upgrade instructions for the 5.0.0 Service Pack 3 release](upgrade-instructions-5-0-0-sp3.md).

## Translation

- When an image initially managed as a language‑specific asset with a specific version (for example, under `/en/`) is moved out to a global folder with an updated version and baseline export is performed, the new baseline continues to reference outdated language‑specific versions of that image, leading to a failed baseline export. (GUIDES-39394)
