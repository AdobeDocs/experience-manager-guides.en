---
title: Open DITA topic or map files in same tab
description: Learn how to Open DITA topic or map files in same tab
exl-id: 81ad2e18-3ea7-4cc1-8387-d703d1038a18
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/-QYM6xoQCkvRcpxpsWtnJb5le7-4RirhgOZk94UvzIg
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
    internal-label: Reports
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Open DITA topic or map files in same tab {#id223HI0P202H}

In some workflows, when you click on a link of a topic or a map file, it opens in a new tab. This could lead to many tabs opened in your browser, which could impact your productivity. You can change this behavior of opening a topic or map file in a new tab, and force it open in the current tab itself. To do so, perform the following configuration changes:

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


**Parent topic:**[Customize Web Editor](conf-web-editor.md)
