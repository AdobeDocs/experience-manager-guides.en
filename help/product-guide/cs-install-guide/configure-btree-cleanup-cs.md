---
title: Configure B-tree clean up job for Cloud services
description: Configure B-tree clean up job for Cloud services
feature: Output Generation
role: Admin
level: Experienced

---
# Configure B-tree clean up for Cloud Service

Set up the B-tree cleanup job and manage the enable/disable settings for Guides BTree deletion to keep your system optimized and the storage clean.

## Configure B-tree clean up job

Perform the following steps to configure B-tree clean up job:

1. Use the instructions given in [Configuration overrides](../cs-install-guide/download-install-additional-config-override.md) to create the configuration file.

1. In the configuration file, provide the following (property) details:

    |PID|Property Key|Property Value|
    |---|---|---|
    |`com.adobe.guides.utils.schedulers.GuidesBTreesCleanupSchedulerJob`|`cronExpression`| **Default value:** "0 0 0 * * ?"|


## Configure Guides BTree Deletion Enable setting

Perform the following steps to enable or disable the deletion setting:

1. Use the instructions given in [Configuration overrides](../cs-install-guide/download-install-additional-config-override.md) to create the configuration file.

1. In the configuration file, provide the following (property) details:

    |PID|Property Key|Property Value|
    |---|---|---|
    |`com.adobe.fmdita.config.ConfigManager`|`btree.deletion.enabled`| **Default value:** "True"|