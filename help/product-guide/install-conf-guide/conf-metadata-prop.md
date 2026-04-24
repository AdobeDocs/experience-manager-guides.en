---
title: Configure the ignore list of metadata properties  
description: Learn how to configure ignore list for metadata properties in AEM Guides.
feature: Web Editor Configuration
role: Admin
level: Experienced

---
# Configure the ignore list of metadata properties 

When a file is edited, the current working copy of the file is compared with its latest document version. This comparison includes content changes and system-generated metadata changes. To prevent system-generated metadata updates from affecting the working copy indicator, you can configure an ignore list for metadata properties.

Use the instructions given in [Configuration overrides](download-install-config-override.md#) to create the configuration file. In the configuration file, provide the following (property) details to configure the **Ignore metadata property for dirty version** option:


|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`xmleditor.dirtychecker.ignoremetadata`|`<comma-separated list / array of metadata properties>` |

## Default metadata properties in the ignore list

AEM Guides includes a default set of metadata properties in the ignore list. You can modify this list to add or remove metadata properties as required.

* "jcr:mixinTypes",
* "jcr:primaryType",
* "jcr:frozenMixinTypes",
* "jcr:frozenPrimaryType",
* "jcr:frozenUuid",
* "jcr:uuid",
* "dam:extracted",
* "jcr:lastModified",
* "jcr:lastModifiedBy",
* "dc:modified",
* "dam:sha1",
* "dam:size",
* "guides:wordCount",
* "dam:scene7UploadTimeStamp",
* "dam:scene7LastModified"

Only the metadata properties that are not included in the ignore list are considered for marking a document's version dirty. 

**Parent topic:**[Customize Web Editor](customize-overview.md)
