---
title: Configure filenames
description: Learn how to disable postprocessing for a folder uploaded to Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: 42722c6f-1b1c-4a7e-89ef-a373623eb774
hidefromtoc: yes
---
# Disable postprocessing for a folder 

By default, all uploaded assets are processed using the DAM Update Asset workflow. Experience Manager Guides runs an additional processing, called postprocessing, as a part of this workflow. This also helps in generating the UUIDs

While uploading your files and folders to the *Adobe Experience Manager Assets* server, you can also disable the postprocessing and the generation of UUIDs. 

Use the instructions in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following (property) details to disable the postprocessing on a given path or ignore the postprocessing for a folder:

>[!NOTE]
>
> You can also use regular expressions (regex) to define rules that apply to multiple folders or an entire folder hierarchy. For more details, view the [Use regex to enable or disable post-processing](#use-regex-to-enable-or-disable-post-processing)section. 

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.config.ConfigManager`| `ignored.post.processing.paths`| String value to set any standard NODE_OPTIONS (multivalued property, strings with path that omit `/` at the end or regex) <br> **Default Value**: `/content/dam/projects/translation_output`|

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.config.ConfigManager`| `enabled.post.processing.paths`|String value to set any standard NODE_OPTIONS (multivalued property, strings with path that omit `/` at the end or regex) <br> **Default Value**: `/content/dam` |

## Rules to enable or disable postprocessing 

By default, postprocessing is done for every folder path under the Experience Manager DAM folder. Configurations are applied for any folder according to the following rules: 

* If the parent is ignored for postprocessing but the child folder is enabled, then the child and all its successors are considered enabled.
* If the parent is enabled for postprocessing but the child is ignored, then the child and all its successors are considered ignored.
* If the same folder path exists in both `ignored.post.processing.paths` and `enabled.post.processing.paths` configurations, then it's considered ignored for postprocessing.

## Use regex to enable or disable post-processing

Instead of specifying individual folder paths, you can use regular expressions (regex) to define rules that apply to multiple folders or entire folder hierarchies. 

Regex patterns are evaluated against the full asset path during post-processing.

When regular expressions (regex) are used to configure ignored and enabled post‑processing paths, AEM Guides evaluates both configurations against the asset path. If a path matches both an ignore rule and an enable rule, ignore rules always take precedence.

The following examples illustrate how regex-based ignore and enable rules are evaluated.

## Regex evaluation scenarios for post-processing

### Ignore parent hierarchy, enable specific folder

**Ignore regex**

`regex:/content/dam/lang-test/.*`

**Enable regex**

`regex:/content/dam/lang-test/.*/parent1`

In the above example, post-processing will be disabled for `/content/dam/lang-test/en/parent1`. 

Although the path matches the enable regex, it is already matched by the ignore regex. Ignore rules take precedence, so post-processing is not enabled.

### Ignore specific folder, enable broader hierarchy

**Ignore regex**

`regex:/content/dam/lang-test/.*/parent1`

**Enable regex**

`regex:/content/dam/lang-test/.*`

In the above example, post-processing will be disabled for `/content/dam/lang-test/en/parent1` and enabled for `/content/dam/lang-test/en/parent2`. 

The `parent1` path is explicitly ignored and remains disabled. Other folders that match only the enable regex are processed.

### Ignore parent folder, enable a child folder

**Ignore regex**

`regex:/content/dam/lang-test/.*/parent1`

**Enable regex**

`regex:/content/dam/lang-test/.*/parent1/child1`

In the above example, post-processing will be disabled for `/content/dam/lang-test/en/parent1` and `/content/dam/lang-test/en/parent1/child2` and enabled for `/content/dam/lang-test/en/parent1/child1`. 

The child folder explicitly enabled by regex is processed. Other child folders remain disabled because their parent path matches the ignore regex.

### Ignore specific child folder, enable parent hierarchy

**Ignore regex**

`regex:/content/dam/lang-test/.*/parent1/child1`

**Enable regex**

`regex:/content/dam/lang-test/.*/parent1`

In the above example, post-processing will be disabled for `/content/dam/lang-test/en/parent1/child1` and enabled for `/content/dam/lang-test/en/parent1` and `/content/dam/lang-test/en/parent1/child2`. 

Only the explicitly ignored child folder is skipped. The parent folder and other child folders are processed because they match the enable regex and do not match the ignore regex.

