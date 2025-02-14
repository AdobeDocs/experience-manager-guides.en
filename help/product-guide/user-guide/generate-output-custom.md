---
title: Custom
description: Learn how to create custom preset from the map console and map dashboard. Configure a custom output preset in AEM Guides.
exl-id: 1bb14411-ec94-4960-92ba-3b2ff7a29932
feature: Publishing
role: User
---
# Custom {#id205BEF00PX0}

The Custom output presets are available for custom DITA-OT plug-ins. You can create a custom DITA-OT output preset to publish output using your custom DITA-OT plug-in.

You can create the Custom preset in two ways:

- [Create the Custom preset from the Map console](#create-the-custom-preset-from-the-map-console)
- [Create the Custom preset from the Map dashboard](#create-the-custom-preset-from-the-map-dashboard) 

## Create the Custom preset from the Map console

Perform the following steps to create the Custom preset from the Map console:

1. [Open a DITA map file in the Map console](./open-files-map-console.md). 

    You can also access the map file from the **Recent files** widget in the [Overview section](./intro-home-page.md#overview). The selected map file would open in Map console. 
1. In the **Output presets** tab, select the + icon to create an output preset. 
1. Select **Custom** from the Type dropdown in the **New output preset** dialog box. 
1. In the **Name** field, provide a name to this preset.
1. Select the **Add to current folder profile** option to create an output preset within the current folder profile. The ![folder profile icon](images/global-preset-icon.svg) indicates a folder-profile-level preset.  

   Learn more about [Manage Global and Folder profile output presets](./web-editor-manage-output-presets.md).

 1. Select **Add**.   

    The Custom preset is created.

    ![](images/custom-preset-dialog.png){width="300" align="left"}

In the Map console, the preset configuration options are organized under the **General** and **Advanced** tabs. 

![](images/custom-preset-config.png){width="800" align="left"}

The **General** tab contains the following configuration options:

- DITA-OT command line arguments
- Transformation name
- File name
- Output path
- Conditional filtering \(If the conditions are defined for a map\)
- Use baseline \(If a baseline is created for a map\)
- Post generation workflow

**Advanced**

The Advanced tab contains the following configuration options:

- Retain temporary files
- File properties 

For details on preset configuration options, refer to the [Custom preset configuration](#custom-preset-configuration) section.


## Create the Custom preset from the Map dashboard

Perform the following steps to create the Custom preset from the Map dashboard:

1. In the Assets UI, navigate to and select the DITA map to open it in Map dashboard.
1. Ensure that the **Output Presets** tab is selected.
1. Select **Create** in the toolbar.

    A new output preset creation form is displayed.

    ![](images/new-output-preset-map-dashboard.png){width="650" align="left"}

1.  Enter the required configuration details for the Custom preset. 
1.  Select **Done** to save the preset settings.

For details on preset configuration options, refer to the [Custom preset configuration](#custom-preset-configuration) section.

## Custom preset configuration

Configuration options vary slightly depending on whether you are configuring the preset from the Map console or the Map dashboard. Some options apply only to the Map dashboard, while others apply to both.

In cases where the same configuration has two different field labels, a **/** separates them in the table below. The first represents the label in the Map console, and the second represents the label in the Map dashboard. 

For example, **Output path/Destination Path** - Here, **Output path** is the label used in the Map console, while **Destination Path** is the label used in the Map dashboard for the same configuration.

| Custom output options | Description |
| --- | --- |
| Output Type (*Applicable for Map dashboard only*) | The type of output you want to generate. To generate output using custom DITA-OT plug-in, choose the Custom option. |
| Setting Name (*Applicable for Map dashboard only*) | Give a descriptive name for the output settings you are creating. For example, you can specify _Internal customers output_ or _end-users output_. |
| DITA-OT command line arguments | Specify the additional arguments that you want DITA-OT to process while generating output. For details about the command-line arguments supported in DITA-OT, view [DITA-OT documentation](https://www.dita-ot.org/). |
| Transformation name | Specify the type of output you want to generate. This is required if you want to generate output using your own custom plug-in, which is integrated in the DITA-OT plug-in. For example, if you want to generate XHTML output, specify `xhtml`. For a list of transformations available in DITA-OT, view [DITA-OT transformations (output formats)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) in OASIS DITA-OT User Guide. |
| File Name | Specify the file name with which you want to save the output.<br><br>**Note**: If you do not provide a file name, then the DITA map's title is used to generate the final output file name. If the map does not have a title, then the DITA map's file name is used to name is the final output. The file name is sanitized using the rules configured in the system to handle any invalid character. |
| Conditional filtering/Apply conditions using | Select one of the following options:<br><br>* **None applied**: Select this option if you do not want to apply any condition on the published output.<br>* **DITAVal file**: Select DITAVal file(s) to generate personalized content. You can select multiple DITAVal files using the browse dialog or by typing file path. Use the cross icon near the file name to remove it. DITAVal files are evaluated in the order specified, so the conditions specified in the first file take precedence over the matching conditions specified in later files. You can maintain the file order by adding or deleting files. If the DITAVal file is moved to some other location or is deleted, it is not automatically deleted from the map dashboard. You need to update the location in case files are moved or deleted. You can hover over the file name to view the path in the AEM repository where the file is stored. You can only select DITAVal files and an error is displayed if you have selected any other file type.<br>* **Condition preset**: Select a condition preset from the drop-down to apply a condition while publishing the output. The option is visible if you have added a condition present in the Condition Presets tab of the DITA map console. To know more about condition preset, view [Use condition presets](generate-output-use-condition-presets.md#id1825FL004PN). |
| Output path/Destination Path | The path within your AEM repository where the EPUB output is stored. |
| Retain temporary files | Select this option to retain the temporary files generated by DITA-OT. If you are experiencing errors while generating output through DITA-OT, select this option to retain the temporary files. You can then use those files to troubleshoot output generation errors.<br> <br>  After generating the output, select the **Download temporary files** ![download temporary files icon](images/download-temp-files-icon.png) icon to download the ZIP folder containing the temporary files. <br><br> **Note**: If file properties are added during generation, the output temporary files also include a *metadata.xml* file containing those properties. | 
| Run post generation workflow | When you choose this option, a new Post Generation Workflow drop-down list is displayed containing all workflows configured in AEM. You must select a workflow that you want to execute after completion of the output generation workflow.<br><br>**Note**: For more information about creating a custom post-output generation workflow, view _Customize post-output generation workflow_ in Install and configure Adobe Experience Manager Guides as a Cloud Service. |
| Use Baseline | If you have created a Baseline for the selected DITA map, select this option to specify the version that you want to publish.<br><br> View [Work with Baseline](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) for more detail. |
| File properties/Properties | Select the properties that you want to process as metadata. These properties are set from the Properties page of the DITA map or bookmap file. The properties you select from the dropdown list appear under the **File Properties** field. Select the cross icon next to the property to remove it. <br><br>**Note**: You can also pass on the metadata to the output using DITA-OT publishing. For more details view, [Pass on the metadata to the output using DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Parent topic:**[Understanding the output presets](generate-output-understand-presets.md)

