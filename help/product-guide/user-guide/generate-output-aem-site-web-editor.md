---
title: AEM Sites
description: Create and configure the AEM Sites preset in the Map cosole using the composite component mapping and legacy component mapping.
feature: Publishing
role: User
exl-id: f3657268-9dee-43af-b643-499dbc3ca948
---
# AEM Sites preset in the Map console

You can create AEM Sites preset from the Map console and configure them to generate the AEM Sites output. There are two ways to create  the AEM Sites output:

- [Use composite component mapping](#use-composite-component-mapping) 
- [Use legacy component mapping](#use-legacy-component-mapping)

>[!TIP]
>
> It is recommended that you use the composite component mapping, available in the Experience Manager Guides 2502 release, and newer versions, for an enhanced performance. 

## Use composite component mapping 

The composite component mapping offers faster and scalable publishing to AEM Sites as compared to legacy component mapping. It comes with out-of-the-box editable templates which can be customized as per your requirements using AEM Template editor. The templates utilize a mix of WCM core components and specialized `guides-components` to ensure that your end users get the best experience on your AEM Sites pages. You can also customize your existing templates using the composite component mapping method. 

Experience Manager Guides provides predefined templates for creating AEM Sites. These templates help you ensure consistency in content layout and structure. 
- [Create home pages](../cs-install-guide/download-install-aem-sites-templates-cs.md#create-a-home-page-using-the-template) based on these predefined templates. 
- You can [edit topic templates](../cs-install-guide/download-install-aem-sites-templates-cs.md#package-installation) and apply styles according to your requirements.
- You can also [customize existing AEM Sites templates](../cs-install-guide/download-install-aem-sites-templates-cs.md#customize-existing-aem-sites-templates).


**Create AEM Sites Preset**

Perform the following steps to create the AEM Sites preset using composite component mapping:

1. [Open the DITA map file in map console](./open-files-map-console.md). 
1. In the **Output presets** panel, select the + icon to create an output preset.
1. Select **AEM Sites** from the **Type** drop-down in the **New output preset** dialog box.
1. Deselect the **Use legacy component mapping** option.
1. Select the **Add to current folder profile** option to create an output preset within the current folder profile. The ![folder profile icon](images/global-preset-icon.svg) indicates a folder-profile-level preset.  

   Learn more about [Manage Global and Folder profile output presets](./web-editor-manage-output-presets.md).

 1. Select **Add**.   

    The preset for AEM Sites is created.


    ![New ](images/new-aem-sites-dialog-box.png){width="300" align="left"}

<!-----------------------
### Generate the AEM Sites output using the templates

Once, the preset is created, you can configure the various options available for AEM Sites output generation. Experience Manager Guides allows you to use the out of the box templates or add your own AEM Sites templates.

You can configure the Out-of-the-box Sites template  in two ways:

- In the **Sites** field, select the AEM sites where you want to publish your output.  For example, `AEMG Docs`.

    The **Publish path** and the **Topic page template** options are automatically set in the dropdown.  For example,  `AEMG-Docs-Site/en/docs/product1` and `Topic page` are set respectively. You can also choose the other options from the dropdown.

- Or, Select the **Use Sites path** option to select the complete Sites path, and then select a **Map page template**. 

    You can browse a predefined Sites path or specify a custom path even if the specified path has not been pre-created within the AEM Sites structure. In such cases, the system creates the necessary structure during the publishing process by using the selected map homepage template.

   For example, you can specify the path `/content/AEMG-Docs-Site/en/docs/product4` where the `product4`does not exist in the strcuture. In this case, the system automatically creates `product4` using the selected **Map page template** and publish the output within this newly created page. 
   
   The **Topic page template** is automatically set as `Topic Page`. However, you can choose to select other available options in the dropdown.

--->

### AEM Sites preset configuration for composite component mapping

>[!NOTE]
>
> Before configuring the AEM Sites preset for Experience Manager Guides, your administrator needs to create an AEM Sites structure using the templates. 

- **On-premise Software**: Learn more about how to [download and install AEM Sites templates](../install-guide/download-install-aem-sites-templates.md) for On-premise Software.
- **Cloud Service**: Learn more about how to [download and install AEM Sites templates](../cs-install-guide/download-install-aem-sites-templates-cs.md) for Cloud Service.

In the Map console, the preset configuration options for composite component mapping are organized under the following tabs:

- General
- Content
- Topic list
- Cross map references 

![New ](images/aem-sites-new-config.png){width="650" align="left"}

**General**

The **General** tab contains the following configuration options:

| AEM Sites options | Description |
| --- | --- |
|Use site path|Use this option to publish your content to an Experience Manager Site.|
|Site path|**This option appears if you select **Use site path** option**. Browse the predefined Experience Manager Site path or specify a custom path where you want the output to be published. The **Use Sites option** allows you to specify the entire publishing path even if the specified path has not been pre-created within the AEM Sites structure. In such cases, the system creates the necessary structure during the publishing process by using the selected map homepage template.<br><br>You can also use variables while setting the Site path. For details, view [Use variables for setting the Destination Path, Site Name, or File Name options](./generate-output-use-variables.md)|
|Map page template|**This option appears if you select **Use site path** option**. Select a template you want to apply for map home pages.|
|Site|Name of the Experience Manager Sites to which you want to publish your content. The options in the dropdown are populated based on the list of sites available in AEM Sites. <br>Select **Refresh** ![refreseh icon](images/navtitle-refresh-icon.svg) to fetch a fresh list of options and reflect the udpated data.|
| Publish Path | The path within your AEM repository where the output is stored. The Publish Path is populated with all the paths that contain pages created based on the Home Page template. The AEM Sites output of the DITA map is generated under this path.  For example, if you specify the Site as `AEMG-Docs` and the Publish Path as `aemg-docs-en/docs/product-abc.`, then the AEM Sites output is generated under the `aemg-docs-en/docs/product-abc/` node in `crx/de`.|
|Topic page template|Select the template you want to apply to all the output topics.|
|Generate page names based on|  **Topic filename**: Uses the DITA topic's file name to create the Site URL. <br> **Topic title**: Uses the DITA topic's title to create the Experience Manager Site names.|
| Cleanup previously generated pages| -  **Delete previously generated pages for topic removed from the map**: If the structure of the DTIA map changes, you can use this option to remove the previously generated pages for the removed topics. This feature is available only for full map publishing.<br><br>Let's say you have published a DITA map, which contains topics a.dita, b.dita, and c.dita. Before publishing the map again, you removed b.dita topic from the map. Now, if you have selected this option, then all content related to b.dita is removed from the AEM Sites output and only a.dita and c.dita are published.<br><br>**Note**: Information about deleted pages is also captured in the output generation logs. For more information about accessing the log files, [View and check the log file](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). <br><br>**Caution**: On deleting the topics, the pages become unavailable from the published site. So, before the topics are deleted, a warning appears. You must confirm to delete them.<br><br>- **Delete all pages created by other sources at this path**: If you select this option, all pages published on this path from other maps, individual topics, or any other source are deleted. The pages also become unavailable from the published site. So, before the topics are deleted, a warning appears. You must confirm to delete them.|
| Post Generation Workflow | When you choose this option, a new Post Generation Workflow drop-down list is displayed containing all workflows configured in AEM. You must select a workflow that you want to execute after completion of the output generation workflow. |

**Content**

The **Content** tab contains the following configuration options:

| AEM Sites options | Description |
| --- | --- |
| Use Baseline | If you have created a Baseline for the selected DITA map, select this option to specify the version that you want to publish.<br><br>View [Work with Baseline](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) for more details. |
| Conditional filtering | Select one of the following options:<br><br>**None**: Select this option if you do not want to apply any condition on the published output.<br>**Using DITAVAL**: Select DITAVal file(s) to generate conditionalized content. You can select multiple DITAVal files using the browse dialog or by typing file path. Use the cross icon near the file name to remove it. DITAVal files are evaluated in the order specified, so the conditions specified in the first file take precedence over the matching conditions specified in later files. You can maintain the file order by adding or deleting files. If the DITAVal file is moved to some other location or is deleted, it is not automatically deleted from the map dashboard. You need to update the location in case files are moved or deleted. You can hover over the file name to view the path in the AEM repository where the file is stored. You can only select DITAVal files and an error is displayed if you select any other file type.<br>**Condition preset**: Select a condition preset from the drop-down to apply a condition while publishing the output. This option is visible if you have added a condition for the DITA map file. The conditional settings are available in the Condition Presets tab of the DITA map console. To know more about condition preset, view [Use condition presets](generate-output-use-condition-presets.md#id1825FL004PN). |
| Additional DITA-OT Command Line Arguments | Specify the additional arguments that you want DITA-OT to process while generating output. For details about the command-line arguments supported in DITA-OT, view [DITA-OT documentation](https://www.dita-ot.org/). |
| Metadata <br> <br>File (Assets) Properties | Select the properties that you want to process as metadata. These properties are set from the Properties page of the DITA map or bookmap file. The properties you select from the dropdown list appear under the **File Properties** field. Select the cross icon next to the property to remove it. <br><br>**Note**: The metadata properties are case-sensitive.<br><br>*If you have selected a Baseline, then the values for the properties are based on the version of the selected Baseline.<br>* If you have not selected a Baseline, then the values for the properties are based on the latest version.<br><br>You can also pass on the metadata to the output using DITA-OT publishing. For more details view, [Pass on the metadata to the output using DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Note**: If you have not defined the `cq:tags` in the Properties option, then the values for `cq:tags` are picked from the current working copy even if you have selected a Baseline for publishing. |
| Metadata <br> <br>Use map properties as fallback | If selected, the properties defined for the map file are also copied into the topics where such properties are not defined. Consider the following points while using this option:<br><br>*Only String, Date, or Long (singe and multi-valued) properties can be passed on to the AEM Site pages.<br>* The metadata values for a String type property does not support any special characters (such as `@, #, " "`).<br>* This option should be used along with the `Properties` option. |

**Topic list**

The **Topic list** tab displays the list of topics present in the current working copy of the DITA map. By default, all topics are included. You can select specific topics and generate the AEM Sites output only for them. For example, you have updated some topics so you can publish only those topics instead of publishing the entire DITA map.

![aem sites topic list](images/aem-presets-topic-list.png) {align="left"}


>[!NOTE] 
>
> When a Baseline is selected in the **Content** tab, the Topic list displays topics and their versions from the attached Baseline. Alos, the incremental publishing from the Topics list should be used only when there is no change to the structure of the map. If there is a change in the map structure/TOC, then the entire map should be published once to update the TOC.

**Cross map references**

This list contains topics containing cross-map references with `scope ="peer"`. You can specify the publishing context for a list of cross map references with `scope="peer"` to topics available in other DITA maps. This tab appears if you use the Experience Manager Guides (UUID) version. 

For more details, refer to the [Working with linked topics](#working-with-linked-topics) section below.

Once configured, save the changes done to the preset, and select **Generate** to generate AEM Sites for the corresponding map. 

>[!NOTE]
>
> If you are publishing content to AEM sites for the first time, it is recommended to publish the pages at the site level. This ensures the output is displayed correctly on the **Publish** instance without any CSS disruption.

## Use legacy component mapping

The steps to create the AEM Sites preset using legacy component mapping are the same as those outlined in [Composite component mapping](#use-composite-component-mapping) section above. However, while creating the preset, ensure that you select the **Use legacy component mapping** option in the **New output preset** dialog.

![](images/aem-sites-output-legacy.png) {width="300" align="left"}

In the Map console, the preset configuration options for legacy component mapping are organized under the following tabs:

- General
- Content
- Cross map references 

![New ](images/aem-sites-preset-legacy-config.png){width="500" align="left"}

**General**

The **General** tab contains the following configuration options:

| AEM Sites options | Description |
| --- | --- |
| Site Name | A site name where the output is stored in your AEM repository.<br><br>A node in the AEM repository is created with the name specified here. If you do not specify the Site Name, then the site node is created with the DITA map file name.<br><br>The Site Name you specify here is also used as the title in the browser tab.<br><br>You can also use variables while setting the Site Name. For details, view [Use variables for setting the Destination Path, Site Name, or File Name options](./generate-output-use-variables.md) |
| Output path | The path within your AEM repository where the output is stored. While generating the final output, the Site name and Output path are combined. For example, if you specify the Site name as `user-guide` and the Output Path as `/content/output/aem-guides`, then the final output is generated under the `/content/output/aem-guides/user-guide` node.<br><br>You can also use variables while setting the output path. For details, view [Use variables for setting the Destination Path, Site Name, or File Name options](./generate-output-use-variables.md) |
| Existing output pages | Select the **Overwrite Content** option to overwrite content in the existing pages. This option only overwrites content present under the content and head nodes of the page. This option enables blended publishing of content. Selecting this option provides an option to select deleting orphan pages from the published output. This is also the *default* option for creating the AEM Sites output.<br><br>Select the **Delete and Create** option to force delete any existing pages during publishing. This option deletes the page node along with its content and all child pages under it. Use this option if you have changed the design template of your output preset or if you want any extra pages already present in the destination to be removed. |
|Delete previously generated pages for topics removed from the map| If the structure of the DTIA map changes, you can use this option to remove the previously generated pages for the removed topics. This feature is available only for full map publishing.<br><br>Let's say you have published a DITA map, which contains topics a.dita, b.dita, and c.dita. Before publishing the map again, you removed b.dita topic from the map. Now, if you have selected this option, then all content related to b.dita is removed from the AEM Sites output and only a.dita and c.dita are published.<br><br>**Note**: Information about deleted pages is also captured in the output generation logs. For more information about accessing the log files, [View and check the log file](generate-output-basic-troubleshooting.md#id1821I0Y0G0A__id1822G0P0CHS). <br><br>**Caution**: On deleting the topics, the pages become unavailable from the published site. So, before the topics are deleted, a warning appears. You must confirm to delete them.|
| Design | Select the design template that you want to use to generate the output.<br><br>For details about how to use custom design templates to generate output, contact your publishing administrator. |
| Post Generation Workflow | When you choose this option, a new Post Generation Workflow drop-down list is displayed containing all workflows configured in AEM. You must select a workflow that you want to execute after completion of the output generation workflow. |
| Retain temporary files | Select this option to retain the temporary files generated by DITA-OT. If you are experiencing errors while generating output through DITA-OT, select this option to retain the temporary files. You can then use those files to troubleshoot output generation errors.<br> <br>  After generating the output, select the **Download temporary files** ![download temporary files icon](images/download-temp-files-icon.svg) icon to download the ZIP folder containing the temporary files. <br><br> **Note**: If file properties are added during generation, the output temporary files also include a *metadata.xml* file containing those properties. | 

**Content**

![New ](images/aem-sites-content-tab.png){width="650" align="left"}

The **Content** tab contains the following configuration options:

| AEM Sites options | Description |
| --- | --- |
| Use Baseline | If you have created a Baseline for the selected DITA map, select this option to specify the version that you want to publish.<br><br>View [Work with Baseline](./web-editor-baseline.md) for more details. |
| Conditional filtering | Select one of the following options:<br><br>**None**: Select this option if you do not want to apply any condition on the published output.<br>**Using DITAVAL**: Select DITAVal file(s) to generate conditionalized content. You can select multiple DITAVal files using the browse dialog or by typing file path. Use the cross icon near the file name to remove it. DITAVal files are evaluated in the order specified, so the conditions specified in the first file take precedence over the matching conditions specified in later files. You can maintain the file order by adding or deleting files. If the DITAVal file is moved to some other location or is deleted, it is not automatically deleted from the map dashboard. You need to update the location in case files are moved or deleted. You can hover over the file name to view the path in the AEM repository where the file is stored. You can only select DITAVal files and an error is displayed if you select any other file type.<br>**Condition preset**: Select a condition preset from the drop-down to apply a condition while publishing the output. This option is visible if you have added a condition for the DITA map file. The conditional settings are available in the Condition Presets tab of the DITA map console. To know more about condition preset, view [Use condition presets](generate-output-use-condition-presets.md#id1825FL004PN). |
| Metadata <br> <br>File (Assets) Properties | Select the properties that you want to process as metadata. These properties are set from the Properties page of the DITA map or bookmap file. The properties you select from the dropdown list appear under the **File Properties** field. Select the cross icon next to the property to remove it. <br><br>**Note**: The metadata properties are case-sensitive.<br><br>*If you have selected a Baseline, then the values for the properties are based on the version of the selected Baseline.<br>* If you have not selected a Baseline, then the values for the properties are based on the latest version.<br><br>You can also pass on the metadata to the output using DITA-OT publishing. For more details view, [Pass on the metadata to the output using DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA).<br><br>**Note**: If you have not defined the `cq:tags` in the Properties option, then the values for `cq:tags` are picked from the current working copy even if you have selected a Baseline for publishing. |
| Metadata <br> <br>Use map properties as fallback | If selected, the properties defined for the map file are also copied into the topics where such properties are not defined. Consider the following points while using this option:<br><br>*Only String, Date, or Long (singe and multi-valued) properties can be passed on to the AEM Site pages.<br>* The metadata values for a String type property does not support any special characters (such as `@, #, " "`).<br>* This option should be used along with the `Properties` option. |

**Cross map references**

This list contains topics containing cross-map references with `scope ="peer"`. You can specify the publishing context for a list of cross map references with `scope="peer"` to topics available in other DITA maps. This tab appears if you use the Experience Manager Guides (UUID) version. 

For more details, refer to the [Working with linked topics](#working-with-linked-topics) section below.

## Working with linked topics

Experience Manager Guides allows you to create topic references using the `peer @scope`. You can then define the publishing context of these references from the AEM Sites presets and finally generate the output of the linked topics. 

For more details, view [Generate output of linking topics from other maps](../user-guide/generate-output-aem-site.md#generate-output-linking-topics-from-other-maps).


Perform the following steps to specify the publishing context for cross-linked files:

1. Open the **Cross map references** tab. To view this tab,  ensure that the `<xrefs>` have unique IDs. Unique IDs for `<xrefs>` will be automatically generated on editing/saving the older content if the ID isn't there.

    You'll not be able to view the cross-map linking in the following cases:
    - For the presets created before the 4.6 release, the Cross references tab is disabled and a tool tip, **Refer to Map dashboard**, appears.
    - For presets created from the map dashboard, **Refer to Map dashboard** tooltip appears.
    - For OOTB presets, **Refer to Map dashboard** tooltip appears.
    - For global presets, create a local copy of this global preset to set cross map references.


1. A list of topics and their references is displayed

    >[!NOTE]
    >
    >The **Cross map references** tab shows topics that are linked using the `scope="peer"` only. For links with `scope="local"`, you don't need to specify the publishing context.

    All linked topics have their latest output preset and map selected by default. The publishing context for all the linked topics is set to `<Most recently generated>` map by default.
 
    ![Cross map references](images/aem-sites-preset-cross-map-references.png)

1. If you want to use the most recently published output of each dependent file in the map, select **Use most recently generated** publish context for all dependent topics.
You should publish the map selected as the parent map before publishing the map containing linked topics. If the map with linked topics isn't published, the links appear as normal text instead of hyperlinks in the AEM Sites output.
You should select the same type of AEM Sites preset for the linked topic. For example, if the current AEM Sites preset uses legacy component mapping, then select a similar AEM Sites preset of the linked topic. 
1. In the Parent Map drop-down list, select the map file with whose output you want to link the current map's output.
Selecting a map file shows the map's UUID in the Parent Map UUID column. The Output Presets associated with the chosen map are listed in the Parent Map's Preset list. For example, Topic 1 in Map A contains a reference to Topic 2. Topic 2 can be present in single or multiple maps. You can select the parent map and a specific preset or the most recently published output for each link.

1. If the same topic is referred to more than once in a file, then you can add a different publishing context for each instance. This provides greater flexibility and control over their content. For example, Topic 3 is present in both Map B and Map C. Topic 1 contains two references to Topic 3. You can choose Map B as a parent map for the first link and Map C as the parent for the second link.

1. In the Parent Map's Preset drop-down list, select the output preset with which you want to link the current map's output.
    >[!NOTE]
    >
    > The different AEM Sites presets of the current map appear in the dropdown list. If you don't select a preset, a warning icon appears, and the output generation, fails.

1. Select the required map and its output preset for all source topics and select **Generate**.




**Parent topic:** [Understanding the output presets](generate-output-understand-presets.md)