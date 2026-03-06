---
title: Create and manage new baseline (Beta) from the Map console
description: Create and manage new baseline (Beta) from the map console in Adobe Experience Manager Guides. 
feature: Authoring, Features of Web Editor, Publishing
role: User
---
# Create and manage new Baseline (Beta) from Map console

>[!NOTE]
>
> This article applies to new Baseline (Beta) offering improved performance and stability available with the Experience Manager Guides 2026.03.0 release. To use this baseline, contact the Customer Success Team to have the feature enabled.

The enhanced Baseline feature introduces a modernized architecture that significantly improves the reliability, performance, and scalability of the AEM Guides baseline workflow. By optimizing how baseline data is stored and retrieved, this enhancement delivers faster operations, greater stability, and a more predictable editing experience; especially when working with large and complex document sets.

## Key advantages

- Stores only essential baseline data, reducing system overhead
- Dynamically loads additional content as users scroll
- Improves performance and responsiveness for large baselines
- Supports pagination for efficient handling of extensive content
- Allows inclusion of files without labels for greater flexibility
- Provides a stable, reliable, and consistent baseline experience

## Migrating to new Baseline (Beta)

Once you have the feature enabled from Customer Success Team, you need to migrate the existing baselines to the new Baseline (Beta). 

Perform the following steps, to migrate the existing baseline to the new Baseline (Beta).

1. Select the Adobe Experience Manager logo at the top and choose **Tools**.
1. In the **Tools** panel select **Guides**.
1. Select the **Bulk Processor** tile.

    ![flow-asset-processor](images/flow-asset-processor.png){align="left"}

    The Guides Bulk Processor window opens.    

1. Select **New Process** tab on the top right corner of the window to start a new processing task.

    The **New process** dialog opens.   

1. Provide the following details in the dialog:

    1. **Feature Type**: Select **Baseline** from the drop drown.
    1. **Select folders and files**: Navigate and choose one or multiple folders and files to process. 
    1. **Select folders to ignore**: Optionally, select sub-folders within the chosen parent folder to exclude from migrating.   

    ![new-process-baseline](images/new-process-baseline.png){align="left"}

1. Select **Create**. You get a pop-up showing **Asset processing triggered successfully**. You can see the status of the processing task on the window.
You can also select **View logs** to check and download the logs for the migration task. 

    ![view-logs-baseline](images/view-logs-baseline.png){align="left"}

    The log report provide details of the migration, including the number of maps migrated, baselines successfully migrated, and related details.      

    ![logs-detail-baseline](images/logs-detail-baseline.png){align="left"}

>[!NOTE]
>
> No baseline edits should be made during migration, particularly in working copies, to prevent failures. Post‑migration, some baselines may require rebuilding if versions are missing.    

## Using the new Baseline (Beta)

- **Creating the baseline**: You can create a baseline from the Map console by performing the same steps as listed in [Create a Baseline](./web-editor-baseline.md#create-a-baseline).
- **Configuring the baseline for Manual update**: You can manually create a static baseline with a specific version of the topics and referenced content by performing the same steps as listed in [Configuring Baseline for Manual update](./web-editor-baseline.md#configuring-baseline-for-manual-update).
- **Configuring the baseline for Automatic update**: Select this option for baseline creation to automatically pick the topics according to the label applied to them by performing the same steps as listed in [Configuring Baseline for Automatic update](./web-editor-baseline.md#configuring-baseline-for-automatic-update).
- **Manage baseline**: You can manage your existing baselines using the various features on the Baseline dashboard as mentioned in [Manage baselines](./web-editor-baseline.md#manage-baselines).
- **Actions available for an existing baseline**: You can also perform many operations on the baseline from the Options menu as listed in [Options menu for baseline](./web-editor-baseline.md#actions-available-for-an-existing-baseline). Additionally for dynamic baselines you can also use **Edit properties**  and **Rebuild** options from the Options menu. Using the Rebuild feature, you can trigger an update to your baseline whenever changes occur.

    ![rebuild-baseline](images/rebuild-baseline.png){align="left"}

- **Version management for baseline**: You can edit the version number for a baseline by selecting the Edit icon.

    ![edit-baseline-icon](images/edit-baseline-icon.png){align="left"}

    When you select **Edit** for a specific baseline, the **Edit version** dialog opens. Choose the required version and select **Update**. The baseline is then updated with the new version.

    ![edit-version-baseline](images/edit-version-baseline.png){align="left"}

- **Baseline filters**: Using the Filters icon in the Baseline Filters panel you can apply filters on the baseline opened in the baseline editing window. For more details, view [Filters in baseline](./web-editor-baseline.md#baseline-filters)    








 
