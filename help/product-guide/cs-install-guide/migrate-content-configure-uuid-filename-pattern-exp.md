---
title: Configure UUID filename pattern
description: Learn how to configure UUID filename pattern
feature: Migration
role: Admin
level: Experienced

---
# Configure UUID filename pattern

When you import content, it is not necessary that your file names will be based on the UUID. In a system that uses UUID-based file names, it is mandatory that all files are referred using their UUIDs rather than their original file names. If an imported file doesn't have UUID-based file names, you can configure the system to add a UUID to their file property. This UUID is then used to refer such files where UUID is not used for naming the files.

## Steps to configure UUID filename pattern

>[!INFO]
>
> The steps to configure UUID filename pattern differ based on your deployment type: Cloud or On-Premise. Select only the tab relevant to your deployment.

>[!BEGINTABS]

>[!TAB Cloud Service] 

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to configure UUID filename pattern:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.config.ConfigManager`|`uuid.regex`|String specifying the regex for UUID filename pattern. <br> If a file doesn't follow the specified pattern, a UUID is added to the file's property and all references to the file are updated with the UUID assigned to the file. <br> **Default value**: `"^GUID-(?<id>.*)"` |


>[!TAB On-premise] 

Perform the following steps to check file names against a UUID pattern and assign UUID to files that do not have a UUID assigned:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and select the *com.adobe.fmdita.config.ConfigManager* bundle.

1.  In the **UUID Filename Patterns** property, specify a pattern to check the imported file's names.

    If a file doesn't follow the specified pattern, a UUID is added to the file's property and all references to the file are updated with the UUID assigned to the file.

1.  Select **Save**.

>[!ENDTABS]





