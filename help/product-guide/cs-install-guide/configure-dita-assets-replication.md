---
title: Configure DITA Assets Replication for Cloud service
description: Learn how to configure dita assets replication for Cloud service
feature: Output Generation
role: Admin
level: Experienced
exl-id: 1eafc6b2-2b85-486a-bb2c-0038fae1fef9
---
# Configure DITA assets replication

To configure the asset processing feature perform the following steps:

1. Use the instructions given in [Configuration overrides](../cs-install-guide/download-install-additional-config-override.md) to create the configuration file.

1. In the configuration file, provide the following (property) details:

    |PID|Property Key|Property Value|
    |---|---|---|
    |`com.adobe.fmdita.config.ConfigManager`|`publish.replicate`| **Default value:** "true"|
