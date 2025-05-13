---
title: Processing and reprocessing assets
description: Learn how to process assets
feature: processing 
role: Admin
level: Experienced
---
# Processing or reprocessing assets

In data-intensive workflows such as publishing, efficient asset management is crucial for maintaining performance and reliability. The process of processing or reprocessing assets is specifically designed to handle user-specific assets that require intensive data operations. This approach addresses two primary scenarios: when the initial processing of assets encounters errors, or when files were not processed at all due to the absence of a post-processing trigger. By enabling targeted, folder-level processing, users can isolate and process only the necessary assets, thereby avoiding the overhead of unnecessary computations. This selective approach significantly enhances performance, reducing the time required for critical operations like publishing and report generation. Overall, it contributes to greater efficiency and speed in handling complex data tasks.

## Processing the assets

Follow the below mentioned steps to process or reprocess the assets:

1. Select the Adobe Experience Manager logo at the top and choose **Tools**.
1. In the **Tools** panel select **Guides**.
1. Select the **Asset Processor** Tile.

    ![flow-asset-processor](images/flow-asset-processor.png){width="550" align="left"}

1. The Guides Asset Processor window opens with the following details:

    -   **Execution ID**: It is the unique Id for each reprocessing task that you perform.

    -   **Folder**: Shows the folder selected for migration.

    -   **Excluded Folders**: Points to the folder that is excluded from migration.

    -   **Start time:** Shows the date and time the migration process is initiated.

    -   **End Time**: Shows the date and time the migration process ends.

    -   **Status**: Points to the status of migration as In progress, Completed or Cancelled.

    ![Guides-asset-processor](images/guides-asset-processor.png){width="550" align="left"}

1. Select **New Process** tab on the top right corner of the window to start a new processing task.

    ![New-process-asset-processor](images/new-process-asset-processor.png){width="550" align="left"}

1. Select the folder you want to process or reprocess. You can also select the folders (within the parent selected folder) which you want to exclude or ignore.

    >[!NOTE]
    >
    > Only one folder can be selected at a given time for processing. For specific operations, you can exclude multiple folders.

1. Select **Create**. You get a pop-up showing **Success and the Process triggered successfully** as shown in the snippet. The same is reflected in the list. You can see the status of the migration process on the window.

    ![Message-asset-processor](images/message-asset-processor.png){width="550" align="left"}


## Additional options for the processing tasks   

Additional options are available for the processing task once it has been initiated. You can access these options by hovering over the Execution ID of your task. Details of these options are provided below:

- **Restart** : Restarts the asset processing task.

    ![restart-asset-processor](images/restart-asset-processor.png){width="550" align="left"}

- **View logs**: Shows the logs for the asset processing task.

    ![logs-asset-processor](images/logs-asset-processor.png){width="550" align="left"}


