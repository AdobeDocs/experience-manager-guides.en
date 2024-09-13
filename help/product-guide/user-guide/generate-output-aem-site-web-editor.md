---
title: AEM Sites
description: Create and configure AEM Sites preset in AEM Guides. Use AEM Sites support to generate article-based output, output linking topics, publish conref, and search a string within the content.
feature: Publishing
role: User
---

# AEM Sites {#id205BE3008SW}


You can create AEM Sites presets from the Web Editor and configure them to generate the AEM Sites output.

AEM Sites presets in Experience Manager Guides use the DITA-OT method to convert content into normalized formats and then into HTML. This HTML is subsequently used to create AEM Sites pages. AEM Sites leverage core WCM components, facilitating efficient content creation and management.

Experience Manager Guides provide predefined templates for creating AEM Sites. These presets help you ensure consistency in content layout and structure. You can also create custom templates based on these predefined templates, and apply styles accordingly.



## Create AEM Sites Presets

Perform the following steps to create the AEM Sites presets from the Web Editor:

1. In the Repository panel, open the DITA map file in Map View.
1. In the **Output** tab, select the + icon to create an output preset.
1. Select **AEM Sites** from the **Type** drop-down in the **New output preset** dialog box.

![New ](images/new-aem-sites-dialog-box.png)





>[!NOTE]
>
>Before configuring the AEM Sites presets for Experience Manager Guides, your administrator needs to create an AEM Sites structure using the templates. 
- **On-premise Software**: Learn more about how to [download and install AEM Sites templates](../install-guide/download-install-aem-sites-templates.md) for On-premise Software .
- **Cloud Service**: Learn more about how to [download and install AEM Sites templates](../cs-install-guide/download-install-aem-sites-templates-cs.md) for Cloud Service.


### AEM Sites presets based on legacy component mapping 

You can also create the AEM Sites presets using the legacy component mapping. These presets generate the AEM Sites output using only the DITA-OT method. 

To create the AEM Sites presets based on legacy component mapping, select **Use legacy component mapping** option from the **New output preset** dialog box.

Some options may differ for the presets that use legacy component mapping.



## Configure the AEM Sites presets

The configurations are organized under the **General**, **Content**, **Topic list**, and **Cross map references** tabs.

![aem sites preset settings](images/aem-sites-new-config.png)
**General**

The **General** tab contains the following configurations:

- Use site path
- Site
- Publish path
- Topic page template
- Generate page names based on
    - Topic file name
    - Topic title
- Cleanup previously generated pages
    - Delete previously generated pages for topics removed from the map 
    - Delete all pages created by other sources at this path:
- Post generation workflow



**Content**

The **Content** tab contains the following configurations:

- Use Baseline
- Condition filtering
- Additional DITA-OT command line arguments
- Metadata
    - File (Assets) properties
- Use map properties as fallback


For details, refer to [AEM Sites configuration](#aem_sites_config). 

**Topic List**

The Topic List displays the list of topics present in the current DITA map. You can select specific topics and generate the AEM Sites output only for them. By default, all topics are included.
**Topic List** tab is present in the AEM presets that are not created based on legacy mapping. 

**Cross-map references**
You are shown a list of source and the linked topics or xrefs in them. The source topics contain cross map references or links to some topics available in other DITA maps. 
Learn more about how to generate output linking topics from other maps.





## AEM Sites configuration {#aem_sites_config}

The following options are available for the AEM Sites output:

| AEM Sites options | Description |
| --- | --- |
|Use site path|Use this option if you want to publish your content to an Experience Manager Site.|
|Site|Home page of the Experience Manager Sites to which you want to publish your content.|
| Publish Path | The path within your AEM repository where the output is stored. While generating the final output, the Site Name and Destination Path are combined. For example, if you specify the Site Name as `user-guide` and the Destination Path as `/content/output/aem-guides`, then the final output is generated under the `/content/output/aem-guides/user-guide` node.<br><br>You can also use variables while setting the Destination Path. For more details about using variables, View [Use variables for setting the Destination Path, Site Name, or File Name options](generate-output-use-variables.md#id18BUG70K05Z). |
| Topic page template |The structural components that you can use to organize content consistently across multiple documents. These templates are predefined in the Adobe Experience Manager Site template.|
|Generate page names based on|  **Topic filename**: Uses the DITA topic's file name to create the Site names. <br> **Topic title**: Uses the DITA topic's title to create the Experience Manager Site names.|
| Cleanup previously generated pages| -  **Delete previously generated pages for topic removed from the map**: If you select this option, then all orphan pages are deleted from the published AEM Site. For this feature to run successfully, you must publish the entire DITA map and not use the incremental publishing.<br><br>Let's say you have published a DITA map, which contains topics a.dita, b.dita, and c.dita. Before publishing the map again, you removed b.dita topic from the map. Now, if you have selected this option, then all content related to b.dita is removed from the AEM Sites output and only a.dita and c.dita are published.<br><br>This feature does not remove any published child map. For example, if your parent map contains a child map, and you remove the entire child map, then the child map content is not deleted from the published output. However, if you remove any topic from a child map and republish, then the removed topic's content is deleted from the AEM Sites output.<br><br> Also, if there is any referenced content, and that content is removed before republishing, then the referenced content's data is not removed.<br><br>**Note**: Information about deleted orphan pages is also captured in the output generation logs. For more information about accessing the log files, [View and check the log file](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). <br><br>**Caution**: On deleting the topics, the pages become unavailable from the published site. So, before the topics are deleted, a warning appears. You must confirm to delete them.<br><br>- **Delete all pages created by other sources at this path**: If you select this option, all pages published on this path from other maps, individual topics, or any other source are deleted. The pages also become unavailable from the published site. So, before the topics are deleted, a warning appears. You must confirm to delete them.|
| Post Generation Workflow | When you choose this option, a new Post Generation Workflow drop-down list is displayed containing all workflows configured in AEM. You must select a workflow that you want to execute after completion of the output generation workflow. |
| Use Baseline | If you have created a Baseline for the selected DITA map, select this option to specify the version that you want to publish.<br><br>**Important**: When you are generating incremental output for the AEM Site, then the output is created using the current version of the files and not the attached Baseline.<br><br>View [Work with Baseline](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) for more details. |
| Conditional filtering | Select one of the following options:<br><br>**None Applied**: Select this option if you do not want to apply any condition on the published output.<br>**DITAVal file**: Select DITAVal file(s) to generate conditionalized content. You can select multiple DITAVal files using the browse dialog or by typing file path. Use the cross icon near the file name to remove it. DITAVal files are evaluated in the order specified, so the conditions specified in the first file take precedence over the matching conditions specified in later files. You can maintain the file order by adding or deleting files. If the DITAVal file is moved to some other location or is deleted, it is not automatically deleted from the map dashboard. You need to update the location in case files are moved or deleted. You can hover over the file name to view the path in the AEM repository where the file is stored. You can only select DITAVal files and an error is displayed if you select any other file type.<br>**Condition preset**: Select a condition preset from the drop-down to apply a condition while publishing the output. This option is visible if you have added a condition for the DITA map file. The conditional settings are available in the Condition Presets tab of the DITA map console. To know more about condition preset, view [Use condition presets](generate-output-use-condition-presets.md#id1825FL004PN). |
| Additional DITA-OT Command Line Arguments | Specify the additional arguments that you want DITA-OT to process while generating output. For details about the command-line arguments supported in DITA-OT, view [DITA-OT documentation](https://www.dita-ot.org/). |
| File (Assets) Properties | Select the properties that you want to process as metadata. These properties are set from the Properties page of the DITA map or bookmap file. The properties you select from the dropdown list appear under the **File Properties** field. Select the cross icon next to the property to remove it. <br><br>**Note**: The metadata properties are case-sensitive.<br><br>*If you have selected a Baseline, then the values for the properties are based on the version of the selected Baseline.<br>* If you have not selected a Baseline, then the values for the properties are based on the latest version.<br><br>You can also pass on the metadata to the output using DITA-OT publishing. For more details view, [Pass on the metadata to the output using DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Note**: If you have not defined the `cq:tags` in the Properties option, then the values for `cq:tags` are picked from the current working copy even if you have selected a Baseline for publishing. |
| Use map properties as fallback | If selected, the properties defined for the map file are also copied into the topics where such properties are not defined. Consider the following points while using this option:<br><br>*Only String, Date, or Long (singe and multi-valued) properties can be passed on to the AEM Site pages.<br>* The metadata values for a String type property does not support any special characters (such as `@, #, " "`).<br>* This option should be used along with the `Properties` option. |
| Existing Output Pages | Select the **Overwrite Content** option to overwrite content in the existing pages. This option only overwrites content present under the content and head nodes of the page. This option enables blended publishing of content. Selecting this option provides an option to select deleting orphan pages from the published output. This is also the *default* option for creating the AEM Sites output.<br><br>Select the **Delete and Create** option to force delete any existing pages during publishing. This option deletes the page node along with its content and all child pages under it. Use this option if you have changed the design template of your output preset or if you want any extra pages already present in the destination to be removed.| 
| Retain temporary files | Select this option to retain the temporary files generated by DITA-OT. If you are experiencing errors while generating output through DITA-OT, select this option to retain the temporary files. You can then use those files to troubleshoot output generation errors.<br> <br>  After generating the output, select the **Download temporary files** ![download temporary files icon](images/download-temp-files-icon.png) icon to download the ZIP folder containing the temporary files. <br><br> **Note**: If file properties are added during generation, the output temporary files also include a *metadata.xml* file containing those properties. | 


### Generate the AEM Sites output using the templates

Experience Manager Guides allows you to use the out of the box templates or add your own AEM Sites templates.

Before configuring the AEM Sites presets, ensure to create an AEM Sites structure using the templates.  
For more details, view [Download and install AEM Sites templates](../install-guide/download-install-aem-sites-templates.md).



Perform the following steps to create and configure an AEM Sites preset:
1. Open the **Output Presets** tab of the DITA map you want to publish.
1. Select the **AEM Sites** output preset.
1. (Optional) Uncheck **Use legacy component mapping** option to create a non-legacy AEM Sites preset .
1. Click **Add**. The preset for AEM Sites is created.
1. You can configure the Out-of-the-box Sites template  in two ways:
    1. Select **Site** and then choose the publish path and the topic page templates from the populated options: 
         1. Select the Site.
        1. Select **Site**. For example, `AEMG Docs`. 
        1. The **Publish path** and the **Topic page template** options are automatically set in the dropdown. You can also choose the options. For example,  `AEMG-Docs-Site/en/docs/product1` and `Topic page` are set respectively.
    1. Select the complete Site path: 
        1. Select **Use Site path** option.
        1. Select the complete Site path. For example, `/content/AEMG-Docs-Site/en/docs/product1`.
        1. The ‘Topic page template’ is automatically set as `Topic Page`. 
        

1. Save the changes done to the preset.
1. Select the **Generate** option.
1. Generate AEM Sites for the corresponding map. For example, `/content/AEMG-Docs-Site/en/docs/product`.






### Publish linked topics

Experience Manager Guides simplifies the publishing of complex documents by allowing you to create topic references using the `peer @scope`. You can then define the publishing context of these references from the AEM Sites presets and finally generate the output of the linked topics. 
For more details, view [Generate output of linking topics from other maps](../user-guide/generate-output-aem-site.md#generate-output-linking-topics-from-other-maps).




Perform the following steps to specify the publishing context for cross-linked files:
1. Open the **Output Presets** tab of the DITA map you want to publish.
1. Select the **AEM Sites** output preset.

    You can view the **General**, **Content**, **Topic list**, and **Cross map references** tabs.
You'll not be able to view the cross-map linking in the following cases:
    - For the presets created before the 4.6 release. The Cross references tab is disabled and a tool tip, Refer to Map dashboard appears.
    - For presets created from the map dashboard. Refer to Map dashboard tooltip appears.
    - For OOTB presets, Refer to Map dashboard tooltip appears.
    - For global presets,  Create a local copy of this global preset to set cross map references.
If you want to use AEM Sites presets from the Web Editor, either create a new preset or duplicate the existing one.

1. Open the **Cross map references** tab. 

    You are shown a list of topics and their references. The source topics contain cross map references or links to some topics available in other DITA maps.
To use the cross-map reference panel from Web Editor, `<xrefs>` must have unique IDs. Unique IDs for `<xrefs>` will be automatically generated on editing/saving the older content if the ID isn't there.

    >[!NOTE]
    >
    >The **Cross map references** tab shows topics that are linked using the peer @scope only. For links with local @scope, you don’t need to specify the publishing context.

    All linked topics have their latest output preset and map selected by default. The publishing context for all the linked topics is set to `<Most recently generated>` map by default.
 
    ![Cross map references](images/aem-sites-cross-map-references.png)

1. If you want to use the most recently published output of each dependent file in the map, select **Use most recently generated** publish context for all dependent topics.
You should publish the map selected as the parent map before publishing the map containing linked topics. If the map with linked topics isn't published, the links appear as normal text instead of hyperlinks in the AEM Sites output.
You should select the same type of AEM Sites preset for the linked topic. For example, if the current AEM Sites preset uses legacy component mapping, then select a similar AEM Sites preset of the linked topic. 
1. In the Parent Map drop-down list, select the map file with whose output you want to link the current map’s output.
Selecting a map file shows the map’s UUID in the Parent Map UUID column. The Output Presets associated with the chosen map are listed in the Parent Map’s Preset list. For example, Topic 1 in Map A contains a reference to Topic 2. Topic 2 can be present in single or multiple maps. You can select the parent map and a specific preset or the most recently published output for each link.

1. If the same topic is referred to more than once in a file, then you can add a different publishing context for each instance. This provides greater flexibility and control over their content. For example, Topic 3 is present in both Map B and Map C. Topic 1 contains two references to Topic 3. You can choose Map B as a parent map for the first link and Map C as the parent for the second link.

1. In the Parent Map’s Preset drop-down list, select the output preset with which you want to link the current map’s output.
    >[!NOTE]
    >
    > The different AEM Sites presets of the current map appear in the dropdown list. If you don’t select a preset, a warning icon appears, and the output generation, fails.
1. Select the required map and its output preset for all source topics and select **Generate**.


### Generate article-based output from the Web Editor

You can generate the AEM Site output for one or more topics, or the entire DITA map from the Web Editor. You need to create output presets for your DITA map and then you can easily generate the AEM Site output for your map. If you have updated a few topics in your map, you can also generate the AEM Site output only for those topics from the Web Editor. For more details, view [Article-based publishing from the Web Editor](web-editor-article-publishing.md#id218CK0U019I).




**Parent topic:** [Understanding the output presets](generate-output-understand-presets.md)
