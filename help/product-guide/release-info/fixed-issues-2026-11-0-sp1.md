---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2026.11.0 Service Pack 1 release
description: Learn about the bug fixes in the 2026.11.0 Service Pack 1 release of Adobe Experience Manager Guides as a Cloud Service.
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Fixed issues in the 2026.11.0 Service Pack 1 release 

This article covers the bugs fixed in the 2026.11.0 Service Pack 1 release of Adobe Experience Manager Guides as a Cloud Service.

## Publishing

- When you regenerate selected topics or a sub-map using the AEM Sites (composite component mapping) output with `microservice-based` publishing, the generation takes about as long as generating the complete map. (GUIDES-59322)
- After you regenerate a sub-map that contains chunked topics using the new AEM Sites output, the table of contents (TOC) displays incorrect titles and links. Every chunked topic entry shows the title of the last chunked topic. (GUIDES-58650)
- When you publish to AEM Sites using a dynamic baseline, either Baseline (legacy) or New Baseline, the following issues occur: 
  - The baseline is rebuilt more than once during the same publish operation, which lengthens publishing time and, in some cases, causes the rebuild to stall. With New Baseline, incremental publish also uses a stale baseline instead of the current one, so the output may not reflect the latest content. (GUIDES-60189)
  - The Map dashboard shows performance issues. (GUIDES-60189, GUIDES-55646)

## Known issues

Adobe has identified the following known issues for the 2026.11.0 Service Pack 1 release:



