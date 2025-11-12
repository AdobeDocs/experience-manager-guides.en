---
title: Configure Asset processing for Cloud service
description: Learn how to configure Asset processing for Cloud service
feature: Output Generation
role: Admin
level: Experienced

---
# Configure asset processing feature 

To configure the asset processing feature perform the following steps:

1. Use the instructions given in [Configuration overrides](../cs-install-guide/download-install-additional-config-override.md) to create the configuration file.

1. In the configuration file, provide the following (property) details:

    |PID|Property Key|Property Value|
    |---|---|---|
    |`com.adobe.fmdita.config.ConfigManager`|`enable.asset.processing.scheduler`| **Default value:** "true"|
