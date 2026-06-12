---
title: Enable new PDF engine 
description: Learn how to enable the new PDF engine in Experience Manager Guides
feature: Web Editor Configuration
role: Admin
level: Experienced

---

# Configure the new publishing engine for Native PDF

The new publishing engine for Native PDF provides updated PDF rendering capabilities, support for OpenType fonts, and improved CSS processing.

Use the instructions given in Configuration overrides to create the configuration file.In the configuration file, provide the following (property) details:

| PID | Property Key | Property Value |
|-----|--------------|----------------|
| `com.adobe.fmdita.publish.config.GuidesPublishConfiguratorService` | `guides.publish.config` | `{"PDF_ENGINE": "v2"}` |