---
title: Configure New Baseline for On-premise
description: Learn how to enable or disable New Baseline for On-premise
feature: System Configuration
role: Admin
level: Experienced
---
# Configure New Baseline for On-Premise

>[!IMPORTANT]
>
> Deploy system configurations through code (for example, via your deployment pipeline) instead of applying them manually in the runtime environment.

The following steps explain how to enable the New Baseline in your On-Premise environment.

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and select the **com.adobe.fmdita.config.ConfigManager** bundle.

1.  Enable the setting **Enable faster Baseline (v2)**. You can also search with the exact setting name `enable.baseline.v2`. 

1.  Select **Save**.

>[!NOTE]
>
>After enabling this feature, you must migrate existing baselines to the new baseline. For step-by-step instructions and a walkthrough video, view [New baseline (Beta) in Experience Manager Guides](../user-guide/web-editor-baseline-v2.md).

