---
title: Set the Advanced Map Editor as default
description: Learn how to Set the Advanced Map Editor as default
exl-id: ecc023f6-48eb-4afd-97a2-4b3cdd5a8991
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

Perform the following steps to make the Advanced Map Editor as the default editor for the map files:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundle.

1.  Select the **Hide Basic Map Editor** option.

    With this option selected, users will not see the Basic Map Editor link anywhere in the user interface. By default, map files will open in the Advanced Map Editor.
