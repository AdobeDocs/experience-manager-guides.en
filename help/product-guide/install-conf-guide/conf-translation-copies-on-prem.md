---
title: Configure destination copy initialization in translation workflow for On-Premise
description: Learn how to enable or disable initialization of destination copy in translation workflow for On-Premise
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
