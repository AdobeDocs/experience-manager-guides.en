---
title: Configure display of UUID-based links
description: Learn how to Configure display of UUID-based links
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: d2383230-ff8f-4e9b-a529-9b9d167ebf90
---
# Configure display of UUID-based links {#id2035G20M0QN}

By default, when you create a link using the Insert Reference or Insert Reuse Content option in the Editor, the link is created using the UUID of the referenced content. The **Link** property \(in Properties panel\) of the referenced content can be configured to show the relative file path of the referenced content or the UUID. For Cloud Service, by default the UUID of the referenced content is shown in the Properties panel. For On-Premise, this display is controlled by the **Enable UUIDs** option in the `configMgr`. By default, it is turned ON, which implies that the UUID of the referenced content is shown in the Properties panel.

The following tabs provide instructions to show the relative path or the UUID of the referenced content in the Editor based on your Experience Manager Guides setup: Cloud Service or On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Use the instructions given in [Configuration overrides](download-install-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to show the relative path or the UUID of the referenced content in the Editor.

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`xmleditor.uuid`|Boolean \(true/false\). If you want to show the relative path of the linked content, then set this property to false. <br> **Default value**: true |


>[!TAB On-Premise]

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundle.

1.  In the *XmlEditorConfig* settings, the **Enable UUIDs** option is enabled by default. This implies that UUID of the referenced content is shown in the **Link** property in the Properties panel.

    If you want to show the relative path of the linked content, then deselect the **Enable UUIDs** option.

1.  Click **Save**.

>[!ENDTABS]

**Parent topic:**[Customize Web Editor](customize-overview.md)
