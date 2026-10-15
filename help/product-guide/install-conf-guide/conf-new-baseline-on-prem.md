---
title: Configure New Baseline for On-premise
description: Learn how to enable or disable New Baseline for On-premise
feature: Configuration
role: Admin
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
---
# Configure New Baseline for On-Premise

>[!IMPORTANT]
>
> Deploy system configurations through code instead of applying them manually in the runtime environment.

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
>After enabling this feature, you must migrate existing baselines to the new baseline. For step-by-step instructions and a walkthrough video, view [New baseline in Experience Manager Guides](../user-guide/web-editor-baseline-v2.md).

