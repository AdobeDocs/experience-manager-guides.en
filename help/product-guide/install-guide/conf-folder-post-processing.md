---
title: Configure filenames
description: Learn how to disable postprocessing for a folder uploaded to Adobe Experience Manager Assets
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: ff6e1322-9655-42aa-b353-199c70c9de49
---
# Disable postprocessing for a folder 

By default, all uploaded assets are processed using the DAM Update Asset workflow. Experience Manager Guides runs an additional processing, called postprocessing, as a part of this workflow. This also helps in generating the UUIDs.

While uploading your files and folders to the *Adobe Experience Manager Assets* server, you can also disable the postprocessing and the generation of UUIDs. 


Perform the following steps to disable the postprocessing on a given path or ignore the postprocessing for a folder:


1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http


    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.config.ConfigManager** bundle.

1.  Select the **Ignored Paths for Post Processing** option, to ignore a folder for post processing.

    String value to set any standard NODE_OPTIONS (multivalued property, strings with path that omit `/` at the end)

    **Default Value**: `/content/dam/projects/translation_output`

    >[!NOTE]
    >
    > This property is disabled by default and the translation tab is available on the map dashboard.
 
1. Select the **Enabled Paths for Post Processing** option, to enable a path for post processing.

    String value to set any standard NODE_OPTIONS (multivalued property, strings with path that omit `/` at the end)

    **Default Value**: `/content/dam/`

    >[!NOTE]
    >
    > This property is disabled by default and the translation tab is available on the map dashboard.


1.  Click **Save**.

>[!NOTE]
>
> In addition to the ignored and enabled paths configured via the OSGi configuration (`com.adobe.fmdita.config.ConfigManager`), post-processing behavior is also influenced by a repository-level node located at `/var/dxml/postprocess/ignoredPaths`. Commonly referred to as **cache** in Adobe Experience Manager Guides, this node contains properties that mark specific paths to be ignored, with each path set to `true`.<br> If a folder is unexpectedly excluded from post-processing and is not listed in the OSGi configuration, it is recommended to check this repository node. If the path appears there and is set to `true`, it will be ignored. To re-enable processing, you  can remove the corresponding property manually from the node.

## Rules to enable or disable postprocessing 

By default, postprocessing is done for every folder path under the Experience Manager DAM folder. Configurations are applied for any folder according to the following rules: 

* If the parent is ignored for postprocessing but the child folder is enabled, then the child and all its successors are considered enabled.
* If the parent is enabled for postprocessing but the child is ignored, then the child and all its successors are considered ignored.
* If the same folder path exists in both ignored.post.processing.paths and enabled.post.processing.paths configurations, then it's considered ignored for postprocessing.
