---
title: Download files
description: Learn how to download files from the DITA map console in AEM Guides and export a DITA map file in AEM repository.
exl-id: ae9eb355-d3ac-446a-958b-5f2da43f5533
feature: Content Management
role: User
TQID: https://experienceleague.adobe.com/xwz0wuugvwPsmIX78kuwv5te2NGcNTik-qoJvijRzzg
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
subfeature_v2:
  - id: a7bba4a6-624b-4427-a9b8-dd411a1bfd41
    internal-label: Map Editor
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
    internal-label: Map console
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Download files {#id216MC0H0BE8}

You can download assets including DITA and non-DITA files. There are multiple ways in which you can download assets, some methods are native to Adobe Experience Manager and others are supported by Adobe Experience Manager Guides. For native Adobe Experience Manager assets download information, view [Download assets from Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/download-assets-from-aem.html) in Adobe Experience Manager documentation. The following section explains the mechanism of downloading files in Experience Manager Guides.

## Download a DITA map file from the Editor 

Perform the following steps to download a DITA map file from the Editor:

1. Navigate to the DITA map that you want to download.
1. Select the DITA map to open it in the Editor.
    
1. In the Map view, select the **Options** icon and choose **Download map** from the list.  

    ![](images/download-map-option-editor.png)

    The **Download map** dialog is displayed. 

    ![](images/download-map-dialog-new.png){width="300"}

1. In the Download Map dialog, you can choose the following options:

    - **Use baseline**: Select this option to get a list of Baselines created for the DITA map. If you want to download the map file and its contents based on a specific Baseline, select the Baseline from the drop-down list. For more details about working with Baselines, view [Work with Baseline](generate-output-use-baseline-for-publishing.md#).
    
    - **File hierarchy options**: You can also use the file hierarchy dropdown to choose how the folder structure is handled for your downloaded map files. The available options are:
    
        - **Retain file hierarchy**: Select this option from the dropdown to retain the existing folder structure for the downloaded files. 
        - **Flatten file hierarchy**: Select this option from the dropdown to download all referenced topics and media files in a single folder.

        For each option, you can further specify how file names are handled for downloaded files. The following file name options are available:

        - **Use GUID file name**: Downloads the map file with GUID as file name.
        - **Use actual file name**: Downloads the map file with its original file name. When this option is used with Flatten file hierarchy, any duplicate file names in the map are automatically resolved by appending numeric suffixes (_2, _3, and so on) to ensure unique file names. 
       
    >[!NOTE]
    >
    > You can also download the map file without selecting any option. In that case, the last persisted version of the referenced topics and media files are downloaded.
    
    
1. Select **Download**.

    The map download request is queued. 
    
    ![](images/download-map-notification.png)

    You will receive the following notification once the map is ready to download.

    ![](images/download-map-success-message.png){width="550"}

1. Select **Download** to download the map file in `.zip` format. Or, download it later from the AEM inbox. 

    >[!NOTE]
    >
    > By default, the downloaded maps remain for five days in the Adobe Experience Manager notification Inbox.

Once the map is downloaded, you can select the map and use the Open icon on the top to open the downloaded content. To view the associated metadata of the downloaded map, open the `metdata.json` file included in the downloaded content. This file is available for both *File hierarchy* options - Flatten file hierarchy and Retain file hierarchy. 

## Download a DITA map file from the Map dashboard 

Once you have the DITA map file in the Adobe Experience Manager repository, you can download the map file along with its dependents. This gives you the flexibility to share the complete map file for offline editing, validation, review, or simply creating a backup.

Perform the following steps to download a DITA map file along with its dependent files:

1.  In the Assets UI, navigate to the DITA map that you want to download.

1.  Select the DITA map to open it in DITA map console.

1.  Select the **Topics** tab to view the list of topics available in the DITA map.

1.  In the main toolbar, select **Download Map**.

    The Download Map dialog appears.

    ![](images/download-map.png){width="300"}

1.  Select **Download**. In the Download Map dialog, you can choose the following options:

    -   **Use Baseline**: Select this option to get a list of Baselines created for the DITA map. If you want to download the map file and its contents based on a specific Baseline, select the Baseline from the drop-down list. For more details about working with Baselines, view [Work with Baseline](generate-output-use-baseline-for-publishing.md#).
    
    -   **Flatten File Hierarchy**: Select this option to save all referenced topics and media files in a single folder.     


    >[!NOTE]
    >
    > You can also download the map file without selecting any option. In that case, the last persisted version of the referenced topics and media files are downloaded.

1.  After you select the **Download** button, the map download request is queued. You will receive the following notification once the map is ready to download.

    ![](images/download-map-prompt.png){width="550"}

    -   Select **Download** to download the map file in.zip format.

    -   Select **Download Later** to download the map file at a later time. The download link can be accessed from the Adobe Experience Manager notification Inbox. Select the generated map notification in the Inbox to download the map in .zip format.

    >[!NOTE]
    >
    > By default, the downloaded maps remain for five days in the Adobe Experience Manager notification Inbox.

![](images/download-map-inbox.png){width="300"}

Once the map is downloaded, you can select the map and use the Open icon on the top to open the downloaded content. 

**Parent topic:**[Manage content](authoring.md)
