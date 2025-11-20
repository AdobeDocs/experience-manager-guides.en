---
title: Non-UUID to UUID content migration
description: Learn how to migrate Non-UUID to UUID content
exl-id: f8b723bf-84c0-4fe6-936e-63970fb3e417
feature: Migration
role: Admin
level: Experienced
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
|4.3.1 non-UUID |  4.3.2 UUID|After migrating to version 4.3.2 UUID, you can directly install 4.6.0 (UUID). Once you are on 4.6.0, upgrade to version 5.1.0, and then install 5.1.0 Service Pack 1.|
|4.6.0 Service Pack 4 non-UUID|4.6.1 UUID |After migrating to version 4.6.1 UUID, you can directly upgrade to 5.1.0 (UUID). Once the upgrade is complete, install version 5.1.0 Service Pack 1.|

For detailed steps on migrating your content, refer to the following articles:

- [**4.3.1 non-UUID to 4.3.2 UUID content migration**](./migrate-non-uuid-4-3.md)
- [**4.6.0 Service Pack 4 non-UUID to 4.6.1 UUID content migration**](./migrate-non-uuid-uuid-4-6.md)



