---
title: Custom
description: Learn how to create custom preset from the web editor and map dashboard. Configure a custom output preset in AEM Guides.
feature: Publishing
role: User
hide: yes
exl-id: b96e6599-f8f3-491a-8b8f-fcb1e0f58aae
---
# Custom {#id205BEF00PX0}

The Custom output presets are available for custom DITA-OT plug-ins. You can create a custom DITA-OT output preset to publish output using your custom DITA-OT plug-in.

You can create the Custom preset in two ways:

**From the Web Editor:** In the Repository panel, open the DITA map file in Map View, then in the Output tab, select the + icon to create an output preset, and then select Custom from the type drop-down in the Add preset dialog.

In the Web editor the configurations have been organized under General and Advanced tabs:

**General**

The **General** tab contains the following configurations:

-   DITA-OT Command Line Arguments
-   Transformation Name
-   File Name
-   Output Path
-   Apply Conditions Using \(If the conditions are defined for a map\)
-   Use Baseline \(If a baseline is created for a map\)
-   Post Generation Workflow

**Advanced**

The Advanced tab contains the following configurations:

-   Retain temporary files
-   File Properties

For details, refer to [Custom configuration](#id231KJA00REJ).

**From the map dashboard**

To open output presets for PDF, click on a DITA map file from the Assets UI, then click on Output Presets, and then click on the HTML5 option. In the Map dashboard, click **Edit** on the top to update the various configurations, and then click **Save**.

**Custom configuration**

The following options are available for the Custom output preset:

| Custom output options | Description |
| --- | --- |
| Output Type | The type of output you want to generate. To generate output using custom DITA-OT plug-in, choose the Custom option. |
| Setting Name | Give a descriptive name for the output settings you are creating. For example, you can specify _Internal customers output_ or _end-users output_. |
| DITA-OT Command Line Arguments | Specify the additional arguments that you want DITA-OT to process while generating output. For details about the command-line arguments supported in DITA-OT, see [DITA-OT documentation](https://www.dita-ot.org/). |
| Transformation Name | Specify the type of output you want to generate. This is required if you want to generate output using your own custom plug-in, which is integrated in the DITA-OT plug-in. For example, if you want to generate XHTML output, specify `xhtml`. For a list of transformations available in DITA-OT, see [DITA-OT transformations (output formats)](http://www.dita-ot.org/2.3/user-guide/AvailableTransforms.html) in OASIS DITA-OT User Guide. |
| File Name | Specify the file name with which you want to save the output.<br><br>**Note**: If you do not provide a file name, then the DITA map's title is used to generate the final output file name. If the map does not have a title, then the DITA map's file name is used to name is the final output. The file name is sanitized using the rules configured in the system to handle any invalid character. |
| Apply conditions using | Select one of the following options:<br><br>* **None applied**: Select this option if you do not want to apply any condition on the published output.<br>* **DITAVal file**: Select DITAVal file(s) to generate personalized content. You can select multiple DITAVal files using the browse dialog or by typing file path. Use the cross icon near the file name to remove it. DITAVal files are evaluated in the order specified, so the conditions specified in the first file take precedence over the matching conditions specified in later files. You can maintain the file order by adding or deleting files. If the DITAVal file is moved to some other location or is deleted, it is not automatically deleted from the map dashboard. You need to update the location in case files are moved or deleted. You can hover over the file name to see the path in the AEM repository where the file is stored. You can only select DITAVal files and an error is displayed if you have selected any other file type.<br>* **Condition preset**: Select a condition preset from the drop-down to apply a condition while publishing the output. The option is visible if you have added a condition present in the Condition Presets tab of the DITA map console. To know more about condition preset, see [Use condition presets](generate-output-use-condition-presets.md#id1825FL004PN). |
| Destination Path | The path within your AEM repository where the EPUB output is stored. |
| Retain temporary files | Select this option to retain the temporary files generated by DITA-OT. If you are experiencing errors while generating output through DITA-OT, select this option to retain the temporary files. You can then use those files to troubleshoot output generation errors.<br> <br>  After generating the output, select the **Download temporary files** ![download temporary files icon](images/download-temp-files-icon.png) icon to download the ZIP folder containing the temporary files. <br><br> **Note**: If file properties are added during generation, the output temporary files also include a *metadata.xml* file containing those properties. | 
| Run Post Generation Workflow | When you choose this option, a new Post Generation Workflow drop-down list is displayed containing all workflows configured in AEM. You must select a workflow that you want to execute after completion of the output generation workflow.<br><br>**Note**: For more information about creating a custom post-output generation workflow, see _Customize post-output generation workflow_ in Install and configure Adobe Experience Manager Guides as a Cloud Service. |
| Use Baseline | If you have created a Baseline for the selected DITA map, select this option to specify the version that you want to publish.<br><br>See [Work with Baseline](generate-output-use-baseline-for-publishing.md#id1825FI0J0PF) for more detail. |
| File Properties | Select the properties that you want to process as metadata. These properties are set from the Properties page of the DITA map or bookmap file. The properties you select from the dropdown list appear under the **File Properties** field. Select the cross icon next to the property to remove it. <br><br>**Note**: You can also pass on the metadata to the output using DITA-OT publishing. For more details see, [Pass on the metadata to the output using DITA-OT](pass-metadata-dita-ot.md#id21BJ00QD0XA). |

**Parent topic:**[Understanding the output presets](generate-output-understand-presets.md)
