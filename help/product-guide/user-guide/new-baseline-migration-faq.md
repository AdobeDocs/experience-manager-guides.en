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

This FAQ addresses common questions related to Baseline V2 migration, behavior changes, migration considerations, and expected outcomes when upgrading to the new baseline model.

### Does baseline migration create V2 baselines for all versions of a map?

No. Baseline migration creates V2 baselines only for the **current working copy** of the map.

### What happens when a user reverts to a previous version of a map?

When a previous version of a map is restored or accessed, the baselines associated with that map version are automatically migrated to the new baseline model through an asynchronous migration job.

### Are invalid references migrated to the new baseline?

No. Invalid references are skipped during migration to ensure baseline consistency and reliability.

### Are reltable references included in the new baseline model?

No. References originating from **reltable** elements are excluded from baseline resolution, consistent with the behavior of the previous baseline model.

### How are DIRECT references handled in Baseline V2?

In the new baseline model, direct map references are explicitly classified as **DIRECT** references. During migration and baseline resolution, these references take precedence over other reference types.

### Are `scope="peer"` references included in the baseline?

No. References with `scope="peer"` are excluded from the baseline model. Skipping these references helps improve publishing performance and reduces unnecessary dependency resolution.

### Can baselines still be managed from the Map Dashboard?

No. Baseline management is supported only from the **Map Console** in Baseline V2.

Creating and managing baselines from the **Map Dashboard** is no longer supported.

### Is any precaution required during migration?

Yes. Avoid editing baselines while migration is in progress, especially in working copies. Performing baseline modifications during migration can result in migration failures or inconsistent baseline states.

### What happens if versions are missing after migration?

Some baselines may require rebuilding after migration if the versions referenced by the baseline are no longer available.

### What are the key benefits of migrating to the new baseline?

The Baseline V2 model provides several improvements, including:

- Improved performance and scalability
- Better UI and backend consistency
- Deterministic editing and saving behavior
- Enhanced filtering and navigation capabilities
- Dependency impact previews
- Improved reliability during baseline creation and updates
- Better API and automation support

### Will baseline migration change the baseline?

No. Baseline migration attempts to migrate the baseline **as-is** without modifying existing references or baseline content.

The references contained in the baseline remain unchanged during migration.

Changes to references or dependency resolution behavior occur only when the migrated baseline is:

- Edited
- Rebuilt
- Newly created using the Baseline V2 model

### What is the approximate time required to migrate baselines on on-premises servers?

Migration duration depends on several factors, including:

- Number of baselines
- Total number of references
- Repository size
- Hardware configuration
- Available system resources

Based on internal observations for repositories containing approximately **18,000+ references**:

| Migration Scope | Typical Duration |
|-----------------|------------------|
| Single baseline | A few seconds |
| 10–15 baselines | A few tens of seconds |
| 25–50 baselines | Approximately 1–2 minutes |

> These figures are indicative only and may vary depending on repository complexity, infrastructure capacity, and environmental conditions.