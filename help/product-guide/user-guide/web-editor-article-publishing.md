---
title: Generate Knowledge Base output
description: Learn how to publish one or more articles from the Map console. Generate output for one or more topics in a DITA map in AEM Guides.
exl-id: d89ce69d-8d4c-4265-bfca-60763f561afd
feature: Publishing
role: User
---
# Generate Knowledge Base output {#id218CL05J0M1}

Adobe Experience Manager Guides comes with an article-based publishing feature that allows the users to publish one or more Knowledge Base articles simultaneously.

This engine also comes with an OOTB content template, built on top of Adobe Experience Manager core components, that lets users create a knowledge-based repository of the technical content. This template can be customized to suit the needs of the customers.This engine allows the users to build the DITA map in an additive fashion and publish topics as and when they are ready. 

If you have updated the content only for a few topics in your DITA map, you do not always have to publish the entire map. You can select and publish only the updated topics.

For article-based publishing, you need to create the output preset for your Knowledge Base DITA map. Your map must include the topics that you want to publish. You can also apply conditions and specify the AEM Sites details for the output preset. Then, you can generate output using the **Generate output** feature.

Perform the following steps to generate article-based ouput:

1. [Create the Knowledge Base preset](./generate-output-knowledge-base.md) for article-based output.
1. Navigate to the **Articles** tab and select the topics for which you wish to generate the output.
1. Select **Generate output** at the top to generate the output.

    ![](images/add-preset-articles-tab_cs.png){align="left"}

1. In the **Confirm files for publishing** prompt, select the files you want to publish and confirm by selecting **Publish**.

    ![New ](images/knowledge-base-confirm-files-for-publishing.png){align="left"}

    You will view the status of the output generation process. The **Topics** column lists the topics for which output is being generated while the **Status** column displays the publishing status of each topic.


    ![](images/add-preset-output-generated_cs.png){align="left"}

    To view the output, close the **Output Generated** dialog box and select **View output** on the preset page. 


    >[!NOTE]
    >
    > You can also Rename, Duplicate, or Delete an existing output preset from the Options menu.


**Parent topic:**[Work with the Editor](web-editor.md)
