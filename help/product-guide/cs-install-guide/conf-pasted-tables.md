---
title: Customize Web Editor
description: Learn how to customize the display of pasted tables in Editor
feature: Web Editor Configuration
role: Admin
level: Experienced
---
# Configure display of pasted tables

Using the secondary toolbar in the Editor, you can insert a simple table at the current or next valid location of a topic. You can also copy a table from Microsoft Word or Excel and paste it directly into a topic file.

Administrators can configure how copied tables are displayed. By default, such copied tables are displayed as `<simpletable>` in the editor if they include edits or merged rows/columns. However, you can change this setting to display copied tables as `<tgroup>` by updating the XML Editor Configuration setting.

To update the default table format, perform the following steps:

1. Open the Adobe Experience Manager Navigations page and select **Tools** on the left.
2. In the Tools panel, select **Guides** from the list of tools.
3. Select **Folder Profiles**, and then select the **Global Profile** tile. 
4. Navigate to the **XML Editor Configuration** tab. 
5. Select the **Edit** icon on the top.
6. Select the Download icon to download the `ui_config.json` file on your local system. You can then make changes to the file and then upload the same.
7. In the `ui_config.json` file, update the `simpletable` setting as shown below: 

    The `simpletable` setting:

    ```
    "htmlToDitaMapping":{ "table": {"name" : "simpletable"} },

    ```
    Setting updated to `tgroup`

    ```
    "htmlToDitaMapping":{ "table": {
    "name" : "tgroup",
    "wrapTag" : {
        "dita" : "table",
        "html" : "div"
    }
    } },

6. Save the file and upload it.

