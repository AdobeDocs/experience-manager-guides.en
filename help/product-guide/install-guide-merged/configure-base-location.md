---
title: Native PDF | Configure Base Output Location for Publishing PDF for Cloud services
description: Configure Base Output Location for Publishing PDF for Cloud services
feature: Output Generation
role: Admin
level: Experienced

---
# Configure Base Output Location for publishing output

The following tabs provide instructions to configure the base output location based on your Experience Manager Guides setup: Cloud Service or On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Use the instructions given in [Configuration overrides](../cs-install-guide/download-install-additional-config-override.md) to create the configuration file.

1. In the configuration file, provide the following (property) details to configure the base output location:

    |PID|Property Key|Property Value|
    |---|---|---|
    |`com.adobe.fmdita.config.ConfigManager`|`base.output.path`| **Default value:** "/content/dam/fmdita-outputs"|

>[!TAB On-Premise]    

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and select the *com.adobe.fmdita.config.ConfigManager* bundle.

1.  Update the property **Base Output Location** to specify the default path in the AEM repository where the PDF will be saved after publishing. Additionally, if an invalid path is entered, it will automatically revert to the default path: /content/dam/fmdita-outputs.

1.  Click **Save**.

>[!ENDTABS]
