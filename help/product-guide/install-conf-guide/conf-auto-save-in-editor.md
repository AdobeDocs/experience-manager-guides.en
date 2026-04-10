---
title: Configure file auto-save in the Web Editor
description: Learn how to Configure file auto-save in the Web Editor
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 142a588a-3d26-48ee-a3fe-23882922243c
---
# Configure file auto-save in the Web Editor {#id199CC0J0M5Z}

One of the most common features in the browser-based editor it the ability to save data after a specific period of time. The AEM Guides Web Editor also supports auto-saving of topic and map files at the specified time interval. When this feature is triggered, the working copy of the topic or map is saved. A new version of the topic or map is not created. To create a new version, you have to click the Save Revision icon in the Web Editor's toolbar.

The auto-save feature is not enabled by default and you need to enable this using the configuration file for Cloud Service and from the `configMgr` for On-Premise .

The following tabs provide instructions to enable the auto-save feature in the Web Editorbased on your Experience Manager Guides setup: Cloud Service or On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Use the instructions given in [Configuration overrides](download-install-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to configure file auto-save and auto-save time interval:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`xmleditor.autosave`|Boolean \(true/false\).<br> **Default value**: false |
|`xmleditor.autosaveinterval`|Specify the time interval in seconds to trigger the auto-save feature.|

>[!TAB On-Premise]

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundle.

1.  In the *XmlEditorConfig* settings, select the **Auto Save** option.

1.  In the **Auto Save Interval** field, specify the time interval in seconds to trigger the auto-save feature.

1.  Click **Save**.

>[!ENDTABS]
