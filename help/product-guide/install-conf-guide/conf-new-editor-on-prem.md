---
title: Configure New Editor
description: Learn how to enable or disable New Editor
feature: System Configuration
role: Admin
level: Experienced
---
# Configure New Editor for On-Premise 

>[!IMPORTANT]
>
> Deploy system configurations through code (for example, via your deployment pipeline) instead of applying them manually in the runtime environment.

The following steps explain how to enable the New Editor in your On-Premise environment.

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and select the **com.adobe.fmdita.config.ConfigManager** bundle.

1.  Enable the setting **Enable Editor 2.0** (`enable.markup.editor`).  

1.  Select **Save**.

