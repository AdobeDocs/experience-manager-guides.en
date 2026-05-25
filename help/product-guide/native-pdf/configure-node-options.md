---
title: Native PDF | Configure Node process for Native PDF Publishing
description: Learn how to configure Node process for Native PDF Publishing
feature: Output Generation
role: Admin
level: Experienced
exl-id: f470939b-a5cb-4d28-92d1-7a0a52c4c637
TQID: https://experienceleague.adobe.com/7i-6SjvI5FuSNsWPy9sX96UsXld9fJjAjHNKDKzo824
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
    internal-label: Native PDF publishing
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Configure Node Process for Native PDF Publishing for Cloud Service

Native PDF publishing starts a separate NodeJs process to convert the files generated in the publishing process to a final PDF. You might have to tweak the configurations of this Node process running Native PDF publishing to support different scenarios. For example, to run larger workloads you should increase the maximum heap size available to the spawned NodeJs process.

Use the instructions given in [Configuration overrides](../install-conf-guide/download-install-config-override.md) to create the configuration file.In the configuration file, provide the following (property) details:

|PID|Property Key|Property Value|
|---|---|---|
|`com.adobe.fmdita.config.ConfigManager`|`native.pdf.node.opts`|String value to set any standard `NODE_OPTIONS`.<BR> Default value: ""|
