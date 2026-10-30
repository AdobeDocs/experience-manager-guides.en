---
title: Enable new PDF engine
description: Learn how to enable the new PDF engine in Experience Manager Guides
feature: Web Editor Configuration
role: Admin
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
---

# Configure Native PDF engine v2

The new publishing engine for Native PDF i.e _Native PDF engine v2_ provides updated PDF rendering capabilities and fixes for _Native PDF engine v1_ issues.

>[!BEGINTABS] 
>[!TAB Cloud Service] 

Use the instructions given in [Configuration overrides](../install-conf-guide/download-install-config-override.md) to create the configuration file. In the configuration file, provide the following (property) details:

| PID | Property Key | Property Value |
|-----|--------------|----------------|
| `com.adobe.fmdita.publish.config.GuidesPublishConfiguratorService` | `guides.publish.config` | `{"PDF_ENGINE": "v2"}` <br> Default value: `v1`|

>[!TAB On-Premise] 


For On-Premise deployments, its availability depends on the AEM and Java versions.

The _Native PDF engine v2_ requires **Java 17 or later**.

- **AEM 6.5:** Native PDF Publishing engine v2 isn't supported because AEM 6.5 runs on Java 8.
- **AEM 6.5 LTS:** Native PDF Publishing engine v2 is enabled by default. No additional configuration is required.

If you prefer to switch back to the _Native PDF engine v2_ with AEM 6.5 LTS, then uninstall the PDF publisher package:
 `/crx/packmgr/index.jsp#/etc/packages/com.adobe.guides/pdf-publisher-package-3.0.0.zip` from the CRX Package Manager.

>[!ENDTABS] 

