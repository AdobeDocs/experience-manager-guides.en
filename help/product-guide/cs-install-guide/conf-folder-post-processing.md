---
title: Configure filenames
description: Learn how to disable postprocessing for a folder uploaded to Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: 42722c6f-1b1c-4a7e-89ef-a373623eb774
---
# Disable postprocessing for a folder 

By default, all uploaded assets are processed using the DAM Update Asset workflow. Experience Manager Guides runs an additional processing, called postprocessing, as a part of this workflow. This also helps in generating the UUIDs

While uploading your files and folders to the *Adobe Experience Manager Assets* server, you can also disable the postprocessing and the generation of UUIDs. 

## Configure folder paths or regex to disable post-processing

You can disable post-processing for one or more folders by configuring exact folder paths or regular expressions (regex). Use regex when you want a single rule to apply to multiple folders or an entire folder hierarchy.

Use the instructions in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following (property) details:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.config.ConfigManager`| `ignored.post.processing.paths`| String value to set any standard NODE_OPTIONS (multivalued property, strings with path that omit `/` at the end) <br> **Default Value**: `/content/dam/projects/translation_output`|

**Disable post-processing using regex**

To ignore multiple folders and subfolders using a single rule, prefix the value with regex:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.config.ConfigManager`| `ignored.post.processing.paths`| String value to set any standard NODE_OPTIONS (multivalued property, strings with path that omit `/` at the end or regex with prefix `regex:`) <br> **Default Value**: `/content/dam/projects/translation_output` <br> Regex example: `regex:/content/dam/test/.*`|

>[!IMPORTANT]
>
> When regex is used for ignored paths, the rule applies hierarchically:
>
> * If a parent folder matches the ignore regex, all child folders are also ignored for post-processing.
> * A child folder cannot be enabled for post-processing if its parent folder already matches an ignore regex.

## Configure folder paths or regex to enable post-processing

By default, post-processing is enabled for all content under /content/dam. You can explicitly enable post-processing for specific folders by configuring exact paths or regex patterns.

Use the instructions in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following (property) details:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.config.ConfigManager`| `enabled.post.processing.paths`|String value to set any standard NODE_OPTIONS (multivalued property, strings with path that omit `/` at the end) <br> **Default Value**: `/content/dam` |

**Enable post-processing using regex**

Use regex to enable post-processing for multiple folders or folder hierarchies with a single rule.

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.config.ConfigManager`| `ignored.post.processing.paths`| String value to set any standard NODE_OPTIONS (multivalued property, strings with path that omit `/` at the end or regex with prefix `regex:`) <br> **Default Value**: `/content/dam/` <br> Regex example: `regex:/content/dam/test/.*`|

>[!NOTE]
>
> Enable rules defined using regex are evaluated against the asset path. If a matching parent folder is ignored using regex, the enable rule is not applied.

## Rules to enable or disable postprocessing 

By default, postprocessing is done for every folder path under the Experience Manager DAM folder. Configurations are applied for any folder according to the following rules: 

* If the parent is ignored for postprocessing but the child folder is enabled, then the child and all its successors are considered enabled.
* If the parent is enabled for postprocessing but the child is ignored, then the child and all its successors are considered ignored.
* If the same folder path exists in both ignored.post.processing.paths and enabled.post.processing.paths configurations, then it's considered ignored for postprocessing.

