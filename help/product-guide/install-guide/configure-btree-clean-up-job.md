---
title: Configure B-tree clean up job for On-Premise services
description: Configure B-tree clean up job for On-Premise services
feature: Output Generation
role: Admin
level: Experienced

---
# Configure B-tree clean up job for On-Premise services

Perform the following steps to configure B-tree clean up job:

1. Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1. Search for and select the *com.adobe.fmdita.config.ConfigManager* bundle.

1. Enable the setting **Guides btree deletion enabled**. 

1. Configure the B-tree clean up scheduler as shown below.

    ![](assets/btree-cleanup-config.png){align="left"}

1. Click **Save**.
