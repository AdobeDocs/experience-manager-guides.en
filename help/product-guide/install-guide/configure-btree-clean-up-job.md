---
title: Configure B-tree clean up job for On-Premise services
description: Configure B-tree clean up job for On-Premise services
feature: Output Generation
role: Admin
level: Experienced

---
# Configure B-tree clean up for On-Premise Service

Set up the B-tree cleanup job and manage the `Guides B-tree deletion` setting to keep your system optimized and storage clean.

## Configure B-tree clean up job

Perform the following steps to configure B-tree clean up job:

1. Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1. Search for and select the *com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob* bundle.

1. Update the cron expression to set up the B-tree cleanup scheduler job run frequency.

1. Configure the B-tree clean up scheduler as shown below.

    ![](assets/btree-cleanup-config.png){align="left"}

1. Select **Save**.


## Configure Guides B-tree deletion enable setting

Perform the following steps to enable the setting:

1. Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1. Search for and select the *com.adobe.fmdita.config.ConfigManager* bundle.
1. Enable the setting **Guides btree deletion enabled**.

    ![](assets/btree-cleanup-setting.png){align="left"}

1. Select **Save**.
   
