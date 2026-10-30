---
title: Custom indexing deployment for On-premise setup
description: Learn how to custom index content for On-premise setup
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 87c0519d-120a-4bb7-b70f-7d217bcd7580
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
---
# Reindexing for Find and replace (Source view) feature for On-Premise

Reindexing is required to enable the **Find and replace (Source view)** feature,  which allows you to scan the entire content visible in the Author view and also the underlying Source content (XML structure, including elements, tags, and attribute values) for the searched string.

## Reindexing

For on-premise setups, the index definition is included with the package. To enable the feature, you must reindex the content. 

Start reindexing by setting the property `reindex=true (Boolean)` on the node: ` /oak:index/guidesAssetLucene` to reindex previously captured content. 

The reindexing process will continue until the system automatically changes this property back to false. You can monitor the progress of the reindexing operation in the system logs.
