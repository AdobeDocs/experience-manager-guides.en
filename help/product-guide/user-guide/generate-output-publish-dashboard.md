---
title: Manage publish tasks using the Publish Dashboard
description: Manage publish tasks using the Publish Dashboard in AEM Guides. Know how to access the publishing dashboard and cancel a publish task.
exl-id: d9e25e52-ba9d-4088-ac95-8df76b69f5d3
feature: Publishing
role: User
---
# Manage publish tasks using the Publish Dashboard {#id205CC08305Z}

When you have a large set of publishing tasks running on your system, it becomes practically impossible to check each DITA map individually to monitor its publishing task. Adobe Experience Manager Guides gives the administrators and publishers one unified view of all publishing tasks running in the system. A list of all active publishing tasks is available in the Publish Dashboard.

The Publish Dashboard gives a complete overview of all publishing tasks currently running in the system.

![](images/publish-dashboard.png){align="left"}

The Publish Dashboard contains the following details:

- **Map Title** - The title of a map file that is being currently published or is in the publish queue.

- **File Name** - The file name of the DITA map.

- **Output Preset** - Name of the output preset that is used to generate the output.

- **Initiated By** - Username of the user who initiated the publishing task.

- **Started On** - Date and time when the publishing task was started.

- **Elapsed Time** - Time since when the publishing task is running in the system.

- **Delete icon** - Cancel or terminate a publishing task.

The left panel in the Publish Dashboard provides the following filtering options:

- **Output Preset** - Select one or more output presets for which you want to view the currently active publishing tasks. In the following screenshot, the publishing tasks are filtered to show only those tasks that use the AEM Site output preset:

    ![](images/publish-dashboard-preset-filter.png){align="left"}

- **Initiated By** - Select a username from the list to show the publishing tasks initiated by the selected user.

- **Map** - Select a map file from the list to show the publishing tasks running for the selected map.

## Access the Publish Dashboard 

You can access **Publish Dashboard** directly from the [Experience Manager Guides Home page](./intro-home-page.md). Open the home page and select **Publish queue** option from the left panel.

>[!NOTE]
>
> Only an Administrator or Publisher can access the Publish Dashboard.

You can also access **Publish Dashboard** from the Adobe Experience Manager **Tools** page. To use this method, perform the following steps:

1.  Select the Adobe Experience Manager logo at the top and then select **Tools**.

1.  Select**Guides** from the list of tools.

1.  Select the **Publish Dashboard** tile.

    The Publish Dashboard opens with a list of all active publishing tasks in the system.

    If you select the File Name link, the DITA map dashboard of the selected map is shown.

    ![](images/publish-dashboard-click-filename-link.png){align="left"}


>[!NOTE]
>
> You can also access the Publish Dashboard from the **Outputs** tab while you generate output from the map dashboard. For more details, refer to [View the status of the output generation task](generate-output-for-a-dita-map.md#viewing_output_history).

## Cancel a publishing task 

Perform the following steps to cancel an output generation task from the Publish Dashboard:

1.  [Access the Publish Dashboard](#access-the-publish-dashboard).

1.  From the list of active publishing tasks, select the delete icon of a task that you want to cancel.

    ![](images/publish-dashboard-cancel-task.png){align="left"}

1.  Select **Yes** on the **Confirm Cancellation** message prompt.

    The cancel command is accepted and cancellation is attempted as long as the task remains active. Once the task is successfully terminated, it is removed from the currently active task list. The task's status also gets updated in the DITA map dashboard as Cancelled. In the following screenshot, the *HTML5* task is canceled from the Publish Dashboard and its status is also changed in the DITA map dashboard.

    ![](images/cancelled-output-task.png){align="left"}


**Parent topic:**[Output generation](generate-output.md)
