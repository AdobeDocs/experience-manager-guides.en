---
title: Configure paginated loading Explorer, Templates, and Collections
description: Learn how to configure enable or disable paginated loading Explorer, Templates, and Collections in AEM Guides.
feature: Web Editor Configuration
role: Admin
level: Experienced

---
# Enable paginated loading for Explorer, Templates, and Collections

Paginated loading allows content in the Left panel (Explorer/Repository, Collections, and Template) to load in smaller batches instead of all at once, improving performance when working with large files.

Use the instructions given in [Configuration overrides](download-install-config-override.md#) to create the configuration file. In the configuration file, provide the following (property) details to configure the **Enable Loadfiles Pagination** option:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`ENABLE_LOADFILES_PAGINATION`|Boolean \(true/false\). **Default value**: false |

>[!NOTE]
>
> This configuration is disabled by default and the option isn't available in the Editor.

**Parent topic:**[Customize Web Editor](customize-overview.md)
