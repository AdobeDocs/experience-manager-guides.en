---
title: Create output presets from the Web Editor
description: Create output presets from the web editor. Learn how to edit, rename, duplicate, and delete an output preset in AEM Guides.
feature: Authoring, Features of Web Editor, Publishing
role: User
hide: true
exl-id: ce8e3614-907b-4172-a8f0-e81e4dc096df
TQID: https://experienceleague.adobe.com/nCmtXuQXfOVVHbmGrRT6rVzEa6NlR-o9TGmwhqczWPs
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
# Create output presets from the Web Editor {#id218CL400JW3}

Perform the following steps to create output presets for your DITA map:

1.  In the Assets UI, navigate to the map file that you want to edit.

1.  To get an exclusive lock on the map file, select the map file and click **Check Out**.

1.  Select the **Edit Topics** option from the action menu on the map file.

    The map file is opened for editing in the Web Editor.

    >[!NOTE]
    >
    > You can add or delete any topic from the map using the Advanced Map Editor. For more details, see [Work with the Advanced Map Editor](map-editor-advanced-map-editor.md#).

1.  In the **Output** tab, select the + icon to create an output preset for your DITA map.

    ![](images/output-tab-preset_cs.png){width="350"}

1.  Enter the name of the preset in the Add preset dialog and then click **Add**.

1.  Enter the following configuration details.

    1.  Select the required options in the **General** tab. You can choose to create an output preset with or without conditions. You can also use a DITVAL file. AEM Guides also allows you to select a baseline for publishing a specific version of your DITA map.
    1.  Enter the AEM Site details in the **AEM** tab. **Site** displays the list of the AEM Sites available on your AEM repository. **Category**, **Section Template**, and **Article Template** are the structural components used to organize the look and feel of your output. These are predefined in the AEM Site template.

        >[!NOTE]
        >
        > Refresh each dropdown to get the further classification in the next drop down.

    1.  From the **Articles** tab, select the topics for which you wish to generate the output.
1.  Select the **Generate Preset** icon at the top to generate the output.

    ![](images/add-preset-articles-tab_cs.png){width="800"}

1.  You will see the status of the output generation process. The **Topics** column lists the topics for which output is being generated while the **Status** column displays the publishing status of each topic.

    To view the output, hover the mouse pointer over the topic and click View Output.

    ![](images/add-preset-output-generated_cs.png){width="800"}


>[!NOTE]
>
> You can also Edit, Rename, Duplicate, or Delete an existing output preset from the Options menu.

![](images/edit-preset_cs.png){width="550"}

**Parent topic:**[Article-based publishing from the Web Editor](web-editor-article-publishing.md)
