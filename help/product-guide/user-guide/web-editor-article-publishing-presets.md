---
title: Create output presets from the Web Editor
description: Create output presets from the web editor. Learn how to edit, rename, duplicate, and delete an output preset in AEM Guides.
exl-id: cd38b039-ef91-45c9-a226-433e57b09873
feature: Authoring, Features of Web Editor, Publishing
role: User
TQID: https://experienceleague.adobe.com/e5BEPmlmFDY2ipC8nNQPjrgGx3cV6AaD4PmZYw4hAYI
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
    internal-label: Web Editor
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Create output presets for Knowledge Base from the Editor {#id218CL400JW3}

Perform the following steps to create output presets for your DITA map:

1.  In the Assets UI, navigate to the map file that you want to edit.

1.  To get an exclusive lock on the map file, select the map file and select **Checkout**.

1.  Select the **Edit Topics** option from the action menu on the map file.

    The map file is opened for editing in the Editor.

    >[!NOTE]
    >
    > You can add or delete any topic from the map using the Advanced Map Editor. For more details, view [Work with the Advanced Map Editor](map-editor-advanced-map-editor.md#).

1. Select the **Open in map console** icon. The map opens in the map console. 

1. Navigate to the **Output presets** tab and select the + icon to create an output preset for your DITA map.   

1. Select **Knowledge Base** from the **Type** drop-down, enter name, and select **Adobe Experience Manager** in the **New output preset** dialog box.
1. Select the **Add to current folder profile** option to create an output preset for the current folder profile. ![folder profile icon](images/global-preset-icon.svg) icon indicates a folder profile level preset.  

   Learn more about [Manage Global and Folder Profile output presets](./web-editor-manage-output-presets.md).

 1. Select **Add**.   

    The preset for Knowledge Base is created.


    ![New ](images/knowledge-base-preset-dialog-box.png)

Once the preset is created, you can generate the output for specific knowledge base articles. To do this, navigate to the **Articles** tab and select the topics for which you wish to generate the output.
1. Select **Generate output** at the top to generate the output.

    ![](images/add-preset-articles-tab_cs.png)

1. In the **Confirm files for publishing** prompt, select the files you want to publish and confirm by selecting **Publish**.

    ![New ](images/knowledge-base-confirm-files-for-publishing.png)

You will view the status of the output generation process. The **Topics** column lists the topics for which output is being generated while the **Status** column displays the publishing status of each topic.


![](images/add-preset-output-generated_cs.png)

To view the output, close the Output Generated dialog box and select **View output** on the preset page. 


>[!NOTE]
>
> You can also Rename, Duplicate, or Delete an existing output preset from the Options menu.



**Parent topic:**[Article-based publishing from the Editor](web-editor-article-publishing.md)
