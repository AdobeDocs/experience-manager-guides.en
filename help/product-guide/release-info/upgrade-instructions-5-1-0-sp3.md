---
title: Release Notes | Upgrade instructions for Adobe Experience Manager Guides 5.1.0 Service Pack 3 release
description: Learn about the compatibility matrix and how to upgrade to the 5.1.0 Service Pack 3 release of Adobe Experience Manager Guides.

---
# Upgrade instructions for the 5.1.0 Service Pack 3 release (December 2025)

This article covers the upgrade instructions and the compatibility matrix for 5.1.0 Service Pack 3 release of Adobe Experience Manager Guides.

For the list of issues that have been fixed in this release, view [Fixed issues in the 5.1.0 Service Pack 3 release](../release-info/fixed-issues-5-1-0-sp3.md).

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by Experience Manager Guides 5.1.0 Service Pack 3 release. 

|AEM Guides| AEM Version| Service Pack |
| --- | --- | --- |
|5.1.0 Service Pack 3 (UUID) | 6.5 LTS | 1  |
|5.1.0 Service Pack 3 (UUID) | 6.5  | 23, 22, 21 |

For more details, view the [Technical requirements](../install-guide/download-install-technical-requirements.md) section in the On-Premise Installation and Configuration Guide.

### FrameMaker and FrameMaker Publishing Server

|Release| FMPS| FM |
| --- | --- | --- |
|5.1.0 Service Pack 3 (UUID) | Supported | 2022 or higher  |

### Oxygen Connector

| Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac |
| --- | --- | --- |--- |--- |
| 5.1.0 Service Pack 3 (UUID) | 3.8-uuid.1|3.8-uuid.1 |2.3 | 2.3  |

### Knowledge base template version

|Components package name| Components version | Template version|
|---|---|---|
|Experience Manager Guides Components Content Package for Cloud Service|dxml-components.all-1.3.0| aem-site-template-dxml.all-1.0.4|

### New AEM Site template version

|AEM Guides | AEM version | Components version | Site version|
|---|---|---| ---|
|5.1.0 Service Pack 3 UUID |6.5 LTS | guides-components.all-1.4.1|aemg-docs.all-1.2.0|
|5.1.0 Service Pack 3 UUID |6.5 | guides-components.all-1.4.0|aemg-docs.all-1.2.0|


## Prerequisites

As per standard DITA behavior, the scope=`external` attribute must not be applied to internal links, as it is intended only for references to external resources. Applying this attribute to internal links may disrupt workflows. For content managed in Experience Manager Guides, use the default scope=`local` or key-based references instead.

## Upgrade to 5.1.0 Service Pack 3 release of Experience Manager Guides

You can easily upgrade your current version of Experience Manager Guides to version 5.1.0 Service Pack 3 on **AEM 6.5** or **AEM 6.5 LTS**. 

>[!NOTE]
>
> If you are currently on AEM 6.5 and plan to move to AEM 6.5 LTS, view [Upgrading to Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade). 

Before you proceed with upgrading to version 5.1.0 Service Pack 3 of Experience Manager Guides, you must consider the following points:

- If you are using version 5.1.0, or 5.1.x , then you can directly upgrade to version 5.1.0 Service Pack 3. 
- If you are using version 4.6.0, 4.6.x, 5.0.0, or 5.0.x, then you need to upgrade to version 5.1.0.
- If you are using version 4.6.3, 4.6.1, 4.6, or 4.4, then you need to upgrade to version 5.0.0. 
- If you are using version 4.3.x, 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1, or 4.1.x then you need to upgrade to version 4.4 before upgrading to version 5.0.0.
- If you are using version 4.0 you need to upgrade to version 4.2 before upgrading to version 4.3.x.
- If you are using version 3.8.5, you need to upgrade to version 4.0 before upgrading to version 4.2.
- If you are on a version prior to 3.8.5, refer to the Upgrade Experience Manager Guides section in the product-specific installation guide available on [Adobe Experience Manager Guides help PDF archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
> You must install AEM service pack before upgrading Experience Manager Guides version.

For details, view [Upgrade instructions for the On-premise releases](../install-guide/upgrade-xml-documentation.md) of Experience Manager Guides.
