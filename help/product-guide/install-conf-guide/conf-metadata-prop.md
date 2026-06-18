---
title: Configure the ignore list of metadata properties  
description: Learn how to configure ignore list for metadata properties in AEM Guides.
feature: Web Editor Configuration
role: Admin
level: Experienced

---
# Configure the ignore list of metadata properties 

When a file is edited, any changes to the metadata fields available under **File properties** or applied at the backend trigger the asterisk (*) on the document version. To prevent system-generated metadata updates from affecting this indicator, administrators can configure an ignore list for metadata properties.

>[!BEGINTABS]

>[!TAB Cloud Service]

Use the instructions given in [Configuration overrides](download-install-config-override.md#) to create the configuration file. In the configuration file, provide the following (property) details to configure the **Ignore metadata property for dirty version** option.


|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`xmleditor.dirtychecker.ignoremetadata`|`<comma-separated list / array of metadata properties>` |

>[!TAB On-Premise]

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundle.

1.  In the *XmlEditorConfig* settings, navigate to **Ignore metadata property for dirty version** option. 
 
    Review the list of default metadata properties currently configured to be ignored.

1. Add or remove metadata properties as per the requirements. 
1. Select **Save** to save the updated configuration. 


>[!ENDTABS]

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

**Parent topic:**[Customize Editor](customize-overview.md)
