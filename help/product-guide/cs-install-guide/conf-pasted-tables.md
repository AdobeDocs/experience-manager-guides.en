---
title: Customize Web Editor
description: Learn how to customize the display of pasted tables in Editor
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 839128b4-4889-4c61-b1c0-214ba1d3165e
---
# Configure display of pasted tables

Using the secondary toolbar in the Editor, you can insert a simple table at the current or next valid location of a topic. You can also copy a table from Microsoft Word or Excel and paste it directly into a topic file.

Administrators can configure how copied tables are displayed. By default, such copied tables are displayed as `simpletable` in the editor. However, you can change this setting to display copied tables as `tgroup` by updating the XML Editor Configuration setting.

>[!NOTE]
>
> If you copy a table with merged rows or columns, then the table will be pasted as normal table `trgoup` and not `simpletable` irrespective of the table setting configured in the XML Editor Configuration. 

To update the default table format, perform the following steps:

1. Open the Adobe Experience Manager Navigations page and select **Tools** on the left.
2. In the Tools panel, select **Guides** from the list of tools.
3. Select **Folder Profiles**, and then select the profile where you want to update the table setting. 
4. Navigate to the **XML Editor Configuration** tab. 
5. Select the **Edit** icon on the top.
6. Select the **Download** icon to download the `ui_config.json` file on your local system. 
7. In the `ui_config.json` file, update the `simpletable` setting as shown below: 
 
    ```    
    "htmlToDitaMapping":{ "table": {
    "name" : "tgroup",
    "wrapTag" : {
        "dita" : "table",
        "html" : "div"
    }
    } },
    
    ```


Once updated, save the file and upload it.
