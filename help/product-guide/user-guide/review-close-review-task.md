---
title: Request a re-review or close a review task as an Author
description: Know about the workflow of closing a review task or re-requesting a review as an Author in Experience Manager Guides.
feature: Reviewing
role: User
exl-id: d2119bbe-3a0c-4da3-b4f8-7872496fa61f
---
# Request a re-review or close a review task as an Author

>[!IMPORTANT]
>
> The new features described in this article are enabled by default with 2508 release of Experience Manager Guides as a Cloud Services. Reviews that were created before the migration are not impacted and will continue to use the earlier workflow. If you prefer to continue using the existing features without these updates, contact your Customer Success team to have the new features disabled. 

When a review task is marked as completed by a Reviewer, a notification is triggered to the task initiator, enabling them to access and review the task and related task level comments. 

As the initiator of the review task, you can then decide how to proceed based on the feedback. The available options are:

- Request a re-review
- Close the review task

## Request a re-review or close a review task 

 Perform the following steps to request a re-review or close a review task:

1. Open the **Review panel** from the left panel of the Editor.
2. Select the review task you want to close or resubmit for review from the **Active tasks** list.
    
    >[!NOTE]
    >
    > You can also open the task in the task dashboard for a more comprehensive view. To do this, select **Open in task dashboard** from the Options menu of any active review task. This opens the task details in the Projects console.

    ![](images/task-dashboard-selection-author-view.png)
3. Select the **Task comments** icon to access and review the task level comments added by the Reviewer.

    ![](images/task-comments-selection-author-view.png).

    The **Task comments** dialog is displayed on the right. 

    ![](images/task-comments-dialog-editor.png){width="350" align="left"}.
4. Select **Update task** to take further action on the selected review task.      
5. In the **Update task** dialog, choose one of the following actions:
    
    - **Reqest a re-review**: Initiates another round of review. You can select a different version of the topic for review. By default, the latest (or the last-edited) version of the topic or map file sent for review is selected. You can also use the **Edit versions** option to set the version of selected topics to **Latest version** or **Baseline** as per the need.  Reviewers who completed the previous review will receive a notification to provide feedback on the updated version. Other reviewers, who haven't marked the review task as complete, are notified about the topic update.       

    - **Close review**: Closes the review task. The **Update task** button present at the bottom of the Review panel changes to **Closed** and a notification is sent to all users involved in the review task indicating its closure.
    
    For details on how review notifications trigger, view [Understanding review notifications](./review-understanding-review-notifications.md).

    ![](images/update-task-dialog.png){width="350" align="left"}
    
    You can also [check the status of your review task](./review-manage-tasks-review-dashboard.md#check-the-status-of-a-review-task-check-review-status-id199rf0a0uhs) using the **Check review status** option present in the Update task dialog. Selecting this option takes you to Review dashboard where the status report of your review task is displayed. 
    
    ![](images/check-review-status-icon.png){width="650" align="left"}
      
7. Select **Confirm**.


As an Author or initiator of a review task, when you close the task, the **Update task** button present at the bottom of the Review panel is changed to **Closed**, indicating the task is no longer active. 

 ![](images/review-task-status-closed-review-panel.png){width="350" align="left"}
    
Also, the **Update task** button present in the Review panel remains disabled for the other users of the review task. For example, as one of the reviewers of a review task, if you open the task in the Editor, the Update task button will be disabled with a message **You don't have permission to act on this task**. Only the initiator of a review task has permission to update the task from the Editor. 

 ![](images/update-task-button-disabled.png){width="350" align="left"}

## Check review status 

You can track the review status of your topics from the **Update task** dialog. This feature helps you to monitor progress, view Reviewer's feedback, and take action when needed. 



