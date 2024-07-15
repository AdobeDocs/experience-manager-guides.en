---
title: Publish a topic to a Content Fragment
description: Publish a topic or the elements within a topic to a Content Fragment in AEM Guides.  Learn how to view the Content Fragments present for a topic and republish them.
exl-id: b1769e48-d721-4e93-b10f-04b385272be7
feature: Publishing
role: User
---
# Publish Content Fragments

Content Fragments are discrete pieces of content in Adobe Experience Manager. They are structured content based on a content model. Content Fragments are pure content without design or layout information. They can be authored and managed independently of the channels that Adobe Experience Manager supports. Content Fragments are modular, where content is broken down into smaller components.

Adobe Experience Manager Guides allows you to publish a topic or the elements within a topic to a Content Fragment. You can create a JSON-based mapping between a topic and a Content Fragment model. Use this mapping to publish a topic or the elements within a topic to a Content Fragment. You can then use Content Fragments in any Adobe Experience Manager site or extract the details via APIs supported by Content Fragments.


To create a Content Fragment, perform the following steps:

1. Create a [Content Fragment model](https://experienceleague.adobe.com/docs/experience-manager-65/assets/content-fragments/content-fragments-models.html?lang=en) in Adobe Experience Manager Assets. 
1. Create a folder where you want to save the Content Fragments that you create based on the Content Fragment model. For example, "stock-content-fragments". 
1. Edit the folder’s properties (for example, "stock-content-fragments") and add the path of the folder, which contains the Content Fragment model in the cloud configuration. 
For example, add `/conf/we-retail` in the cloud configuration. This configuration connects all the Content Fragment models with the folder.       
 ![add cloud configuration details in the folder properties](images/fragment-folder-cloud-configuration.png){width="650" align="left"}
       *Add the cloud configuration in the folder properties to connect it with the fragment models.* 

1. To generate a Content Fragment, select **New Output** ![new output icon](./images/Add_icon.svg) from the **Outputs** section in the **File Properties** of a topic.
1. Select **Content Fragment**.  
    ![file properties options tab](./images/file-properties-outputs-tab.png) {width="300" align="left"}

    *Add a new Content Fragment from the File Properties of a topic*.

1. In the **Generate Content Fragment** dialog box, fill in the following details:

    >[!NOTE]    
    >
    > If you are using 4.4 or 2406 or earlier versions, you view the options in a single tab.
    > If you are using 4.6 or 2409 or later versions, you view the options under the **General** and **Mapping** tabs.
    
    **General** tab 
            ![Add the fragment model and mapping details in the Publish as Content Fragment dialog](images/generate-content-fragment.png)
        *Add the path, name, title, and condition filtering to publish a topic or its elements as a Content Fragment. You can overwrite an existing Content Fragment.*  

    >[!NOTE]
    >
    >You can also publish a  Content Fragment from the **Repository View**. Select the topic that you want to publish as a Content Fragment. Then, from the **Options** menu, select **Publish As** > **Content Fragment**.

    * **Path**: Browse and select the path of the folder where you want to publish the Content Fragment. If you select an existing Content Fragment, it overwrites the contents of the mapped fields.
    * **Title**: Type the title of the Content Fragment. By default, the title is populated with the title of the topic. You can edit it. This title is used to generate the name of the Content Fragment.
    * **Name**: Type the name of the Content Fragment. By default, the name is populated with the title of the topic, and the spaces are replaced with '_'. For example, *sample_content_fragment*. You can edit it.  This name is used to generate the URL for the Content Fragment.

    * You can also select different conditions to publish the content.  Select one of the following options:
        >[!NOTE] 
        > 
        > Conditions are enabled only if condition attributes are defined in the topic.
        
        * **None**: Select this option if you don’t want to apply any condition on the published output.
        * **Using DITAVAL**: Select the DITAVAL file to generate output, which includes specific content. You can select the DITAVAL file using the browse dialog or by typing the file path. 
        * **Using attributes**: You can define condition attributes in your DITA topics. Then, select the condition attribute to publish the relevant content.

          
       
        >[!NOTE]    
        >
        > If you are using 4.4 or 2406 or earlier versions, select **Overwrite existing content** if your Content Fragment already exists and you wish to overwrite it. Experience Manager Guides displays an error if you don’t select the checkbox and your Content Fragment already exists. 



    **Mapping** tab

   ![Add the fragment model and mapping details in the Publish as Content Fragment dialog](images/content-fragment-mapping.png)

    *Add the content fragment model, and mapping details to publish a topic or its elements as a Content Fragment. You can overwrite an existing Content Fragment.*  

    * **Model**: Select the Content Fragment model that you want to use to create your Content Fragment. The models are picked from the folder, which you have configured in the cloud services. 
    * **Mapping**: You can view the topic elements that have an id attribute applied to them. Drag the topic elements to map them to the AEM components present in the content fragment model.  
    
    
        >[!NOTE]    
        >
        > If you are using 4.4 or 2406 or earlier versions, select a mapping from the drop-down. It picks the mappings from the *contentFragmentMapping.json* file.  Your administrator can add the mappings in the *contentFragmentMapping.json* file. Learn more about how to [create a mapping between a topic and a Content Fragment](../cs-install-guide/conf-content-fragment-mapping-cs.md) in the Installation and Configuration Guide. 

1. Click **Generate** to publish the Content Fragment.

1. You can view the Content Fragments for a topic under the **Outputs** section in the **File Properties**.
 
    ![View the Content Fragments for a topic](images/outputs-options-menu.png){width="300" align="left"}
       
     *View the Content Fragments present for a topic and republish them.*  


Once you’ve published the Content Fragments, you can also use them in any Adobe Experience Manager Site.




## Options menu for a Content Fragment 

You can also perform the following actions for a Content Fragment from the **Options** menu:

* **Generate**: Republish the Content Fragment to update it with the latest content from the DITA topic. When you regenerate the output, you cannot change the path, name, title, model, and mapping of the Content Fragment. However, you can select different conditions while regenerating the output.

* **Duplicate**: Duplicate a Content Fragment. You can change the path, name, title, model, and the mapping. You can also select different conditions when you duplicate a Content Fragment.

* **Remove**: Remove a Content Fragment from the outputs list. A confirmation prompt appears. Once you confirm, the Content Fragment is removed from the **Outputs** list. 

    >[!NOTE]
    >
    > No content is deleted from the Content Fragment by this action.

* **View**: View the Content Fragment editor. You can also make changes and save them.

 
