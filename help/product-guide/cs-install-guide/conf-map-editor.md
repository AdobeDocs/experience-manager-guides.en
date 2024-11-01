---
title: Set the Advanced Map Editor as default
description: Learn how to Set the Advanced Map Editor as default
exl-id: 365264ab-f990-42c1-ab79-61a40ecea42f
feature: Web Editor Configuration
role: Admin
level: Experienced
---
# Set the Advanced Map Editor as default {#id181AI0003PN}

>[!NOTE]
>
> The Basic Map Editor, previously available in Experience Manager Guides, has been deprecated starting from version 4.3 and 2307. You can't access the Basic Map Editor to create and manage DITA maps.
>You are recommended to use the Advanced Map Editor. The Advanced Map Editor offers enhanced features and better customization options. Explore more about how to work with the [Advanced Map Editor](../user-guide/map-editor-advanced-map-editor.md). 

For versions earlier than 4.3 and 2307, Experience Manager Guides comes with a Basic Map Editor and an Advanced Map Editor. The Basic Map Editor gives you all necessary features to create your map file. The Advanced Map Editor is much more feature rich and it is integrated within the Web Editor. The Advanced Map Editor allows authors to create and edit DITA map files with an easy-to-use interface.

By default, whenever a new map file is created, it is opened in the Basic Map Editor. You can change this behavior by enabling the setting to open the Advanced Map Editor by default.

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to enable the Basic Map Editor:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|``fmdita.hide.oldmapeditor``|Boolean \(true/false\). If you want to use the Advanced Map Editor by default, then set this property to true.<br> **Default value**: false |

>[!NOTE]
>
> By default, when an author creates a map file and chooses to open it for editing, then the Basic Map Editor is launched. When the Edit option is selected for a map file from the Assets UI, then also it is opened in the Basic Map Editor.

**Parent topic:**[Customize Web Editor](conf-web-editor.md)
