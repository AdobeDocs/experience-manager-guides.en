---
title: Release Notes | Upgrade instructions for Adobe Experience Manager Guides 5.1.0 Service Pack 1 release
description: Learn about the compatibility matrix and how to upgrade to the 5.1.0 Service Pack 1 release of Adobe Experience Manager Guides.
exl-id: 5d6f6c8a-cdd5-498d-b7b9-5587324d43b2
TQID: https://experienceleague.adobe.com/TAPOFpFnxWCX2airNKSO400ZnUMxRk0zJXHd1gx651k
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: afb45297-4313-4f67-818e-bc0b03abe086
    internal-label: Knowledge base
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
    internal-label: FrameMaker Publishing Server
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Upgrade instructions for the 5.1.0 Service Pack 1 release (October 2025)

This article covers the upgrade instructions and the compatibility matrix for 5.1.0 Service Pack 1 release of Adobe Experience Manager Guides.

For the list of issues that have been fixed in this release, view [Fixed issues in the 5.1.0 Service Pack 1 release](../release-info/fixed-issues-5-1-0-sp1.md).

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by Experience Manager Guides 5.1.0 Service Pack 1 release. 

### Adobe Experience Manager

**5.1.0 Service Pack 1 UUID**

Version 6.5 Service Pack 23, Service Pack 22, and Service Pack 21

For more details, view the [Technical requirements](../install-guide/download-install-technical-requirements.md) section in the On-Premise Installation and Configuration Guide.

### FrameMaker and FrameMaker Publishing Server

|Release| FMPS| FM |
| --- | --- | --- |
|5.1.0 Service Pack 1 (UUID) | Supported | 2022 or higher  |

### Oxygen Connector

| Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac |
| --- | --- | --- |--- |--- |
| 5.1.0 Service Pack 1 (UUID) | 3.8-uuid.1|3.8-uuid.1 |2.3 | 2.3  |

### Knowledge base template version

|Components package name| Components version | Template version|
|---|---|---|
|Experience Manager Guides Components Content Package for Cloud Service|dxml-components.all-1.3.0| aem-site-template-dxml.all-1.0.4|

### New AEM Site template version


| Components version | Site version|
|---|---|
|guides-components.all-1.4.0|aemg-docs.all-1.2.0|


## Upgrade to 5.1.0 Service Pack 1 release of Experience Manager Guides

You can easily upgrade your current version of Guides to version 5.1.0 Service Pack 1. Before you proceed with upgrading to version 5.1.0 Service Pack 1 of Experience Manager Guides, you must consider the following points:

- If you are using version 5.1.0, then you can directly upgrade to version 5.1.0 Service Pack 1. 
- If you are using version 4.6.0, 4.6.x, 5.0.0, or 5.0.x, then you need to upgrade to version 5.1.0.
- If you are using version 4.6.3, 4.6.1, 4.6, or 4.4, then you need to upgrade to version 5.0.0. 
- If you are using version 4.3.x, 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1, or 4.1.x then you need to upgrade to version 4.4 before upgrading to version 5.0.0.
- If you are using version 4.0 you need to upgrade to version 4.2 before upgrading to version 4.3.x.
- If you are using version 3.8.5, you need to upgrade to version 4.0 before upgrading to version 4.2.
- If you are on a version prior to 3.8.5, refer to the Upgrade Experience Manager Guides section in the product-specific installation guide available on [Adobe Experience Manager Guides help PDF archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
>You must install AEM service pack before upgrading Experience Manager Guides version.

For details, view [Upgrade instructions for the On-premise releases](../install-guide/upgrade-xml-documentation.md) of Experience Manager Guides.
