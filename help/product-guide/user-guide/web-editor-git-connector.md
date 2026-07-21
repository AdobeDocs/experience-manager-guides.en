---
title: Git Connector overview in Experience Manager Guides 
description: Learn what Git Connector in Experience Manager Guides does, its key features, and how content moves from a Git repository into your AEM Guides workflow.
feature: Authoring, Features of Web Editor
role: User
TQID: https://experienceleague.adobe.com/DDAXW8cUFjvHUeJIbtL6FaHYSU7NW5fkzTai-7n90ms
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
    internal-label: Document state
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
    internal-label: Web Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
---
# Overview

Git Connector allows you to [import content from connected Git repositories into Experience Manager Guides](./web-editor-git-connector-import.md). After the content is imported, you can use Experience Manager Guides authoring, review, translation, and publishing features to develop and deliver documentation.

When content changes in the source repository, you can refetch updates, review conflicts, and synchronize the latest changes with Experience Manager Guides.

## Key features

Git Connector allows authors to pull content directly from a Git repository into Experience Manager Guides, without manual file transfers. Once configured, authors have access to the following capabilities.

**Content ingestion**

- Synchronizes files from any Git repository (public or private) into Experience Manager Guides.
- Filters by source folder path to ingest a single subdirectory instead of an entire repository.
- Uses a `gitignore-aware` rule engine to automatically skip files excluded by `.gitignore` patterns or custom rules.
- Preserves GUIDs on re-sync to keep existing DITA cross-references intact after an update.

**Incremental (delta) sync**

- Tracks the last-synced commit and fetches only files that were added, modified, or deleted on subsequent syncs, instead of re-importing the entire repository.
- Produces a delta report listing every changed file and its change type before you import.
- Maintains consistent fetch times regardless of repository size. For benchmark data, view [Performance benchmarks](#performance-benchmarks).

## How Git Connector works

The following diagram shows how Git Connector moves content from a source repository into Experience Manager Guides through the Konnect framework.

![](./images/git-connector-arch.png)

Git Connector moves content from a Git repository into Experience Manager Guides in four stages:

1. **Crawl and sync**: A crawler connects to your configured Git repository and profile, and syncs content into the connector on demand.
1. **Ingest and detect conflicts**: Incoming files are scanned and hashed against what's already in Experience Manager Guides. Files with no conflicting changes move through automatically; files with conflicting changes are flagged for manual resolution.
1. **Persist**: Resolved content is processed and saved into AEM, alongside your other Experience Manager Guides content.
1. **Experience Manager Guides workflow**: Once persisted, the content is available like any other Experience Manager Guides content for authoring, review, translation, and publishing.

## Performance benchmarks

The following benchmarks show full (non-incremental) **Bulk Importer** sync times on Experience Manager as a Cloud Service, at increasing repository scale.

| Scale | Fetch time | Import time | Total time | Batches | Throughput |
|---|---|---|---|---|---|
| 1,000 files | 1m 53s | 3m 30s | 5m 29s | 10 × 100 | ~286 files/min |
| 5,000 files | 1m 55s | 18m 21s | 20m 27s | 20 × 250 | ~273 files/min |
| 10,000 files | 1m 39s | 36m 22s | 37m 24s | 40 × 250 | ~267 files/min |
| 50,000 files | 1m 25s | 2h 43m | 2h 58m | 200 × 250 | ~270 files/min |

