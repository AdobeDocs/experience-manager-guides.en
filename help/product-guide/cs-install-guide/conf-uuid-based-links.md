---
title: Configure display of UUID-based links
description: Learn how to Configure display of UUID-based links
exl-id: 2ae6a27f-983b-4aa0-be29-166899aeb4ff
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/--RdjezGIsplCdBLF8u-3LvR92rVBcgGmPo8a7GbQys
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
# Configure display of UUID-based links {#id2035G20M0QN}

By default, when you create a link using the Insert Reference or Insert Reuse Content option in the Web Editor, the link is created using the UUID of the referenced content. The **Link** property \(in Properties panel\) of the referenced content can be configured to show the relative file path of the referenced content or the UUID. By default, the UUID of the referenced content is shown in the Properties panel.

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to show the relative path or the UUID of the referenced content in the Web Editor:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`xmleditor.uuid`|Boolean \(true/false\). If you want to show the relative path of the linked content, then set this property to false. <br> **Default value**: true |

**Parent topic:**[Customize Web Editor](conf-web-editor.md)
