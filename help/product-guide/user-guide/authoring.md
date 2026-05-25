---
title: Manage content
description: Manage content and identify your roles and permissions in AEM Guides. Learn the key concepts of content management and working with the global or folder-level profiles.
exl-id: 84926dc2-1180-48ef-85d0-50e3478bf26a
feature: Content Management
role: User
TQID: https://experienceleague.adobe.com/IoB9Dk9vwDaGSsqR-M7VobGnVcD5fMnACBhwkJrLN-I
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
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
    internal-label: Reports
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
    internal-label: Document state
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
    internal-label: Map console
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: da3860b0-d637-47df-bef0-273751180266
    internal-label: Digital asset management
---
# Manage content {#id164JBG0M0T1}

Before you start with the actual content creation, you must familiarize yourself with some basic concepts of content management in Adobe Experience Manager Guides. Then, start with creating different user groups and organizing your assets.

## Key concepts 

Some key concepts of content management in Adobe Experience Manager are as follows:

**Asset management**

Experience Manager Guides uses Adobe Experience Manager's digital asset management \(DAM\) to manage your DITA files. The files that you upload or check into the DAM are stored as digital assets. You can manage and edit your assets in Adobe Experience Manager Assets. For more information about asset management, view [Manage assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html?lang=en).

**Link management**

Move or rename files or change folder structure in the content repository, without worrying about broken references. All references to and from the impacted content are automatically updated. Get warnings when deleting content which is referenced from elsewhere, to prevent unintentional breakages.

**Managing versions**

Experience Manager Guides provides version management for your digital assets. You can easily enable this functionality from a DITA authoring application of choice. Allowing your writers to perform the standard version control functions such as check-in and check-out.

For more information about creating versions or reverting to a specific version, view [Branch, revert, and subsequent versioning](web-editor-preview-topics.md#branch-revert-and-subsequent-versioning).

**Native DITA handling**

While Experience Manager Guides maintains the structure of your DITA files, it also enables Adobe Experience Manager to natively handle DITA using element mapping to map the DITA elements to Adobe Experience Manager components. The native DITA handling is used in features such as topic preview, Adobe Experience Manager Sites publishing, and the review workflows.

## Identify your role and permissions {#id181TF0K0MHT}

Experience Manager Guides provides three out-of-the-box groups. These groups are: *Authors*, *Reviewers*, and *Publishers*. Depending upon the group you are associated with, you have permissions to perform specific tasks as mentioned in the table given below. For example, publishing task can be performed only by a publisher, but not by an author or a reviewer. Similarly, an author can create a new topic, and a reviewer can only review a topic.

>[!TIP]
>
> View the *Permissions* section in the Best practices guide for best practices around setting user permissions.

The following table lists various tasks and the groups that can perform those tasks:

|Task|Authors|Reviewers|Publishers|
|----|-------|---------|----------|
|Create DITA Topic|Yes| |Yes|
|Create DITA Map|Yes| |Yes|
|Map Collections|Yes| |Yes|
|Create Review Task|Yes| |Yes|
|Review Topic[1](#fntarg_1)|Yes|Yes|Yes|
|Key Resolution|Yes| |Yes|
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

[1](#fnsrc_1) If *Authors* and *Publishers* are invited for a review.

[2](#fnsrc_2) Depending on the rights given to the user in the document state profile.
