---
title: Native PDF | Configure JVM flags for Native PDF Publishing
description: Configure JVM flags for Native PDF Publishing
feature: Output Generation
role: Admin
level: Experienced
exl-id: a2a9f44c-cb17-4423-a66e-499bce921398
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
---
# Configure JVM flags for Native PDF Publishing for On-Premise

Native PDF publishing starts a separate JVM process to generate a PDF. You might have to tweak the configurations of this JVM to support different scenarios. For example, to run larger workloads you should increase the maximum heap size available to the spawned JVM process.

Perform the following steps to configure AEM Guides Native PDF Publishing JVM flags:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and select the *com.adobe.fmdita.config.ConfigManager* bundle.

1.  Update the property **Java Command line options for native pdf** (*native.pdf.java.opts*) to pass any standard JVM flags.



1.  Click **Save**.
