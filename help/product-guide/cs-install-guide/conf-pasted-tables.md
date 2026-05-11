---
title: Customize Web Editor
description: Learn how to customize the display of pasted tables in Editor
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 839128b4-4889-4c61-b1c0-214ba1d3165e
TQID: https://experienceleague.adobe.com/0g3LyLfKxZEbtl968wJK6r1xPHRjagayeBF4xSvJF6c
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
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
    internal-label: Profiles
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
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
