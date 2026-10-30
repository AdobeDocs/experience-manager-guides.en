---
title: Configure file auto-save in the Editor
description: Learn how to Configure file auto-save in the Editor
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 142a588a-3d26-48ee-a3fe-23882922243c
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
---
# Configure file auto-save in the Editor {#id199CC0J0M5Z}

One of the most common features in the browser-based editor is the ability to save data after a specific period of time. The AEM Guides Editor also supports auto-saving of topic and map files at the specified time interval. When this feature is triggered, the working copy of the topic or map is saved. A new version of the topic or map is not created. To create a new version, you have to click the Save Revision icon in the Editor's toolbar.

The auto-save feature is not enabled by default and you need to enable this using the configuration file for Cloud Service and from the `configMgr` for On-Premise .

The following tabs provide instructions to enable the auto-save feature in the Editor based on your Experience Manager Guides setup: Cloud Service or On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Use the instructions given in [Configuration overrides](download-install-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to configure file auto-save and auto-save time interval:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`xmleditor.autosave`|Boolean \(true/false\).<br> **Default value**: false |
|`xmleditor.autosaveinterval`|Specify the time interval in seconds to trigger the auto-save feature.||

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
