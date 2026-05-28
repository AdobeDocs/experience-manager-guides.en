---
title: Configure destination copy initialization in translation workflow for On-Premise
description: Learn how to enable or disable initialization of destination copy in translation workflow for On-Premise
feature: System Configuration
role: Admin
level: Experienced
---
# Configure destination copy initialization in translation workflow for On-Premise

The following steps explain how to enable the destination copy initialization in translation workflow for your On-Premise environment.

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and select the **com.adobe.fmdita.config.ConfigManager** bundle.

1.  Enable or disable the setting **Initialize destination language copy with source content** ( translation.workflow.propagate.source.content) as per your requirement. This setting is applicable only when the legacy translation workflow is disabled.

1.  Select **Save**.
