---
title: Configure DITA Assets Replication
description: Learn how to configure dita assets replication
feature: Output Generation
role: Admin
level: Experienced
---
# Configure DITA assets replication

The following tabs provide instructions to configure DITA assets replication feature based on your Experience Manager Guides setup: Cloud Service or On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Use the instructions given in [Configuration overrides](../cs-install-guide/download-install-additional-config-override.md) to create the configuration file.

1. In the configuration file, provide the following (property) details:

    |PID|Property Key|Property Value|
    |---|---|---|
    |`com.adobe.fmdita.config.ConfigManager`|`publish.replicate`| **Default value:** "true"|

>[!TAB On-Premise]

1. Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1. Search for and select the *com.adobe.fmdita.config.ConfigManager* bundle.

1. Configure the setting `Replicate DITA assets` as per your requirement. By default, the setting is enabled.


    ![](assets/dita-assets-replication.png){width="350" align="left"}


1. Select **Save**.

>[!ENDTABS]
