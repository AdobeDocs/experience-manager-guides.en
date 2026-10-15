---
title: Convert non-UUID  content without versions to UUID content
description: Learn how to migrate non-UUID content without versions.
exl-id: 44b5660d-9961-4463-9686-53085249fb05
feature: Migration
role: Admin
level: Experienced
hidefromtoc: 'yes'
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: 5be0fc8f-1cff-5c3e-bb92-2903a56a3de6
    internal-label: Migration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
---
# Migrate unversioned content

>[!IMPORTANT]
>
> You can choose this migration approach if you intend to ignore or not migrate the asset versions. 


1. Download and upload assets from the non-UUID instance to the UUID instance directly from the AEM Assets UI using Adobe tools like the AEM desktop app.

1. Ensure that you enable the DAM update asset workflow  and execute it on all the assets after importing the content for GUID creation.
