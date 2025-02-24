---
title: Generate output 
description: Generate output for a DITA map from the map console and Map dashboard in AEM Guides. 
exl-id: d6cbd44c-e74c-4192-bcc4-fb7752c59508
feature: Publishing
role: User
---
# Generate output  

There are two ways to generate ouput for a DITA map:

- [Generate output for a DITA map from the Map conosle](#generate-output-for-a-dita-map-from-the-map-console) 
- [Generate output for a DITA map from the Map dashboard](#generate-output-for-a-dita-map-from-the-map-dashboard)

## Generate output for a DITA map from the Map console 

Perform the following steps to generate output for a DITA map using Map conosle:

1. [Open a map file in the Map console](./open-files-map-console.md).
2. The DITA map console is displayed with the list of **Output presets** available to generate output.

3. Open the preset that you want to use for generating the output, and select **Generate output** to start the generation process.

    <img src="images/generate-output-pdf.png" alt="metadata tab" width=600>

    Or, hover over the preset and select **Generate** from the preset context menu.
    
    
    <img src="images/generate-preset-map-console.png" alt="metadata tab" width=600>

Once the output generation is complete, select **View output** to view the output.  
    
A **Success** dialog box is visible at the lower-right corner of the screen.
    
If an output is not successful, the below error message is displayed.
    
<img src="images/error-log.png" alt ="error log" width =250>
    
To view the error log, select **Dismiss**, hover over the selected preset tab, and select **View log** from the preset context menu.

## Generate output for a DITA map from the Map dashboard 

Perform the following steps to generate output for a DITA map using Map dashboard:

1.  In the Assets UI, navigate to and select the DITA map file that you want to publish.

    The DITA map console appears with the list of Output Presets available to generate output.

1.  Select one or multiple Output Presets that you want to use for generating the output.

    ![](images/generate-multiple-outputs-uuid.png){width="800" align="left"}

1.  Select the **Generate** icon to start the output generation process.


You can view the current status of the output generation request in the **Outputs** tab. For more information, view [View the status of the output generation task](./generate-output-manage-process.md#view-the-status-of-the-output-generation-task).

>[!IMPORTANT]
>
> If an output generation process for a preset is either in the queue or in progress, you cannot initiate another output generation task for the same preset.

You can also generate the AEM Sites output for one or more topics, or the entire DITA map from the Map console. For more details, view [Generate Knowledge Base output](web-editor-article-publishing.md#id218CK0U019I).




**Parent topic:**[Output generation](generate-output.md)
