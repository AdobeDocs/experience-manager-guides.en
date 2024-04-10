---
title: Configure filenames
description: Learn how to disable post-processing for a folder uploaded to Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
---

# Disable post-processing for a folder 

While uploading your files and folders to the *Adobe Experience Manager Assets* server, you can also disable post-processing and the generation of UUIDs. This can help multiple users quickly upload assets concurrently without interfering with each other. 


Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following (property) details to disable the post-processing or ignore the post-processing for a folder:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.config.ConfigManager`| `ignored.post.processing.paths`| String value to set any standard NODE_OPTIONS (multivalued property, strings with path which omit `/` at the end) <br> **Default Value**: `/content/dam/projects/translation_output`|


|PID|Property Key|Property Value|
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager`| `enabled.post.processing.paths`|	String value to set any standard NODE_OPTIONS (multivalued property, strings with path which omit `/` at the end) <br> **Default Value**: `/content/dam` |


## Order of precedence 

By default, post-processing is done for every folder path. The inherited permission from a higher parent is overridden by the permission applied on the immediate path or inherited from a lower parent for all its successors:

* If the parent is ignored for post-processing but the child folder is enabled, then the child and all its successors are considered enabled.
* If the parent is enabled for post-processing but the child is ignored, then the child and all its successors are considered ignored.
* If the same folder path exists in both ignored.post.processing.paths and enabled.post.processing.paths configurations, then it's considered ignored for post-processing.
