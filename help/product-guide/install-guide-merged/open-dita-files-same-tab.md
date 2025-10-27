---
title: Open DITA topic or map files in same tab
description: Learn how to Open DITA topic or map files in same tab
exl-id: 81ad2e18-3ea7-4cc1-8387-d703d1038a18
feature: Web Editor Configuration
role: Admin
level: Experienced
---
# Open DITA topic or map files in same tab {#id223HI0P202H}

In some workflows, when you click on a link of a topic or a map file, it opens in a new tab. This could lead to many tabs opened in your browser, which could impact your productivity. You can change this behavior of opening a topic or map file in a new tab, and force it open in the current tab itself. To do so, perform the following configuration changes:

>[!BEGINTABS]

>[!TAB Cloud services]

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to open a topic or map file in a new tab:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`xmleditor.openinsametab`|Boolean \(true/false\). <br> **Default value**: `false`|

This setting impacts the following places from where you can access the topic or map files:

-   Create DITA Topic \(at the end of the workflow, when you click the **Open Topic** button\)

-   Create DITA Map \(at the end of the workflow, when you click the **Open Map** button\)

-   Topics tab in the DITA map console

-   Baselines tab in the DITA map console

-   Reports tab in the DITA map console

>[!TAB On-Prem services]

To open DITA topic or map file in the same tab, perform the following configuration changes:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundle.

1.  Select the **Open DITA Topic/Map in Same Tab** option.

1.  Click **Save**.

This setting impacts the following places from where you can access the topic or map files:

-   Create DITA Topic \(at the end of the workflow, when you click the **Open Topic** button\)

-   Create DITA Map \(at the end of the workflow, when you click the **Open Map** button\)

-   Topics tab in the DITA map console

-   Baselines tab in the DITA map console

-   Reports tab in the DITA map console

In some workflows, when you click on a link of a topic or a map file, it opens in a new tab. This could lead to many tabs opened in your browser, which could impact your productivity. You can change this behavior of opening a topic or map file in a new tab, and force it open in the current tab itself.



>[!ENDTABS]

**Parent topic:**[Customize Web Editor](conf-web-editor.md)
