---
title: Release Notes | Upgrade instructions for Adobe Experience Manager Guides 5.1.0 Service Pack 3 release
description: Learn about the compatibility matrix and how to upgrade to the 5.1.0 Service Pack 3 release of Adobe Experience Manager Guides.

---
# Upgrade instructions for the 5.1.0 Service Pack 3 release (December 2025)

This article covers the upgrade instructions and the compatibility matrix for 5.1.0 Service Pack 3 release of Adobe Experience Manager Guides.

For the list of issues that have been fixed in this release, view [Fixed issues in the 5.1.0 Service Pack 3 release](../release-info/fixed-issues-5-1-0-sp3.md).

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by Experience Manager Guides 5.1.0 release. 

### Adobe Experience Manager

**5.1.0 Service Pack 3 UUID**

Version 6.5 Service Pack 23, Service Pack 22, and Service Pack 21

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


| Components version | Site version|
|---|---|
|guides-components.all-1.4.0|aemg-docs.all-1.2.0|


## Upgrade to 5.1.0 Service Pack 3 release of Experience Manager Guides

You can easily upgrade your current version of Guides to version 5.1.0 Service Pack 3. Before you proceed with upgrading to version 5.1.0 Service Pack 3 of Experience Manager Guides, you must consider the following points:

- If you are using version 5.1.0, or 5.1.x , then you can directly upgrade to version 5.1.0 Service Pack 3. 
- If you are using version 4.6.0, 4.6.x, 5.0.0, or 5.0.x, then you need to upgrade to version 5.1.0.
- If you are using version 4.6.3, 4.6.1, 4.6, or 4.4, then you need to upgrade to version 5.0.0. 
- If you are using version 4.3.x, 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1, or 4.1.x then you need to upgrade to version 4.4 before upgrading to version 5.0.0.
- If you are using version 4.0 you need to upgrade to version 4.2 before upgrading to version 4.3.x.
- If you are using version 3.8.5, you need to upgrade to version 4.0 before upgrading to version 4.2.
- If you are on a version prior to 3.8.5, refer to the Upgrade Experience Manager Guides section in the product-specific installation guide available on [Adobe Experience Manager Guides help PDF archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
> - You must install AEM service pack before upgrading Experience Manager Guides version.
> - As per standard DITA behavior, the scope= `external` attribute must not be applied to internal links, as it is intended only for references to external resources. Using this attribute for internal links can cause issues across the content lifecycle and disrupt workflows. Review and correct such instances to ensure smooth and consistent operations.

For details, view [Upgrade instructions for the On-premise releases](../install-guide/upgrade-xml-documentation.md) of Experience Manager Guides.
