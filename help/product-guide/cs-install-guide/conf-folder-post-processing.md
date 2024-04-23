---
title: Configure filenames
description: Learn how to disable postprocessing for a folder uploaded to Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
---

# Disable postprocessing for a folder 

By default, all uploaded assets are processed using the DAM Update Asset workflow. Experience Manager Guides runs an additional processing, called postprocessing, as a part of this workflow. This also helps in generating the UUIDs

While uploading your files and folders to the *Adobe Experience Manager Assets* server, you can also disable the postprocessing and the generation of UUIDs. 


Use the instructions in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following (property) details to disable the postprocessing on a given path or ignore the postprocessing for a folder:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.config.ConfigManager`| `ignored.post.processing.paths`| String value to set any standard NODE_OPTIONS (multivalued property, strings with path that omit `/` at the end) <br> **Default Value**: `/content/dam/projects/translation_output`|


|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.config.ConfigManager`| `enabled.post.processing.paths`|String value to set any standard NODE_OPTIONS (multivalued property, strings with path that omit `/` at the end) <br> **Default Value**: `/content/dam` |


## Rules to enable or disable postprocessing configurations

By default, postprocessing is done for every folder path under the Experience Manager DAM folder. Configurations are applied for any folder according to the following rules: 

* If the parent is ignored for postprocessing but the child folder is enabled, then the child and all its successors are considered enabled.
* If the parent is enabled for postprocessing but the child is ignored, then the child and all its successors are considered ignored.
* If the same folder path exists in both ignored.post.processing.paths and enabled.post.processing.paths configurations, then it's considered ignored for postprocessing.
