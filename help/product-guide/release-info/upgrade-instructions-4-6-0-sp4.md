---
title: Release Notes | Upgrade instructions for Adobe Experience Manager Guides 4.6.0 Service Pack 4 release
description: Learn how to upgrade to  4.6.0 Service Pack 4 release of Adobe Experience Manager Guides
role: Leader
exl-id: d0914e8a-7c7f-47da-9655-697f95f7d4ff
---
# Upgrade instructions for the 4.6.0 Service Pack 4 release (April 2025)

This article covers the upgrade instructions and the  compatibility matrix for 4.6.0 Service Pack 4 release of Adobe Experience Manager Guides.

For the list of issues that have been fixed in this release, view [Fixed issues in the 4.6.0 Service Pack 4 release](fixed-issues-4-6-0-sp4.md).

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by Experience Manager Guides 4.6.0 Service Pack 4 release.

### Adobe Experience Manager

**4.6.0 Service Pack 4 Non-UUID**
Version 6.5 Service Pack 21, 20, and 19

**4.6.0 Service Pack 4 UUID**
Version 6.5 Service Pack 21, 20, and 19

For more details, view the [Technical requirements](../install-guide/download-install-technical-requirements.md) section in the On-Premise Installation and Configuration Guide.

### FrameMaker and FrameMaker Publishing Server

|Release| FMPS 2022 | FMPS 2020 | FM 2022 | FM 2020 |
| --- | --- | --- | --- | --- |
|4.6.0 Service Pack 4 (Non-UUID)| 2022 or higher |2020.2 or higher* | 2022 or higher | 2020.3 or higher |
|4.6.0 Service Pack 4 (UUID) | 2022 or higher | 2020.2 or higher*  | 2022 or higher | 2020.4 or higher |
| | | | |

*Baseline and conditions created in AEM are supported in FMPS releases starting from 2020.2.

### Oxygen Connector

| Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac |  
| --- | --- | --- |--- |--- |
| 4.6.0 Service Pack 4 (Non-UUID)|  2.8-regular-10| 2.8-regular-10 |  1.6 | 1.6  |
| 4.6.0 Service Pack 4 (UUID) | 3.6-uuid.9|3.6-uuid.9 |2.3 | 2.3  |
|  |  |   |  

### Knowledge base template version

|Components package name| Components version | Template version|
|---|---|---|
|Experience Manager Guides Components Content Package for Cloud Service|dxml-components.all-1.2.2| aem-site-template-dxml.all-1.0.15|

### New AEM Site template version

| Components version | Site version|
|---|---|
|guides-components.all-1.0.0|aemg-docs.all-1.0.0 |

## Upgrade to 4.6.0 Service Pack 4 release of Experience Manager Guides

You can easily upgrade your current version of Guides to 4.6.0 Service Pack 4. Before you proceed with the upgrade, you must consider the following points:

- If you are using version 4.6.0, 4.6.0 Service Pack 1 or 4.6.0 Service Pack 3, then you can directly upgrade to 4.6.0 Service Pack 4.
- If you are using version 4.4, 4.3.1, or 4.3.0 , then you need to upgrade to version 4.6.0. 
- If you are using version 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1, or 4.1.x then you need to upgrade to version 4.4 before upgrading to version 4.6.0.
- If you are using version 4.0 you need to upgrade to version 4.2 before upgrading to version 4.3.x.
- If you are using version 3.8.5, you need to upgrade to version 4.0 before upgrading to version 4.2.
- If you are on a version prior to 3.8.5, refer to the Upgrade Experience Manager Guides section in the product-specific installation guide available on [Adobe Experience Manager Guides help PDF archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
>You must install AEM service pack before upgrading Experience Manager Guides version.

The upgrade process for the 4.6.0 Service Pack 4 release follows the same steps as the 4.6.0 release. For detailed instructions, view [Upgrade instructions for the On-premise releases](../install-guide/upgrade-xml-documentation.md) of Experience Manager Guides.
