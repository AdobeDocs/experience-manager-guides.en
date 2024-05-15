---
title: Publish a topic to a experience fragment
description: Publish a topic or the elements within a topic to a experience fragment in AEM Guides.  Learn how to view the experience fragments present for a topic and republish them.
exl-id: b1769e48-d721-4e93-b10f-04b385272be7
feature: Publishing
role: User
---
# Publish to an experience fragment

Experience fragments are pieces of modular content in Adobe Experience Manager. These content blocks are based on templates and encapsulate both content and its layout. These reusable pieces of content allow content creators to assemble and deliver consistent, scalable experiences across multiple channels that Experience Manager supports. This feature helps you easily create consistent marketing experiences efficiently, such as newsletters, promotion banners, and customer testimonials.  

Experience Manager Guides allow you to publish a topic or its elements to an experience fragment. You can create a JSON-based mapping between a topic and components in an experience fragment and use this mapping to publish a topic or its elements to an experience fragment. You can then use experience fragments in any Experience Manager site or extract the details via APIs supported by experience fragments.




To generate an experience fragment, perform the following steps:


1.  Create a folder in the Experience Fragments. Use this folder to save the experience fragments that you create based on the experience fragment templates. For example, *sales-experience-fragments*. 
1. Edit the folder’s properties (for example, *sales-experience-fragments*).
    * Add the path of the folder, which contains the experience fragment templates in the cloud configuration. 
For example, add `/conf/we-retail` in the cloud configuration. This configuration connects all the experience fragment templates with the folder.
    
    * To add the allowed template, specify the regular expression for retrieving the required templates in the **Allowed Templates** field. 
For example:
`/libs/cq/experience-fragments/components/experiencefragment/template`

If you do not define an allowed template for a folder, the templates are picked from the parent folder or the templates folder by default. 

    ![add cloud configuration details in the folder properties](images/fragment-folder-cloud-configuration.png){width="650" align="left"}
       *Add the cloud configuration in the folder properties to connect it with the fragment templates.* 
1. In the **Repository View**, select the topic that you want to publish as an experience fragment. . 
1. From the **Options** menu, select **Publish As** > **Experience fragment**.  
1. In the **Generate Experience Fragment** dialog box, fill in the following details:
        ![Add the fragment model and mapping details in the Publish as experience fragment dialog](images/experience-fragment-generate.png){width="500" align="left"}
       *Add the path, model, and mapping details to publish a topic or its elements as an experience fragment. You can overwrite an existing experience fragment.*  

    * **Path**: Browse and select the path of the folder where you want to publish the experience fragment. You can also select an existing experience fragment and republish it.
    * **Title**: Enter the title of the experience fragment.
    * **Name**: Enter the name of the experience fragment. By default, the name is created from the title, and the spaces are replaced with '_'. For example, *sample_expereince_fragment. 
    * **Template**: Select the experience fragment template that you want to use to create your experience fragment. The templates are picked from the folder that you have configured in the properties. 
    * **Mapping**: It picks the mapping from the *experienceFragmentMapping.json* file and displays it.  

      

        Your administrator can add the mappings in the *experienceFragmentMapping.json* file.  Learn more about how to [create a mapping between a topic and a experience fragment](../cs-install-guide/conf-experience-fragment-mapping-cs.md) in the  Installation and Configuration Guide.

    * You can also select different conditions to publish the content.  Select one of the following options:

        * None: Select this option if you don’t want to apply any condition on the published output.
        * DITAVAL: Select DITAVAL file(s) to generate personalized content. You can select multiple DITAVAL files using the browse dialog or by typing the file path. To know more about condition presets, view [Use condition presets](generate-output-use-condition-presets.md).
        
    * Select the **Overwrite existing content** checkbox if your experience fragment already exists and you wish to overwrite it. Experience Manager Guides displays an error if you don’t select the checkbox and your experience fragment already exists. 
1. Click **Generate** to publish the experience fragment.
1. You can view the experience fragments for a topic under the **Outputs** section in the **File properties**. The experience fragments appear according to the date and time of their publishing. 
 
    ![View the experience fragments for a topic](images/experience-fragment-outputs.png){width=300 align="left"}
       
     *View the experience fragments present for a topic and republish them.*  

 


Once you’ve published the experience fragments, you can also use them on any Adobe Experience Manager site.


## Options menu for an Experience Fragment 

You can also perform the following actions for an experience fragment from the Options menu:

* **Generate**: Republish the experience fragment to update it with the latest content from the DITA topic. When you regenerate the output, you cannot change the path, name, title, and template of the experience fragment. However, you can select different conditions while regenerating the output.

* **Duplicate**: Duplicate an experience fragment. You cannot change the path, name, title, and the template of the experience fragment when you duplicate an experience fragment. You can select different condtions when you duplicate an experience fragment.

* **Remove**: Remove an experience fragment from the outputs list. A confirmation prompt appears. Once you confirm, the experience fragment is removed from the **Outputs** list. 

* **View**: View the experience fragment in an editor. You can make changes and save them.

 
