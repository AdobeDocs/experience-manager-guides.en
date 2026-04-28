---
title: Configure B-tree clean up job for Cloud services
description: Configure B-tree clean up job for Cloud services
feature: Output Generation
role: Admin
level: Experienced
exl-id: de464e92-f17b-4c99-98f2-fdba8d214129
---
# Configure B-tree cleanup 

Set up the B-tree cleanup job and manage the `Guides BTree deletion` setting to keep your system optimized and storage clean.

## Configure B-tree cleanup job

Perform the following steps to configure B-tree clean up job:

1. Use the instructions given in [Configuration overrides](../cs-install-guide/download-install-additional-config-override.md) to create the configuration file.

1. In the configuration file, provide the following (property) details:

    |PID|Property Key|Property Value|
    |---|---|---|
    |`com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob`|`cronExpression`| **Default value:** "0 0 0 * * ?"|


## Configure Guides B-tree deletion enable setting

Perform the following steps to enable the setting:

1. Use the instructions given in [Configuration overrides](../cs-install-guide/download-install-additional-config-override.md) to create the configuration file.

1. In the configuration file, provide the following (property) details:

    |PID|Property Key|Property Value|
    |---|---|---|
    |`com.adobe.fmdita.config.ConfigManager`|`btree.deletion.enabled`| **Default value:** "True"|
