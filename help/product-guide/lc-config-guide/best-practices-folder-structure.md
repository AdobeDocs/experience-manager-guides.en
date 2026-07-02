---
title: Best practices to set up folder structure
description: Learn about the best practices to set up folder structure when working with the Learning and Training content in Experience Manager Guides.
feature: Authoring
role: Admin
level: Experienced
exl-id: 1b99ade0-0eee-42c3-a383-0c3774b6c1f6
TQID: https://experienceleague.adobe.com/jfoPbeASfVpgWYR2-cKacAdhWKPw-2j6qliqzjEzgFw
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
  - id: b1210526-416b-4ef6-bcc0-1692e99f30e9
    internal-label: Administration and security
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: a7a242db-c88c-4e44-818b-bfb4ef92efdf
    internal-label: Permissions
  - id: c8841798-1a28-4264-a46a-984860f8e6f6
    internal-label: User administration
  - id: dc1f7602-db3c-4ad4-a440-ff999bb16455
    internal-label: User management
  - id: f7774ebe-aec9-42b6-97e4-5002acdc712e
    internal-label: Review
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
    internal-label: Map console
  - id: fd456af4-cb12-4a34-8cc4-b74adf885626
    internal-label: Content translation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
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


For more details, view [](./assets/best-practices-guide.pdf)