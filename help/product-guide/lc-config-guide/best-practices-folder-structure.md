---
title: Best practices to set up folder structure
description: Learn about the best practices to set up folder structure when working with the Learning and Training content in Experience Manager Guides.
feature: Authoring
role: Admin
level: Experienced
exl-id: 1b99ade0-0eee-42c3-a383-0c3774b6c1f6
---
# Best practices for setting up the folder structure

This article provides essential steps and best practices for Administrators to set up folder structures in Adobe Experience Manager Guides. A well-organized folder hierarchy ensures smooth authoring, publishing, and translation workflows for Learning and Training content. 

## Set up the folder structure

To allow access to various authoring, publishing, and translation features of Experience Manager Guides, ensure that you set up folders in the right hierarchy as explained below. 

**Create a root-level folder**

Start by creating a root folder for your organization. This serves as the base for all department-level folders and commonly shared assets. 

Example: `/content/dam/ABC-Corp/`

Within this root folder, create a dedicated folder to manage assets that will be used across multiple departments. For example, create a **Common** folder to include shared resources such as images, videos, and more.   

![](assets/root-level-folder.png)

**Create department-level folders**

Create separate folders for each department such as HR, Finance, Legal, so they can manage their own content. 
    
![](assets/department-level-folders.png)
*Caption: Separate folder structure created for HR Department within the root folder*

**Best practices for setting department level folders**

- Create a dedicated **Common** > **assets** folder under each department for department-level common assets (if needed).
- In case you want to share your content for translation, then create language-specific folders (e.g., en, de, fr). Authors should create or update content only in the source language folder (like en), as content outside the source language folder is not included in the translation workflow. The other language folders can be kept empty as placeholders. Learn more about [content translation](../user-guide/translation.md).
- Permissions can be leveraged for limiting access of specific departments or users to the newly created folder structure. For example, assign permissions to ensure only HR department users can create or modify content within the designated folder.

Repeat the same structure for other departments like Finance, Legal, etc.

## Set up the output folder structure

The `fm-ditaoutputs` folder serves as the default storage location for generated outputs from Learning and Training content. These outputs typically include SCORM packages (ZIP files) in the **alm** folder and PDFs in the **pdf** folder.You can change this default output path at the preset level from the **Map console** if needed.

![](assets/fmdita-output-lc.png)

When working with multiple departments, consider creating department-specific folders within the `fm-ditaoutputs` folder structure to ensure users within a specific department have access to the relevant output folders. 

## Create users and assign them to appropriate groups

Once the folder hierarchy is established, you can start creating users and add them to groups so that they have access to relevant features in the Experience Manager Guides. Experience Manager Guides provides three out-of-the-box groups - Authors, Reviewers, and Publishers. Depending upon the group a user is associated with, they are allowed to perform specific tasks. For example, publishing task can be performed only by a publisher, but not by an author. 

To create new users and add them to groups, navigate to **Tools** > **Security** > **Users**.

On the User Management page, select **Create** to create a new user. Add user details and assign them to a group. 

![](assets/create-users-page.png)

For more details, view [User administration and security](../cs-install-guide/user-admin-sec.md)


## Assign permissions to each user group

After users are added to appropriate groups, configure permissions at a group level to ensure they have access to the correct authoring and output folders in the Repository. 

To assign permissions, navigate to **Tools** > **Security** > **Permissions**. 

These permissions help ensure that users can create or modify content only within their designated folders.  

For more details, view [Permissions in AEM](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/security/security#permissions-in-aem).
