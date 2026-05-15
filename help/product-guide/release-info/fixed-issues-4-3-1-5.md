---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 4.3.1.5 release
description: Learn about the bug fixes in the  4.3.1.5 release of Adobe Experience Manager Guides
role: Leader
exl-id: 082dca28-15da-417c-b511-74eb5ac68078
TQID: https://experienceleague.adobe.com/ujQFyhAp5bIB1OJnmqvbHCaiDip7T2qsjlVAWevykK8
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
---
# Fixed issues in the 4.3.1.5 release 


This article covers the bugs fixed in various areas of 4.3.1.5 release of Adobe Experience Manager Guides.



Learn about [upgrade instructions for the 4.3.1.5 release](../release-info/upgrade-instructions-4-3-1-5.md).


## Authoring

- Adding spaces between inline elements within `<codeblock>` causes a line break in the generated output. (15247)
- Experience issues occur while adding elements from the "Insert Element" dialog box. (15108)

## Publishing

- Error logs display incorrect information on publishing content with external scopes. (15242)
- Internal links to DITA files that start with `HTTP` are treated like external links and cause scope errors. (15155)
- AEM Site regeneration fails for DITA maps. (14369)

## Management

- **fmditaTopicrefs** property shows relative paths instead of absolute paths. (15341)
