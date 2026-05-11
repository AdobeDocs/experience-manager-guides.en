---
title: About this guide
description: Learn About this guide
exl-id: cdd40267-3f0c-40d2-acbc-2ebe43633c2f
feature: Introduction
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/AVKmd4mTg5Td4or3-8LB1hXxpv9G89430Et8ZATtTsw
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
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: a7a242db-c88c-4e44-818b-bfb4ef92efdf
    internal-label: Permissions
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
    internal-label: Profiles
  - id: b88be3fe-792c-484d-8262-9f667de75c8d
    internal-label: Version management
  - id: c5fd2af0-6cbb-4746-ab0d-40ecb093af12
    internal-label: Introduction
  - id: c8841798-1a28-4264-a46a-984860f8e6f6
    internal-label: User administration
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
    internal-label: Document state
  - id: f551224f-631f-46f8-b8fc-67744f995ba0
    internal-label: Onboarding
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
    internal-label: Web Editor
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: ce44533e-8ec8-4e11-a9e9-78b0fe561832
    internal-label: Content structure
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: da3860b0-d637-47df-bef0-273751180266
    internal-label: Digital asset management
  - id: e6ff21d3-dec6-4298-8590-7c749fffaf78
    internal-label: Content and assets
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# About this guide {#id175MC0P0S5Z}

Adobe Experience Manager Guides \(later referred as *AEM Guides*\) is a powerful, cloud-based, enterprise-grade component content management solution \(CCMS\). It enables native DITA support in Adobe Experience Manager, empowering AEM to handle DITA-based content creation and delivery. It empowers authors to create content using easy-to-use built-in Web Editor and publish it into various output formats.

This guide provides the instructions to download, install, and configure AEM Guides. In this guide, you will find detailed instructions to set up AEM Guides as per your organizational authoring and publishing needs.

This guide is intended for the following type of audiences:

-   Administrators, who would install and manage AEM Guides.

-   Publishers, who would run the publishing task to generate output in various formats.


## Content structure 

The information in this guide is organized as follows:

-   [About this guide](#id175MC0P0S5Z): This topic provides an introduction to this guide, intended audience, and how the information is organized in this guide.

-   [Download and install](download-install.md#): This topic describes how to download, install, or upgrade AEM Guides.

-   [User administration and security](user-admin-sec.md#): This topic describes the core concept of users and authentication in AEM and the default user groups created by AEM Guides.

-   [Use custom DITA-OT and DITA specialization](dita-ot-specialization.md#): This topic explains how to configure custom DITA-OT plug-ins and use DITA specialization.

-   [Configure document states](customize-doc-state.md#): This topic explains how to configure custom states for your DITA documents.

-   [Migrate existing content](migrate-content.md#): This topic describes how to on-board your existing content on AEM repository.

-   [Configure filenames](conf-file-names.md#): This topic explains how to configure setting to automatically assign file names and define a regex for valid file name characters.

-   [Configure topic and map templates](conf-template-tags.md#): This topic describes how to configure topic and map templates to meet your authoring needs. Learn about tagging system in AEM and how to configure tags to work with AEM Guides.

-   [Customize Web Editor](conf-web-editor.md#): This topic explains the various customizations that you can make in the Web Editor to enhance its functionality.

-   [Include @navtitle attribute by default](auto-add-navtitle.md#): This topic explains how to add the `@navtitle` attribute to a reference file in a map by default.

-   [Configure global or folder-level profiles](conf-folder-level.md#): This topic explains the process of creating folder profiles and giving permissions to specific users.

-   [Version management](version-management.md#): This topic describes how to configure automatic file checkout for files that are opened for editing in the Web Editor.

-   [Configure output generation settings](conf-output-generation.md#): This topic describes the various configurations that you can make to customize the default output generation process.

-   [Configure and customize workflows](customize-workflows.md#): This topic describes various configurations to customize the default workflows shipped in the AEM Guides.

-   [Translate content](translation.md#): This topic provides links to the relevant Help articles in AEM documentation to help you understand and configure the translation framework. Also, learn how to enable component-based translation workflow.

-   [Configure search for AEM Assets UI](conf-dita-search.md#): This topic describes how to configure DITA content search in Assets UI and add your custom attributes in search.


## Overview of Adobe Experience Manager \(AEM\) 

[Adobe Experience Manager \(AEM\)](https://business.adobe.com/products/experience-manager/adobe-experience-manager.html) is a comprehensive content management solution for building websites, mobile apps, and forms. AEM helps you manage your marketing content and assets. AEM is available as a Cloud Service. AEM as a Cloud Service helps you to provide your customers with personalized, content-led experiences by combining the power of the AEM Content Management System with AEM Digital Asset Management.Some of the key resources which can help you get started and deploy to AEM as a Cloud Service are as follows:

-   [Experience Manager as a Cloud Service Overview](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html?lang=en)
-   [Getting Started with the Migration Journey to AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/migration-journey/getting-started.html?lang=en)
-   [Start Onboarding to Experience Manager as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/onboarding/home.html?lang=enhttps://experienceleague.adobe.com/docs/experience-manager-cloud-service/moving/home.html?lang=en)
-   [Implementing Applications for AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/home.html?lang=en)
-   [Deploying to AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/deploying/overview.html?lang=en)
-   [Assets as a Cloud Service Guide](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/assets/home.html?lang=en)

## Additional resources 

Following is a list of other helpful resources of AEM Guides, which are available on the [Learn & Support](https://helpx.adobe.com/support/xml-documentation-for-experience-manager.html) page:

-   User Guide
-   API Reference Guide
