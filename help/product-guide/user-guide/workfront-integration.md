---
title: Workfront integration
description: Learn how to integrate Workfront with AEM Guides and start creating tasks for authoring, publishing, reviewing, and translation workflows.
feature: Authoring
role: User
---
# Workfront Integration

Adobe Workfront is a cloud-based work management solution that helps teams and organizations plan, track and manage their work efficiently. The native integration between Adobe Workfront and Adobe Experience Manager Guides provides you with a unified workspace to seamlessly author and manage content, as well as allocate and track tasks. 

With this integration, you can create and manage Workfront tasks directly from Experience Manager Guides based on your user role. For example, as an Author, you can create a Review task (with one or more DITA topics or maps attached) directly within the Experience Manager Guides interface and assign it to a Reviewer. As a Reviewer, you can work on assigned tasks in the Experience Manager Guides Review UI and return them to the Author with comments. 

Similarly, depending on your role, you can also manage tasks related to Authoring, Publishing, and Translation, ensuring a seamless and efficient workflow throughout the content lifecycle.

**Key features**

With the native Adobe Workfront integration, you can: 

* Plan, allocate, and track the progress of individual tasks and projects without relying on multiple, non-integrated tools. 
* Manage all Experience Manager Guides workflows including authoring, reviewing, publishing, and translating content more efficiently. 
* Receive task notifications through a configurable notification system whenever new tasks are assigned. 
* Monitor project health using Workfront's intuitive dashboard, offering real-time insights into project performance. 
* Maintain a detailed audit trail to easily review and track key project activities from the past. 

## Get started 

Once configured and enabled by your administrator, Workfront tasks can be accessed right from the [Experience Manager Guides Home page](./intro-home-page.md). 

Perform the following steps to access your Workfront tasks: 

1. Log into Experience Manager Guides and open the **Home page**.  
2. In the left panel, select **Workfront**.   
    
3. Sign in to **Workfront** using the same email address as used in Experience Manager Guides. If already signed-up, jump to Step-4.

4. The **Workfront tasks page** is displayed on the right, featuring two tabs - **Created by You** and **Assigned to You**. Use these tabs to [manage Workfront tasks](#manage-workfront-tasks).


### Working with the Your Tasks widget

**Your tasks** is a widget where a list of Workfront tasks(that are assigned to you and are in Open state) is displayed along with the key task details including name of the task, associated project, due date, and the current status.

You can access **Your Tasks** from the [Overview section](./intro-home-page.md#overview). Select **Overview** and the Your tasks widget would display on the right along with other widgets. 

The following options are available when you hover over a task:  

* **Open**: Allows you to open a task. Based on your task type, the task opens in the Editor, Map Console, or Review UI. You can also open a task by simply selecting the task name. 
* **Task details**: Allows you to view key task details before opening the task. 

The widget also provide you with options to sort and resize columns for a customized view. To apply sorting to a column, select the column header and the options would display in a list. To adjust a column's width, hover over the column divider line in the header, then drag to resize.

## Create Workfront tasks

Perform the following steps to create a new Workfront task: 

1. On the Workfront tasks page, select **New task**.

   The **Create task** dialog box is displayed.
2. In the **General** tab, enter the following task details: 

    - **Task type**: Select the task type that you want to create. The available options are: **Authoring**, **Reviewing**, **Publishing**, and **Translation**. 
    - **Project**: Select the project within which you want to create this the task. 
    - **Task name**: Enter a descriptive name for the task. 
    - **Description**: Enter a brief description of the task. 
    - **Due on**: Set the due date for task completion. 
    - **Assignee**: Select an assignee for the task.  
3. Select **Create**.

A new task has been is created and listed under the **Created by you** tab. 

**Attaching assets to a task**

You can create a task without attaching any asset or file to it. However, attaching assets to a task provides assignees quick access to a topic, map or any other file they need to work upon.  

Perform the following steps to attach an asset: 

1. While creating a task, navigate to the **Assets** tab.
2. Navigate to the path where the asset is located, and select the files that you want to attach.  
3. Click **Select**.
   
   This adds the selected assets to the task. You can add more assets by selecting **Add**.
4. Select **Create**.  

>[!NOTE]
>
> As a project manager, you can view this newly created task in your Workfront dashboard along with other key task details.

## Manage Workfront tasks

To help you manage your Workfront tasks easily, the tasks are organized into two seperate tabs:

 - Created by you
 - Assigned to you

All tasks created by you and assigned to you are listed under two seperate tabs - **Created by you** and **Assigned to You** in tabular form, giving you key task details like project name, assignees, task creation date, task completion date, and task status. 

You can perform the following functions on a task created by you: 

* **Open**: Allows you to open the task. Depending on the type of the task, it will open in the Web Editor, Map Console, or Review UI. 
* **Edit**: Allows you to edit task details. 
* **Task details** - Displays the task's details and attached asset.

You can perform the following functions on a task assigned to you: 

* **Open**: Allows you to open the task. Depending on the type of the task, it will open in the Web Editor, Map Console, or Review UI. 
* **Task details** - Displays the task's details and attached asset.

## Working with Workfront Assigned tasks 

To check for a task assigned to you, you can go to the **Your Tasks** widget and get a list of tasks assigned to you. 

Or, navigate to the **Workfront** section in the left panel and get a list of tasks assigned to you under the **Assigned to you** tab. 

>[!NOTE]
>
> When away from your Experience Manager Guides interface, you will receive a Workfront notification for any newly assigned task. To check out these tasks, log in to your AEM Guides instance and access the assigned tasks. 

The following sections walk you through the process of working with different types of tasks assigned to you: 

### Authoring tasks

Perform the following steps to work upon an authoring task: 

1. Access the task either from the **Your tasks** widget or **Assigned to you** tab. You can also use the Task details icon to review key details like task type, associated project, due dates, and more before opening the task. 
2. Select the task or click the Open icon next to the task to open it in the **Editor**.    
3. Review the task details in the **Details** tab and select the **Asset** file to open it.   
4. Make the required edits and select **Mark as done**. 
5. Switch to the **Comments** tab to add a comment to this task. These comments will reflect on the Workfront's project dashboard.  

    >[NOTE]
    >
    > Once the task is marked as done, it will be removed from the **Created by you** tab for the user who initiated this task. 

### Review tasks

As a reviewer, you can review a Workfront review task assigned to you in the Editor.  

Perform the following steps to work upon a review task: 

1. Access the task either from the **Your tasks** widget or **Assigned to you** tab. You can also use the Task details icon to review key details like task type, associated project, due dates, and more before opening the task. 
2. Select the task or click the Open icon next to the task to open it in the **Review UI**.    
3. Perform the required review. 
4. Navigate to the right panel and select the Workfront task details icon.  

    The Workfront Task Details panel expands. 

5. Review key task details before marking the task as done.
6. Select **Mark as done**.
7. Switch to the **Comments** tab to add a comment to this task. These comments will reflect on the Workfront's project dashboard.  

    >[NOTE]
    >
    > Marking the task as done by the Reviewer does not indicate the completion of the task. All review tasks are assigned back to the user who created the task (ideally an author who requested for a review). They can review the comments added by the Reviewer in the Editor and reply if needed. Once all the suggested changes are incorporated, the Task Owner can complete the task by selecting **Mark as Done**.

### Translation tasks

As a translator, you can perform various translation actions on a Workfront Translation task assigned to you in the Editor.  

Perform the following steps to work upon a translation task: 

1. Access the task either from the **Your tasks** widget or **Assigned to you** tab. You can also use the Task details icon to review key details like task type, associated project, due dates, and more before opening the task. 
2. Select the task or click the Open icon next to the task to open it in the **Map console**.    
3. Review task details and the file attached for translation. 
4. Navigate to the **Translation** tab for the various translation options.  
5. Perform the required translation and click **Send for translation**. 
6. Navigate to the Workfront section and select **Mark as done** to indicate that the task is complete.  
7. Switch to the **Comments** tab to add a comment to this task. These comments will reflect on the Workfront's project dashboard.  

    >[NOTE]
    >
    > Once the task is marked as done, it will be removed from the **Created by you** tab for the user who initiated this task. 

### Publishing tasks

As a Publisher, you can view details and publish a Publishing Workfront task assigned to you in the Web Editor.  

Perform the following steps to work upon a publishing task: 

1. Access the task either from the **Your tasks** widget or **Assigned to you** tab. You can also use the Task details icon to review key details like task type, associated project, due dates, and more before opening the task. 
2. Select the task or click the Open icon next to the task to open it in the **map console**.    
3. Review task details and the file attached for publishing. 
4. Navigate to the **Output presets** and perform the required publishing actions.
6. Navigate to the Workfront section and select **Mark as done** to indicate that the task is complete.  
7. Switch to the **Comments** tab to add a comment to this task. These comments will reflect on the Workfront's project dashboard. 

    >[NOTE]
    >
    > Once the task is marked as done, it will be removed from the **Created by you** tab for the user who initiated this task. 