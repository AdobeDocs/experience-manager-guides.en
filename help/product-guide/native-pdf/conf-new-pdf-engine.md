---
title: Enable new PDF engine 
description: Learn how to enable the new PDF engine in Experience Manager Guides
feature: Web Editor Configuration
role: Admin
level: Experienced
---

# Configure Native PDF engine v2

The new publishing engine for Native PDF i.e _Native PDF engine v2_ provides updated PDF rendering capabilities and fixes for _Native PDF engine v1_ issues.

>[!BEGINTABS] 
>[!Cloud Service Android] 

Use the instructions given in [Configuration overrides](../install-conf-guide/download-install-config-override.md) to create the configuration file. In the configuration file, provide the following (property) details:

| PID | Property Key | Property Value |
|-----|--------------|----------------|
| `com.adobe.fmdita.publish.config.GuidesPublishConfiguratorService` | `guides.publish.config` | `{"PDF_ENGINE": "v2"}` <br> Default value: `v1`|

>[!On-Premise Android] 


For On-Premise deployments, its availability depends on the AEM and Java versions.

The _Native PDF engine v2_ requires **Java 17 or later**.

- **AEM 6.5:** Native PDF Publishing engine v2 isn't supported because AEM 6.5 runs on Java 8.
- **AEM 6.5 LTS:** Native PDF Publishing engine v2 is enabled by default. No additional configuration is required.

If you prefer to switch back to the _Native PDF engine v2_ with AEM 6.5 LTS, then uninstall the PDF publisher package:
 `/crx/packmgr/index.jsp#/etc/packages/com.adobe.guides/pdf-publisher-package-3.0.0.zip` from the CRX Package Manager.

>[!ENDTABS] 

