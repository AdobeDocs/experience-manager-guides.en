---
title: Configure file auto-save in the Web Editor
description: Learn how to Configure file auto-save in the Web Editor
exl-id: 4d99c3d8-cf6a-4cf3-aaec-9009a0376c1e
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/yHZSl9G2a6ras7kUUpNho5TG8yeIJzeFXzwxGQSWp44
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Configure file auto-save in the Web Editor {#id199CC0J0M5Z}

One of the most common features in the browser-based editor it the ability to save data after a specific period of time. The AEM Guides Web Editor also supports auto-saving of topic and map files at the specified time interval. When this feature is triggered, the working copy of the topic or map is saved. A new version of the topic or map is not created. To create a new version, you have to click the Save Revision icon in the Web Editor's toolbar.

The auto-save feature is not enabled by default and you need to enable this using the configuration file.

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to configure file auto-save and auto-save time interval:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`xmleditor.autosave`|Boolean \(true/false\).<br> **Default value**: false |
|`xmleditor.autosaveinterval`|Specify the time interval in seconds to trigger the auto-save feature.||

**Parent topic:**[Customize Web Editor](conf-web-editor.md)
