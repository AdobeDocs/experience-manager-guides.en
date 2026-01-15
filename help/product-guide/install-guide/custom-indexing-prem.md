---
title: Custom indexing deployment for On-premise setup
description: Learn how to custom index content for On-premise setup
feature: Web Editor Configuration
role: Admin
level: Experienced
---
# Reindexing for Find and replace feature

Reindexing is required to enable the **Find and replace (Source view)** feature,  which allows you to scan the entire content visible in the Author view and also the underlying Source content (XML structure, including elements, tags, and attribute values) for the searched string.

## Reindexing

For on-premise setups, the index definition is included with the package. To enable the feature, you must reindex the content. 

Start reindexing by setting the property `reindex=true (Boolean)` on the node: ` /oak:index/guidesAssetLucene` to reindex previously captured content. 

The reindexing process will continue until the system automatically changes this property back to false. You can monitor the progress of the reindexing operation in the system logs.