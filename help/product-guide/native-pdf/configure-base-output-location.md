---
title: Native PDF | Configure Base Output Location for Publishing PDF
description: Configure Base Output Location for Publishing PDF
feature: Output Generation
role: Admin
level: Experienced
---
# Configure Base Output Location for publishing PDF

Perform the following steps to configure the base output location for a Native PDF or DITA-OT PDF preset:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and select the *com.adobe.fmdita.config.ConfigManager* bundle.

1.  Update the property **Base Output Location** to specify the default path in the AEM repository where the PDF will be saved after publishing. Additionally, if an invalid path is entered, it will automatically revert to the default path: /content/dam/fmdita-outputs.

1.  Click **Save**.


