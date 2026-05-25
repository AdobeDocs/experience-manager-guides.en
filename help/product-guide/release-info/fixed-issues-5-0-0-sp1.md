---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 5.0.0 Service Pack 1 release
description: Learn about the bug fixes in the 5.0.0 Service Pack 1 release of Adobe Experience Manager Guides
role: Leader
exl-id: 1d0bc3d0-aedf-4f67-b6f7-2208facdee96
TQID: https://experienceleague.adobe.com/0qxye7ZUWt1iixHthjjTNJgtlOQX-C30jGi5zQlRJfA
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
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
---
# Fixed issues in the 5.0.0 Service Pack 1 release (June 2025)


This article covers the bugs fixed in various areas of 5.0.0 Service Pack 1 release of Adobe Experience Manager Guides.

Learn about [upgrade instructions for the 5.0.0 Service Pack 1 release](upgrade-instructions-5-0-0-sp1.md).

## Authoring

- When content is pasted into a `codeblock` or when spaces are added in the `codeblock` and the view is switched, the spacing is lost. (GUIDES-29347)
- When an XML comment is added within an element in the **Source** view, the leading and trailing spaces around the comment are lost upon switching views. (GUIDES- 28188)

## Asset Management

- When opening a topic in **Author** view after a browser refresh, previously applied tags in the **File Properties** panel are not retained, and adding new tags overwrites the existing ones, particularly when a large number of tags are available for selection. (GUIDES-29078)
- When generating a Metadata report for a DITA map containing a large number of assets, the **Manage** button becomes unresponsive or exhibit delayed response. (GUIDES-29778)

## Translation 

- When sending assets for translation from Experience Manager Guides, the assets are not added in the Translation job, which prevents the **Start** button from appearing and stops you from initiating the translation job. (GUIDES-28237)

## Publishing

- When modifying the settings of an output preset within the folder profile and selecting **Apply Preset Changes**, the changes are not propagated to the output presets present in the DITA map. (GUIDES-26694)

## Review

- Attempts to create review tasks through the AEM workflow consistently fails because the review node is not created. (GUIDES-28214)
