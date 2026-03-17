---
title: Configure DITA Assets Replication for On-Premise services
description: Learn how to configure dita assets replication for On-Premise services
feature: Output Generation
role: Admin
level: Experienced
exl-id: 49fd9dfe-e1a5-4388-abbd-ec5d45669b45
---
# Configure DITA assets replication

Perform the following steps to configure the asset processing feature:

1. Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1. Search for and select the *com.adobe.fmdita.config.ConfigManager* bundle.

1. Configure the setting `Replicate DITA assets` as per your requirement. By default, the setting is enabled.


    ![](assets/dita-assets-replication.png){width="350" align="left"}


1. Select **Save**.
