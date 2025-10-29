---
title: Configure Asset processing for Cloud services
description: Learn how to configure Asset processing for Cloud services
feature: Output Generation
role: Admin
level: Experienced

---
# Configure Asset processing feature for Cloud services

To configure the asset processing feature perform the following steps:

1. Use the instructions given in [Configuration overrides](../cs-install-guide/download-install-additional-config-override.md) to create the configuration file.

1. In the configuration file, provide the following (property) details to configure the base output location:

    |PID|Property Key|Property Value|
    |---|---|---|
    |`com.adobe.fmdita.config.ConfigManager`|`enable.asset.processing.scheduler`| **Default value:** "true"|
