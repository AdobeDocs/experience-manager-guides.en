---
title: Create a DITA project
description: Create a DITA project using a template in AEM Guides. Learn how to use a DITA project to initiate the reviews.
exl-id: 0cd83fe3-1764-4f04-ae11-0b71b6ac576c
feature: Reviewing
role: User
TQID: https://experienceleague.adobe.com/mOwLR3UFEcVKiEYLzLxo5lzK3rIeNJtB7q-qEyraY30
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Create a DITA project {#id1645HA00NM6}

Adobe Experience Manager Guides provides a DITA project template that you can use to create and manage your review tasks.

You can create a DITA project and then use it to initiate your reviews. A project lets you define a deadline and control the tasks and time required to complete the review task for which you have created the project.

You can add team members to a project who could then be assigned various roles – Authors, Reviewers, and Publishers.

Once you have created your DITA project, you can initiate your review from the Editor or the Assets UI. For more details, view [Send topics for review](review-send-topics-for-review.md#).

Similarly, whenever an author initiates any review workflow the selected members of the project get an email notification. To configure email notifications, view *Customize email templates* in Install and configure Adobe Experience Manager Guides as a Cloud Service.

Perform the following steps to create a DITA project:

1.  Open Projects console.

    You can also access the Projects console using the following URL:

    ```http    
    http://<server name>:<port>/projects.html
    ```

1.  Select **Create** \> **Project** to launch the Create Project wizard.

    ![](images/project-console-63.png){width="650"}

1.  On the Create Project page, select the **DITA Project** template and select **Next**.

1.  On the Project Properties page, enter the following details:

    Information in the **Basic** tab:

    ![](images/create-project.png){width="650"}

    -   Enter your project's **Title**, **Description**, and **Due Date**.

    -   You can, optionally, choose a thumbnail for the project.

    -   By default, you are made the owner of the project. To add more users to this project:

    1.  Enter or choose a user from the **User** drop-down list.

    1.  Choose a user type - Authors, Reviewers, or Publishers.

        >[!NOTE]
        >
        >You will view other user types in this drop-down list, but for a DITA project you should only choose from Authors, Reviewers, or Publishers user type. Even if you add a user of a different type, that user will not be able to access any DITA-specific features available in Experience Manager Guides.

    1.  Select **Add**.

        >[!NOTE]
        >
        >If you are using Experience Manager Guides version 3.5 or earlier, you are shown an option to select a DITA map file to resolve key references for topic editing, preview and review workflows. In 3.6 and later versions, you can set the root map through the Editor. For more information, view the [User Preferences](web-editor-features.md#id2087G0P40SB) in the Editor. Another way of setting the root map is by configuring it at the global or folder-level profiles. For more details, view *Configure global or folder-level profiles* in the Installation and Configuration Guide.

    Information in the **Advanced** tab:

    -   Enter a name for the project. This name is used to create the URL for this project.

1.  Select **Create**.

    The Project Created dialog appears.

1.  Select **Open** to open your project page.


**Parent topic:**[Introduction to review](review.md)
