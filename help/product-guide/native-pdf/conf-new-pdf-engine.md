---
title: Enable new PDF engine 
description: Learn how to enable the new PDF engine in Experience Manager Guides
feature: Web Editor Configuration
role: Admin
level: Experienced

---

# Configure Native PDF engine v2

The new publishing engine for Native PDF i.e _Native PDF engine v2_ provides updated PDF rendering capabilities and fixes for _Native PDF engine v1_ issues.

Use the instructions given in [Configuration overrides](../install-conf-guide/download-install-config-override.md) to create the configuration file. In the configuration file, provide the following (property) details:

| PID | Property Key | Property Value |
|-----|--------------|----------------|
| `com.adobe.fmdita.publish.config.GuidesPublishConfiguratorService` | `guides.publish.config` | `{"PDF_ENGINE": "v2"}` <br> Default value: `v1`|