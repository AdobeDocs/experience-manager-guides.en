---
title: Article-based publishing from the Map console
description: Learn how to publish one or more articles from the Map console. Generate output for one or more topics in a DITA map in AEM Guides.
exl-id: d89ce69d-8d4c-4265-bfca-60763f561afd
feature: Publishing
role: User
---
# Publish Knowledge Base articles {#id218CL05J0M1}

Adobe Experience Manager Guides comes with an article-based publishing feature that allows the users to publish one or more Knowledge Base articles simultaneously.

This engine also comes with an OOTB content template, built on top of Adobe Experience Manager core components, that lets users create a knowledge-based repository of the technical content. This template can be customized to suit the needs of the customers.This engine allows the users to build the DITA map in an additive fashion and publish topics as and when they are ready. 

If you have updated the content only for a few topics in your DITA map, you do not always have to publish the entire map. You can select and publish only the updated topics.

For article-based publishing, you need to create the output preset for your Knowledge Base DITA map. Your map must include the topics that you want to publish. You can also apply conditions and specify the AEM Sites details for the output preset. Then, you can generate output using the **Generate output** feature.


## Create output presets for article-based publishing

Perform the following steps to create output presets for your DITA map:

1. [Open the DITA map file in Map console](./open-files-map-console.md).
1. Navigate to the **Output presets** tab and select the + icon to create an output preset for your DITA map.   
1. Select **Knowledge Base** from the **Type** drop-down, enter name, and select **Adobe Experience Manager** in the **New output preset** dialog box.
1. Select the **Add to current folder profile** option to create an output preset for the current folder profile. ![folder profile icon](images/global-preset-icon.svg) icon indicates a folder profile level preset.  

   Learn more about [Manage Global and Folder Profile output presets](./web-editor-manage-output-presets.md).

 1. Select **Add**.   

    The preset for Knowledge Base is created.


    ![New ](images/knowledge-base-preset-dialog-box.png){width="800" align="left"}

For preset configuration details, view [create the output preset for your Knowledge Base](./generate-output-knowledge-base.md).

## Generate output 

Once the preset is created, you can generate the output for specific knowledge base articles. 

Perform the following steps to generate article-based ouput:

1. Navigate to the **Articles** tab and select the topics for which you wish to generate the output.
1. Select **Generate output** at the top to generate the output.

    ![](images/add-preset-articles-tab_cs.png){width="800" align="left"}

1. In the **Confirm files for publishing** prompt, select the files you want to publish and confirm by selecting **Publish**.

    ![New ](images/knowledge-base-confirm-files-for-publishing.png){width="800" align="left"}

    You will view the status of the output generation process. The **Topics** column lists the topics for which output is being generated while the **Status** column displays the publishing status of each topic.


    ![](images/add-preset-output-generated_cs.png){width="800" align="left"}

    To view the output, close the **Output Generated** dialog box and select **View output** on the preset page. 


    >[!NOTE]
    >
    > You can also Rename, Duplicate, or Delete an existing output preset from the Options menu.


**Parent topic:**[Work with the Editor](web-editor.md)
