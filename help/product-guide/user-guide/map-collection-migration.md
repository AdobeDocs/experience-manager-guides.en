---
title: Migrate old map collections to new map collections
description: Learn how to migrate map collections from Old to New Map Collections
---

# Migrate old map collections to new map collections

If you already have map collections set up in the old format, you don't need to rebuild them from scratch when moving to the new experience. You can either recreate them manually, or use the built-in migration tool to move everything over in one step.

The migration tool, added as a new process type within the **Bulk processor**, reads your existing old map collections and automatically creates matching new map collections for you. This article walks you through how to run the migration and highlights a few key behaviors you should know before using it.

>[!NOTE]
>
> The Bulk activation feature is not migrated to the New map collection experience. Re-create any map collections used for Bulk Activation in the New map collection experience, if needed.

## Migrate to new map collection

Perform the following steps to migrate the old map collections to new map collections: 

1. Select the Adobe Experience Manager logo and choose **Tools**.
1. In the **Tools** panel, select **Guides**.
1. Select the **Bulk Processor** tile.

    ![Higlights the bulk processor tile](images/flow-asset-processor.png)

1. The Guides Bulk Processor window opens with the following details: 

    - **Feature type**: Shows the feature of the process that is being executed.

    - **Execution ID**: It is the unique ID for each migration task that you perform.        

    - **Created by**: Shows who created the task.

    - **Start time**: Shows the date and time the migration is initiated.

    - **End time**: Shows the date and time the migration ends.

    - **Status**: Shows the status of migration as In progress, Completed, or Failed.

    ![The Guides Bulk Processor window](images/guides-asset-processor-migration.png)    

1. Select **New process** tab on the upper-right corner of the window to start a new migration task.

    The **New process** dialog opens.

    ![New process dialog for migration](images/new-process-migration.png) {width="350"}    

1. Select **Map collection** from the **Feature type** dropdown.

    ![Map collection feature for the migration task](images/new-process.png) {width="350"}

1.  Select **Create**.   

This runs a single job that migrates all existing old map collections into new map collections. No additional configuration is required. 

>[!NOTE]
>
> If the migration task fails you can check the **View logs** option by hovering over the Execution ID.

## Important considerations

- **Re-running the migration:** If the migration process is run again, it does not check for changes in the source (old) map collections. It will unconditionally re-migrate or overwrite the new map collections.
- **Timestamps and uniqueness:** Each migrated map collection stores the timestamp from when it was first migrated. This timestamp is used to maintain uniqueness of the migrated record. Because of this, the migrated map collection will not reflect later updates made to the original (source) map collection, only the state at the time of migration is captured.


