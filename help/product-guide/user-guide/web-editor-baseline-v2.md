---
title: Create and manage baselines from the Map console
description: Create and manage baselines from the map console in Adobe Experience Manager Guides. Learn how to create baselines on the basis of labels and apply filters to the baselines.
feature: Authoring, Features of Web Editor, Publishing
role: User
---
# New baseline

The enhanced Baseline feature introduces a modernized architecture that significantly improves the reliability, performance, and scalability of the AEM Guides baseline workflow. By optimizing how baseline data is stored and retrieved, this enhancement delivers faster operations, greater stability, and a more predictable editing experience; especially when working with large and complex document sets.

## Key Advantages

- Stores only essential baseline data, reducing system overhead
- Dynamically loads additional content as users scroll
- Improves performance and responsiveness for large baselines
- Supports pagination for efficient handling of extensive content
- Allows inclusion of files without labels for greater flexibility
- Provides a stable, reliable, and consistent baseline experience


## Migrating to new baseline 

Once you have the feature flag enabled from your customer success team for the new baseline, you need to migrate the existing baselines to the new enhanced baselines. 

Perform the following steps, to migrate the existing baseline to the new Baselines.

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

    ![flow-asset-processor](images/view-logs-baseline.png){align="left"}

    The log report provide details of the migration, including the number of maps migrated, baselines successfully migrated, and related details.      

    ![flow-asset-processor](images/logs-detail-baseline.png){align="left"}

>[!NOTE]
>
> No baseline edits should be made during migration, particularly in working copies, to prevent failures. Post‑migration, some baselines may require rebuilding if versions are missing.    

## Using the new baselines

- **Creating the baseline**: You can create a baseline from the Map console by performing the same steps as listed in [Create a Baseline](./web-editor-baseline.md#create-a-baseline).
- **Configuring the baseline for Manual update**: You can manually create a static baseline with a specific version of the topics and referenced content by performing the same steps as listed in [Configuring Baseline for Manual update](./web-editor-baseline.md#configuring-baseline-for-manual-update).
- **Configuring the baseline for Automatic update**: Select this option for baseline creation to automatically pick the topics according to the label applied to them by performing the same steps as listed in [Configuring Baseline for Automatic update](./web-editor-baseline.md#configuring-baseline-for-automatic-update).
- Manage baseline: You can manage your existing baselines using the various features on the Baseline dashboard as mentioned in [Manage baselines](./web-editor-baseline.md#manage-baselines).
- Actions available for an existing baseline: This too is the same. For dynamic baselines we can now use Edit properties and Rebuild the baseline as shown below.
- Editing the version of the baseline: you can use the pencil icon to edit the baseline and change the selected version for the given baseline.




 
