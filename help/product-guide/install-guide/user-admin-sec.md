---
title: User administration and security
description: Learn how User administration and security works
exl-id: 1269a652-5261-413d-9ea0-b4f75003e9d8
feature: User Management
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/Che13Q87qddeS5u48gPSfCqfIyunmBshHlq5pB-HjGk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: b1210526-416b-4ef6-bcc0-1692e99f30e9
    internal-label: Administration and security
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
    internal-label: Reports
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: a7a242db-c88c-4e44-818b-bfb4ef92efdf
    internal-label: Permissions
  - id: c837a922-f95c-4da0-83b2-0cfe7038c5d6
    internal-label: Users and groups
  - id: c8841798-1a28-4264-a46a-984860f8e6f6
    internal-label: User administration
  - id: f7774ebe-aec9-42b6-97e4-5002acdc712e
    internal-label: Review
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
    internal-label: Map console
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# User administration and security {#id181AED00G5Z}

To access and configure features in AEM Guides, you need to create users. These users can then be assigned permissions to access all or specific features in AEM Guides. Learn how to configure and maintain user authorization and also understand the theory behind how authentication and authorization works in AEM.

The following topics in AEM documentation will help you understand the user administration and security-related concepts and features:

-   [Users and Groups in AEM](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#UsersandGroupsinAEM)

-   [Permissions in AEM](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#PermissionsinAEM)

-   [Managing Users and Groups](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#ManagingUsersandGroups)

-   [Managing Permissions](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/security.html#ManagingPermissions)


## User groups created by AEM Guides {#id181TF0K0MHT}

AEM Guides provides three out-of-the-box groups. These groups are: *Authors*, *Reviewers*, and *Publishers*. Depending upon the group a user is associated with, they are allowed to perform specific tasks. For example, publishing task can be performed only by a publisher, but not by an author or a reviewer. Similarly, an author can create a new topic, and a reviewer can only review a topic.

>[!TIP]
>
> See the *Permissions* section in the Best practices guide for best practices around setting user permissions.

The following table lists various tasks and the groups that can perform those tasks:

|Task|Authors|Reviewers|Publishers|
|----|-------|---------|----------|
|Create DITA Topic|Yes| |Yes|
|Create DITA Map|Yes| |Yes|
|Map Collections|Yes| |Yes|
|Create Review Task|Yes| |Yes|
|Review Topic[1](#fntarg_1)|Yes|Yes|Yes|
|Key Resolution|Yes| |Yes|
|Open in FrameMaker|Yes| |Yes|
|Check-out/Check-in|Yes| |Yes|
|Edit Topic|Yes| |Yes|
|Move Topic|Yes| |Yes|
|Edit Topic Properties|Yes| |Yes|
|Copy|Yes| |Yes|
|Delete|Yes| |Yes|
|Share|Yes| |Yes|
|**Document state**||||
|Create/edit document state profile| | |Yes|
|Change document state[2](#fntarg_2)|Yes|Yes|Yes|
|**Features available in DITA map console \(Output Presets tab\)**||||
|Generate| | |Yes|
|Edit| | |Yes|
|Duplicate| | |Yes|
|Create| | |Yes|
|Delete Preset| | |Yes|
|**Features available in DITA map console \(Outputs tab\)**||||
|View generated output|Yes| |Yes|
|**Features available in DITA map console \(Topics tab\)**||||
|Create Review Task|Yes| |Yes|
|Edit|Yes| |Yes|
|**Features available in DITA map console \(Baselines tab\)**||||
|Create| | |Yes|
|Edit| | |Yes|
|Duplicate| | |Yes|
|Remove| | |Yes|
|DITA map console \(Reports tab\)|Yes| |Yes|
|**Features available in DITA map console \(Condition Presets\)**||||
|Create/edit condition preset| | |Yes|

## Additional notes on user groups 

The following list contains some recommendations and points related to user groups and corresponding permissions:

-   If you want a user to start the translation or review workflow, ensure that the user is a member of the *Publishers* and *projects-administrators group*.

-   Users must have the read, create, delete, and modify permissions available on the source and target language folders that they need to work on.

-   If you create a project, you are the owner of the project with *Publishers* permissions. For other users in a project to be able to see their team members, create tasks, or create workflows, they must have read access on `/home/users` and `/home/groups` nodes. One way of giving read access on `/home/users` and `/home/groups` nodes is by giving read access to the `projects-users` group.

-   *Reviewers* can access and add review comments on a topic under review from the Project console or from inbox notification link. Also, this access is only available till the time the review task is open.

-   By default, *Publishers* are granted access and permissions on the following folders in DAM:

    -   ``/var/dxml``–\> Read and Write

    -   `/content/dam/fmdita-outputs` –\> Read and Write

    -   `/content/output/sites` –\> Read and Write

    You must give explicit read and write permissions to your publisher if you are using any other location apart from the default publishing locations mentioned above.

-   All users under *Authors*, *Reviewers*, and *Publishers* groups have read access on all content in DAM.

-   Folder-level permissions must be assigned to users via the user administration page.

-   If you want your users to be able to perform search operations on DAM, then make your users a member of the *dam-users* group.

-   If you want to give admin rights to any user, you can do so by giving them access through AEM standard groups like *administrators*, *projects-administrators*, or OSGI configuration \(Felix console\).

-   To give a user rights to change a document state, make sure that you add the user in the state transition section of the document state profile.

[1](#fnsrc_1) If *Authors* and *Publishers* are invited for a review.[2](#fnsrc_2) Depending on the rights given to the user in the document state profile.
