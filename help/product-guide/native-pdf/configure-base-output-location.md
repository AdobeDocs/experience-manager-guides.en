---
title: Configure Base Output Location for Publishing Output for On-Premise services
description: Configure Base Output Location for Publishing Output for On-Premise services
feature: Output Generation
role: Admin
level: Experienced
exl-id: ae1d805a-7b79-4b76-8be2-a19c5552530c
---
# Configure Base Output Location for publishing output for On-Premise services

Perform the following steps to configure the base output location:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and select the *com.adobe.fmdita.config.ConfigManager* bundle.

1.  Update the property **Base Output Location** to specify the default path in the AEM repository where the PDF will be saved after publishing. Additionally, if an invalid path is entered, it will automatically revert to the default path: /content/dam/fmdita-outputs.

1.  Click **Save**.
