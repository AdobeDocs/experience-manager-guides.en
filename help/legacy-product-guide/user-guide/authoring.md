---
title: Manage content
description: Manage content and identify your roles and permissions in AEM Guides. Learn the key concepts of content management and working with the global or folder-level profiles.
feature: Content Management
role: User
hide: true
exl-id: 54b960cf-fb00-4d4a-a836-9de4738c49a8
TQID: https://experienceleague.adobe.com/Rko9tfse1l5d-ZKeidb8hCqs1L2RcMlc9o581Xiakk4
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
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
    internal-label: Reports
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
    internal-label: Profiles
  - id: b88be3fe-792c-484d-8262-9f667de75c8d
    internal-label: Version management
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
    internal-label: Document state
  - id: f7774ebe-aec9-42b6-97e4-5002acdc712e
    internal-label: Review
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
    internal-label: Web Editor
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
    internal-label: Map console
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: da3860b0-d637-47df-bef0-273751180266
    internal-label: Digital asset management
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Manage content {#id164JBG0M0T1}

Before you start with the actual content creation, you must familiarize yourself with some basic concepts of content management in AEM Guides. Then, start with creating different user groups and organizing your assets.

## Key concepts 

Some key concepts of content management in AEM are as follows:

**Asset management**

AEM Guides uses AEM's digital asset management \(DAM\) to manage your DITA files. The files that you upload or check into the DAM are stored as digital assets. You can manage and edit your assets in AEM Assets. For more information about asset management, see [Manage assets](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets.html?lang=en).

**Link management**

Move or rename files or change folder structure in the content repository, without worrying about broken references. All references to and from the impacted content are automatically updated. Get warnings when deleting content which is referenced from elsewhere, to prevent unintentional breakages.

**Managing versions**

AEM Guides provides version management for your digital assets. You can easily enable this functionality from a DITA authoring application of choice. Allowing your writers to perform the standard version control functions such as check-in and check-out.

For more information about creating versions or reverting to a specific version, see [Branch, revert, and subsequent versioning](web-editor-preview-topics.md#id193PG0Y051X).

**Native DITA handling**

While AEM Guides maintains the structure of your DITA files, it also enables AEM to natively handle DITA using element mapping to map the DITA elements to AEM components. The native DITA handling is used in features such as topic preview, AEM Sites publishing, and the review workflows.

## Identify your role and permissions {#id181TF0K0MHT}

AEM Guides provides three out-of-the-box groups. These groups are: *Authors*, *Reviewers*, and *Publishers*. Depending upon the group you are associated with, you have permissions to perform specific tasks as mentioned in the table given below. For example, publishing task can be performed only by a publisher, but not by an author or a reviewer. Similarly, an author can create a new topic, and a reviewer can only review a topic.

>[!TIP]
>
> See the *Permissions*section in the Best practices guide for best practices around setting user permissions.

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

## Pre-requisites to content authoring 

**Work with global or folder-level profiles**

In an enterprise, different groups or products may use different authoring templates, output templates, conditional attribute profiles \(or subject schemes\), and Web Editor configurations. Configuring these only at an enterprise \(or global\) level can make authors experience difficult, as they will see templates or profiles that are not relevant to them.

AEM Guides allows you to configure authoring \(topic or map\) templates, output templates, conditional attribute, and Web Editor configurations at an enterprise \(global\) level as well as at a folder level. This way, you can segregate the configurations for different departments or products in your enterprise.

Also, you can delegate the folder-specific configurations to a department or product administrators to decentralize the administration.

For details on setting up global and folder-level profiles, see *Configure global or folder-level profiles* in Install and configure Adobe Experience Manager Guides as a Cloud Service.
