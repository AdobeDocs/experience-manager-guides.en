---
title: Non-UUID to UUID content migration
description: Learn how to migrate Non-UUID to UUID content
exl-id: f8b723bf-84c0-4fe6-936e-63970fb3e417
feature: Migration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/pZ0HRoSRWcGz2IT9tWAZ-vZYLc-Zc4kyYt8OXRohmTU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: b1210526-416b-4ef6-bcc0-1692e99f30e9
    internal-label: Administration and security
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: c8841798-1a28-4264-a46a-984860f8e6f6
    internal-label: User administration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Non-UUID to UUID content migration {#id226TI0U20XA}


You can migrate your non-UUID content to UUID based on the current version of Experience Manager Guides that you are using. 

>[!IMPORTANT]
>
> Before migrating content to the UUID server, ensure that you've a non-UUID server with compatible AEM Guides version  installed on it.

## Compatibility matrix

Use the following matrix to determine the correct migration path based on your current non-UUID version. This ensures a smooth transition post-migration.

|Non-UUID version required for migration|UUID version after migration | Supported upgrade path post-migration|
|---|---|---|
|4.3.1 non-UUID |  4.3.2 UUID|After migrating to version 4.3.2 UUID, you must directly install 4.6.0 (UUID). Once you are on 4.6.0, upgrade to version 5.1.0, and then install 5.1.0 Service Pack 3.|
|4.6.0 Service Pack 4 non-UUID|4.6.1 UUID |After migrating to version 4.6.1 UUID, you must directly upgrade to 5.1.0 (UUID). Once the upgrade is complete, install version 5.1.0 Service Pack 3.|

## Migration time estimation

The migration utility processes assets at an average rate of ~50 ms per asset. The following table provides migration time estimates for a system configured with 64 vCPUs, 128 GB RAM, and SSD-backed storage. Memory requirements may increase for larger repositories or assets with many renditions or high-resolution binaries.

>[!NOTE]
>
> Actual migration time can vary depending on hardware performance, storage throughput, concurrent AEM activities, and overall system load.


| **Asset Count** | **Approx. Time**        |
|-----------------|-------------------------|
| 10K             | ~8–9 minutes            |
| 50K             | ~42 minutes             |
| 100K            | ~1.4 hours              |
| 250K            | ~3.5 hours              |
| 500K            | ~7 hours                |
| 750K            | ~10.5 hours             |
| 1M              | ~14 hours               |
| 2M              | ~28 hours (~1.2 days)   |
| 3M              | ~42 hours (~1.75 days)  |
| 5M              | ~69 hours (~2.9 days)   |
| 10M             | ~139 hours (~5.8 days)  |


For detailed steps on migrating your content, refer to the following articles:

- [**4.3.1 non-UUID to 4.3.2 UUID content migration**](./migrate-non-uuid-4-3.md)
- [**4.6.0 Service Pack 4 non-UUID to 4.6.1 UUID content migration**](./migrate-non-uuid-uuid-4-6.md)



