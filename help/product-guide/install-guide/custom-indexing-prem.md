---
title: Custom indexing deployment for On-premise setup
description: Learn how to custom index content for On-premise setup
feature: Web Editor Configuration
role: Admin
level: Experienced
---
# Reindexing for Markup Search and Replace feature

Reindexing is required to enable the **Markup Search and Replace** feature, which allows you to search and replace text across DITA XML and Markdown files in your AEM Guides environment.

## Reindexing

For on-premise setups, the index definition is included with the package. To enable the feature, you must reindex the content. 

Deploy the index `guidesAssetLucene` by setting the property `reindex=true (Boolean)` on the node: ` /oak:index/guidesAssetLucene` to reindex previously captured content. 

The reindexing process will continue until the system automatically changes this property back to false. You can monitor the progress of the reindexing operation in the system logs.