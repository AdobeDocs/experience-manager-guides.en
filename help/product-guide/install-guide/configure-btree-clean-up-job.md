---
title: Configure B-tree clean up job for On-Premise services
description: Configure B-tree clean up job for On-Premise services
feature: Output Generation
role: Admin
level: Experienced
exl-id: ff6f968c-3440-4757-882a-676711ad05c3
TQID: https://experienceleague.adobe.com/qvOHGtHbgKS3xUv0pEXKTqeWblIDj8JKJwik8heXwPo
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Configure B-tree cleanup

Set up the B-tree cleanup job and manage the `Guides B-tree deletion` setting to keep your system optimized and storage clean.

## Configure B-tree cleanup job

Perform the following steps to configure B-tree clean up job:

1. Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1. Search for and select the *com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob* bundle.

1. Update the cron expression to set up the B-tree cleanup scheduler job run frequency.

1. Configure the B-tree clean up scheduler as shown below.

    ![](assets/btree-cleanup-config.png)

1. Select **Save**.


## Configure Guides B-tree deletion enable setting

Perform the following steps to enable the setting:

1. Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1. Search for and select the *com.adobe.fmdita.config.ConfigManager* bundle.
1. Enable the setting `Guides btree deletion enabled`.

    ![](assets/btree-cleanup-setting.png)

1. Select **Save**.
