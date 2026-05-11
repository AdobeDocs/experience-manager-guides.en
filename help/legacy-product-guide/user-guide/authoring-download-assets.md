---
title: Download files
description: Learn how to download files from the DITA map console in AEM Guides and export a DITA map file in AEM repository.
feature: Content Management
role: User
hide: true
exl-id: b04a0abe-a029-44ac-b8f4-138d78908d44
TQID: https://experienceleague.adobe.com/iCZL0VgkFqcKWqnTpNWkXvJUXyMbLUL6wENBvVXe40Y
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
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
    internal-label: Map console
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Download files {#id216MC0H0BE8}

You can download assets including DITA and non-DITA files. There are multiple ways in which you can download assets, some methods are native to AEM and others are supported by AEM Guides. For native AEM assets download information, see [Download assets from Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/manage/download-assets-from-aem.html) in AEM documentation. The following section explains the mechanism of downloading files via DITA map console in AEM Guides.

## Export a DITA map file 

Once you have the DITA map file in the AEM repository, you can download the map file along with its dependents. This gives you the flexibility to share the complete map file for offline editing, validation, review, or simply creating a backup.

Perform the following steps to download a DITA map file along with its dependent files:

1.  In the Assets UI, navigate to the DITA map that you want to download.

1.  Click on the DITA map to open it in DITA map console.

1.  Select the **Topics** tab to see a list of topics available in the DITA map.

1.  In the main toolbar, click **Download Map**.

    The Download Map dialog appears.

    ![](images/download-map.png){width="300"}

1.  Click **Download**. In the Download Map dialog, you can choose the following options:

    -   **Use Baseline**: Select this option to get a list of Baselines created for the DITA map. If you want to download the map file and its contents based on a specific Baseline, select the Baseline from the drop-down list. For more details about working with Baselines, see [Work with Baseline](generate-output-use-baseline-for-publishing.md#).
    -   **Flatten File Hierarchy**: Select this option to save all referenced topics and media files in a single folder.
    >[!NOTE]
    >
    > You can also download the map file without selecting any option. In that case, the last persisted version of the referenced topics and media files are downloaded.

1.  After you click the **Download** button, the map download request is queued. You will receive the following notification once the map is ready to download.

    ![](images/download-map-prompt.png){width="550"}

    -   Click **Download** to download the map file in.zip format.

    -   Click **Download Later** to download the map file at a later time. The download link can be accessed from the AEM notification Inbox. Click the generated map notification in the Inbox to download the map in .zip format.

    >[!NOTE]
    >
    > By default, the downloaded maps remain for five days in the AEM notification Inbox.

![](images/download-map-inbox.png){width="300"}

Once the map is downloaded, you can select the map and use the Open icon on the top to open the selected report.

**Parent topic:**[Manage content](authoring.md)
