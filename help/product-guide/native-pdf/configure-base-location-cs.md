---
title: Native PDF | Configure Base Output Location for Publishing PDF for Cloud services
description: Configure Base Output Location for Publishing PDF for Cloud services
feature: Output Generation
role: Admin
level: Experienced
---
# Configure Base Output Location for publishing PDF

To configure the base output location for a Native PDF or DITA-OT PDF , perform the following steps:

1. Use the instructions given in [Configuration overrides](../cs-install-guide/download-install-additional-config-override.md) to create the configuration file.

1. In the configuration file, provide the following (property) details to configure the base output location:

    |PID|Property Key|Property Value|
    |---|---|---|
    |`com.adobe.fmdita.config.ConfigManager`|`base.output.path`| **Default value:** "/content/dam/fmdita-outputs"|
