---
title: Generate PDF using DITA-OT
description: Learn how to create a PDF preset using DITA-OT from the map console and the map dashboard. Configure PDF output preset in AEM Guides.
feature: Publishing
role: User
exl-id: 6ac82dad-34af-4f9e-8b52-4e4f2eb982a4
---
# Create DITA-OT PDF output preset {#id205BE600HAH}

You can create the DITA-OT PDF output preset in two ways:

- [Create the DITA-OT PDF preset from the Map console](#create-the-dita-ot-pdf-preset-from-the-map-console)
- [Create the DITA-OT PDF preset from the Map dashboard](#create-the-dita-ot-pdf-preset-from-the-map-dashboard)

## Create the DITA-OT PDF preset from the Map console

Perform the following steps to create the PDF preset from the Map console:

1. [Open a DITA map file in the Map console](./open-files-map-console.md). 

    You can also access the map file from the **Recent files** widget in the [Overview section](./intro-home-page.md#overview). The selected map file would open in Map console. 
1. In the **Output presets** tab, select the + icon to create an output preset. 
1. Select **PDF** from the Type dropdown in the **New output preset** dialog box. 
1. In the **Name** field, provide a name to this preset.
1. In the **Generate PDF Using** field, select **DITA-OT**.
1. Select the **Add to current folder profile** option to create an output preset within the current folder profile. The ![folder profile icon](images/global-preset-icon.svg) indicates a folder-profile-level preset.  

   Learn more about [Manage Global and Folder profile output presets](./web-editor-manage-output-presets.md).

 1. Select **Add**.   

    The preset for PDF is created.

    ![](./images/pdf-preset-map-console.png){width="350" align="left"}

In the Map console, the preset configuration options for DITA-OT are organized under the **General** and **Advanced** tabs in Map console. 

![](./images/dita-ot-preset-config.png){width="350" align="left"}

**General**

The **General** tab contains the following configuration options:

- Output path
- DITA-OT command line arguments
- PDF file name 
- Conditional filtering \(If the conditions are defined for a map\)
- Use baseline \(If a baseline is created for a map\)
- Post generation workflow

**Advanced**

The **Advanced** tab contains the following configuration options:

-   Enable versioning
-   Retain temporary files
-   File properties

For details on preset configuration options, refer to the [PDF preset configuration](#pdf-preset-configuration) section.


## Create the DITA-OT PDF preset from the Map dashboard

Perform the following steps to create the PDF preset from the map dashboard:

1. In the Assets UI, navigate to and select the DITA map to open it in map dashboard.
1. Ensure that the **Output Presets** tab is selected.
1. Select **Create** in the toolbar.

    A new output preset creation form is displayed.

1.  Enter the required configuration details for the PDF preset. 
1.  Select **Done** to save the preset settings.

## PDF preset configuration

Configuration options vary slightly depending on whether you are configuring the preset from the Map console or the Map dashboard. Some options apply only to the Map dashboard, while others apply to both.

In cases where the same configuration has two different field labels, a **/** separates them in the table below. The first represents the label in the Map console, and the second represents the label in the Map dashboard. 

For example, **Output path/Destination Path** - Here, **Output path** is the label used in the Map console, while **Destination Path** is the label used in the Map dashboard for the same configuration.

| PDF options | Description |
| --- | --- |
| Output Type (*Applicable for Map dashboard only*) | The type of output you want to generate. To generate PDF output, choose the PDF option. |
| Setting Name (*Applicable for Map dashboard only*) | Give a descriptive name for the PDF output settings you are creating. For example, you can specify _Internal customers output_ or _end-users output_. |
| Generate PDF Using (*Applicable for Map dashboard only*)| Select **DITA-OT** to generate the PDF output. Select **FrameMaker Publishing Server** if your administrator has configured this option. Some of the configuration options vary when FMPS is selected. Also, FMPS configuration option is only available in Map dashboard. |
| Output path/Destination Path | The path within your AEM repository where the PDF is stored.<br>The Output path is set through the variable `${base_output_path}`, which is configured by the Administrator. To configure the Output path, view [Configure Base Output Location for  Publishing PDF](../native-pdf/configure-base-location-cs.md). You can also use some out-of-box variables to define the Output path, view [Use variables for setting the Destination Path, Site Name, or File Name options](generate-output-use-variables.md#id18BUG70K05Z). |
| DITA-OT Command Line Arguments | Specify the additional arguments that you want DITA-OT to process while generating output. For details about the command-line arguments supported in DITA-OT, view [DITA-OT documentation](https://www.dita-ot.org/). |
| Transformation name | Specify the type of output you want to generate. This is required if you want to generate output using your own custom plug-in, which is integrated in the DITA-OT plug-in. For example, if you want to generate XHTML output, specify `xhtml`. For a list of transformations available in DITA-OT, view [DITA-OT transformations (output formats)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) in OASIS DITA-OT User Guide. |
| PDF file name/File Name | Specify the file name with which you want to save the PDF.<br><br>You can also use variables while setting the PDF File Name. For more details about using variables, view [Use variables for setting the Destination Path, Site Name, or File Name options](generate-output-use-variables.md#id18BUG70K05Z).<br><br>**Note**: If you do not provide a file name, then the DITA map's title is used to generate the final PDF's file name. If the map does not have a title, then the DITA map's file name is used to name is the final PDF. The file name is sanitized using the rules configured in the system to handle any invalid character. |
| Conditional filtering/Apply Conditions using | Select one of the following options:<br><br>* **None applied**: Select this option if you do not want to apply any condition on the published output.<br>* **DITAVAL file**: Select DITAVAL file(s) to generate personalized content. You can select multiple DITAVAL files using the browse dialog or by typing file path. Use the cross icon near the file name to remove it. DITAVAL files are evaluated in the order specified, so the conditions specified in the first file take precedence over the matching conditions specified in later files. You can maintain the file order by adding or deleting files. You can also apply flags within a DITAVAL file to visually mark content. Each flag can include an image and be styled using formatting such as bold or italics. For more details on customizing flagging styles or resolving formatting conflicts, view [Use the DITAVAL editor](../user-guide/ditaval-editor.md). If the DITAVAL file is moved to some other location or is deleted, it is not automatically deleted from the map dashboard. You need to update the location in case files are moved or deleted. You can hover over the file name to view the path in the AEM repository where the file is stored. You can only select DITAVAL files and an error is displayed if you have selected any other file type. FrameMaker Publishing Server doesn't support multiple DITAVAL files.<br>* **Condition preset**: Select a condition preset from the drop-down to apply a condition while publishing the output. The option is visible if you have added a condition present in the Condition Presets tab of the DITA map console. To know more about condition preset, view [Use condition presets](generate-output-use-condition-presets.md#id1825FL004PN). |
| Run Post Generation Workflow | When you choose this option, a new Post Generation Workflow drop-down list is displayed containing all workflows configured in AEM. You must select a workflow that you want to execute after completion of the output generation workflow.<br><br>**Note**: For more information about creating a custom post-output generation workflow, view Customize post-output generation workflow in Install and configure Adobe Experience Manager Guides as a Cloud Service. |
| Use Baseline | If you have created a Baseline for the selected DITA map, select this option to specify the version that you want to publish.<br><br>View [Work with Baseline](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) for more detail. |
| Retain temporary files | Select this option to retain the temporary files generated by DITA-OT. If you are experiencing errors while generating output through DITA-OT, select this option to retain the temporary files. You can then use those files to troubleshoot output generation errors.<br> <br>  After generating the output, select the **Download temporary files** ![download temporary files icon](images/download-temp-files-icon.png) icon to download the ZIP folder containing the temporary files. The downloaded files would also include `system_config.xml` file that gives you information about author URL, local URL and publish URL. These URLs are configured in the AEM Externalization settings and are reflected in the `system_config.xml` file.<br><br> **Note**:  If file properties are added during generation, the output temporary files also include a *metadata.xml* file containing those properties.| 
| File properties | Select the properties that you want to process as metadata. These properties are set from the Properties page of the DITA map or bookmap file. The properties you select from the dropdown list appear under the **File Properties** field. Select the cross icon next to the property to remove it. <br><br>Note: You can also pass on the metadata to the output using DITA-OT publishing. For more details view, [Pass on the metadata to the output using DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |


**Parent topic:**[Understanding the output presets](generate-output-understand-presets.md)
