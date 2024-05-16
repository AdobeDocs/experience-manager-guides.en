---
title: Publish a topic to a content fragment
description: Publish a topic or the elements within a topic to a content fragment in AEM Guides.  Learn how to view the content fragments present for a topic and republish them.
exl-id: b1769e48-d721-4e93-b10f-04b385272be7
feature: Publishing
role: User
---
# Publish to a content fragment

Content fragments are discrete pieces of content in Adobe Experience Manager. They are structured content based on a content model. Content fragments are pure content without design or layout information. They can be authored and managed independently of the channels that AEM supports. Content fragments are modular, where content is broken down into smaller components.

Adobe Experience Manager Guides allows you to publish a topic or the elements within a topic to a content fragment. You can create a JSON-based mapping between a topic and a content fragment model. Use this mapping to publish a topic or the elements within a topic to a content fragment. You can then use content fragments in any Adobe Experience Manager site or extract the details via APIs supported by content fragments.


To create a content fragment, perform the following steps:

1. Create a [content fragment model](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=en) in Adobe Experience Manager Assets. 
1. Create a folder where you want to save the content fragments that you create based on the content fragment model. For example, "stock-content-fragments". 
1. Edit the folder’s properties (for example, "stock-content-fragments") and add the path of the folder, which contains the content fragment model in the cloud configuration. 
For example, add `/conf/we-retail` in the cloud configuration. This configuration connects all the content fragment models with the folder.       
 ![add cloud configuration details in the folder properties](images/fragment-folder-cloud-configuration.png){width="650" align="left"}
       *Add the cloud configuration in the folder properties to connect it with the fragment models.* 
1. Select the topic that you want to publish in the **Repository View**. 
1. From the **Options** menu, select **Publish As** > **Content Fragment**.  
1. In the **Publish As Content Fragment** dialog, fill in the following details:
        ![Add the fragment model and mapping details in the Publish as content fragment dialog](images/content-fragment-publish.png){width="500" align="left"}
       *Add the path, model, and mapping details to publish a topic or its elements as a content fragment. You can overwrite an existing content fragment.*  

    * **Path**: Browse and select the path of the folder where you want to publish the content fragment. You can also select an existing content fragment and publish it.
    * **Title**: Enter the title of the content fragment.
    * **Name**: Enter the name of the content fragment.
    * **Model**: Select the content fragment model that you want to use to create your content fragment. The models are picked from the folder which you have configured in the cloud services. 
    * **Mapping**: Select a mapping from the drop-down. It picks the mappings from the *contentFragmentMapping.json* file.  

      

        Your administrator can add the mappings in the *contentFragmentMapping.json* file. Learn more about how to [create a mapping between a topic and a content fragment](../cs-install-guide/conf-content-fragment-mapping-cs.md) in the  Installation and Configuration Guide. 

    * You can also select different conditions to publish the content.  Select one of the following options:

        * **None**: Select this option if you don’t want to apply any condition on the published output.
        * **DITAVAL**: Select DITAVAL file(s) to generate personalized content. You can select multiple DITAVAL files using the browse dialog or by typing the file path. 
        * **Condtion attributes**: You can define condition attributes in your DITA topics. Then, select the condition attribute in the condition preset to publish the relevant content.
    
        To know more about condition presets, view [Use condition presets](generate-output-use-condition-presets.md).

       
    * Select **Overwrite** if your content fragment already exists and you wish to overwrite it. Experience Manager Guides displays an error if you don’t select the checkbox and your content fragment already exists. 
1. Click **Create** to publish the content fragment.

1. You can view the content fragments  for a topic under the **Outputs** section in the **File properties**.
 
    ![View the content fragments for a topic](images/outputs-options-menu.png){width="300" align="left"}
       
     *View the content fragments present for a topic and republish them.*  


Once you’ve published the content fragments, you can also use them in any Adobe Experience Manager Site.




## Options menu for an content fragment 

You can also perform the following actions for an content fragment from the **Options** menu:

* **Generate**: Republish the content fragment to update it with the latest content from the DITA topic. When you regenerate the output, you cannot change the path, name, title, and template of the content fragment. However, you can select different conditions while regenerating the output.

* **Duplicate**: Duplicate an content fragment. You can change the path, name, title, and the template. You can also select different conditions when you duplicate an content fragment.

* **Remove**: Remove an content fragment from the outputs list. A confirmation prompt appears. Once you confirm, the content fragment is removed from the **Outputs** list. 

* **View**: View the content fragment in an editor. You can also make changes and save them.

 
