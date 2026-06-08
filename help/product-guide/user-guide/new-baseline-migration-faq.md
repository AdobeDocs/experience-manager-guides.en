---
title: FAQ about new baseline migration in Adobe Experience Manager Guides
description: Learn about the frequently asked questions on new baseline migration in Adobe Experience Manager Guides.
TQID: https://experienceleague.adobe.com/hsiglBlwA8KOqUkkDck1RZb307TBuHfoVFb64DKTcXk
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
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: c38bc65b-dea9-4a6e-9de3-3daf1d2b388b
    internal-label: Bulk activation
  - id: f6b497f1-f8e0-42ce-8e95-56c28d94026e
    internal-label: Conditional content
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
    internal-label: Map console
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
---
# New Baseline migration FAQ

## Overview

This FAQ addresses common questions related to New Baseline  migration, behavior changes, migration considerations, and expected outcomes when upgrading to the New Baseline model.

### Does baseline migration create new baselines for all versions of a map?

No, the migration process creates new baselines only for the **current working copy** of the map. Baselines associated with other working copies are not included in the migration.

### What happens when a user reverts to a previous version of a map?

When a previous version of a map is restored or accessed, the baselines associated with that version are automatically migrated to the new baseline model by an asynchronous migration process.

### Are invalid references migrated to the new baseline?

No, invalid references are skipped during migration to maintain baseline consistency and ensure the reliability of the migrated baseline.

### Are reltable references included in the new baseline model?

No, references originating from **reltable** elements are excluded from baseline resolution, consistent with the behavior of the legacy baseline model.

### How are DIRECT references handled in New Baseline?

In the New Baseline model, the direct map references are explicitly classified as **DIRECT** references. During migration and baseline resolution, these references are given the highest precedence and are resolved before all other reference types.

### Are `scope="peer"` references included in the baseline?

No, references with `scope="peer"` are not included in the baseline model. Excluding these references improves publishing performance and avoids unnecessary dependency resolution.

### Can baselines still be managed from the Map Dashboard?

No, the baseline management is supported only from the **Map Console** in New Baseline.Creating and managing baselines from the **Map Dashboard** is not supported.

### Is any precaution required during migration?

Yes, baseline modifications should be avoided while a migration is in progress, particularly in working copies. Making changes to baselines during migration can lead to migration failures and may leave baselines in an inconsistent state.

### What happens if versions are missing after migration?

Some baselines may need to be rebuilt after migration if the versions referenced by those baselines are no longer available or accessible.

### What are the key benefits of migrating to the new baseline?

The New Baseline model provides several improvements, including:

- Improved performance and scalability
- Better UI and backend consistency
- Deterministic editing and saving behavior
- Enhanced filtering and navigation capabilities
- Dependency impact previews
- Improved reliability during baseline creation and updates
- Better API and automation support

### Does baseline migration change the baseline?

No, baseline migration preserves the baseline exactly as it exists and does not modify its content or references.

All references contained in the baseline remain unchanged throughout the migration process.

Updates to references or dependency resolution behavior occur only after the migrated baseline is:

- Edited
- Rebuilt
- Newly created using the New Baseline model

Until one of these actions is performed, the migrated baseline continues to reflect the original baseline definition.

### What is the approximate time required to migrate baselines for an On-Premise setup?

Migration time depends on several factors, including:

- The number of baselines being migrated
- The total number of references across those baselines
- Repository size and complexity
- Hardware configuration
- Available system resources

Based on internal testing and observations from repositories containing approximately 18,000 references, migration duration can vary significantly depending on the repository structure and operating environment.

| Migration Scope | Typical Duration |
|-----------------|------------------|
| Single baseline | A few seconds |
| 10–15 baselines | A few tens of seconds |
| 25–50 baselines | Approximately 1–2 minutes |

>[!INFO]
>
>These figures are indicative only and may vary depending on repository complexity, infrastructure capacity, and environmental conditions.