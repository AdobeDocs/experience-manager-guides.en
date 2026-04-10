---
title: Set the Advanced Map Editor as default
description: Learn how to Set the Advanced Map Editor as default
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 60205ca4-518f-49fa-b63b-f1a56d70fc01
---
# Set the Advanced Map Editor as default {#id181AI0003PN}

>[!NOTE]
>
> The Basic Map Editor, previously available in Experience Manager Guides, has been deprecated starting from version 4.3 and 2307. You can't access the Basic Map Editor to create and manage DITA maps.
>You are recommended to use the Advanced Map Editor. The Advanced Map Editor offers enhanced features and better customization options. Explore more about how to work with the [Advanced Map Editor](../user-guide/map-editor-advanced-map-editor.md). 

For versions earlier than 4.3 and 2307, Experience Manager Guides comes with a Basic Map Editor and an Advanced Map Editor. The Basic Map Editor gives you all necessary features to create your map file. The Advanced Map Editor is much more feature rich and it is integrated within the Web Editor. The Advanced Map Editor allows authors to create and edit DITA map files with an easy-to-use interface.

By default, whenever a new map file is created, it is opened in the Basic Map Editor. You can change this behavior by enabling the setting to open the Advanced Map Editor by default.

The following tabs provide instructions to make the Advanced Map Editor as the default editor for the map files based on your Experience Manager Guides setup: Cloud Service or On-Premise.


>[!BEGINTABS]

>[!TAB Cloud Service]

Use the instructions given in [Configuration overrides](download-install-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to enable the Basic Map Editor:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|``fmdita.hide.oldmapeditor``|Boolean \(true/false\). If you want to use the Advanced Map Editor by default, then set this property to true.<br> **Default value**: false |

>[!NOTE]
>
> By default, when an author creates a map file and chooses to open it for editing, then the Basic Map Editor is launched. When the Edit option is selected for a map file from the Assets UI, then also it is opened in the Basic Map Editor.

>[!TAB On-Premise]

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundle.

1.  Select the **Hide Basic Map Editor** option.

    With this option selected, users will not see the Basic Map Editor link anywhere in the user interface. By default, map files will open in the Advanced Map Editor.

>[!ENDTABS]

**Parent topic:**[Customize Web Editor](customize-overview.md)
