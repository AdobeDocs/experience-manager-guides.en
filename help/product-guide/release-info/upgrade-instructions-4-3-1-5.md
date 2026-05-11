---
title: Release Notes | Upgrade instructions for Adobe Experience Manager Guides 4.3.1.5 release
description: Learn how to upgrade to  4.3.1.5 release of Adobe Experience Manager Guides
role: Leader
exl-id: 856970ef-9f50-4452-b589-ba1f5ee73322
TQID: https://experienceleague.adobe.com/wN9EyxDaR5dSTnaUQIqKV-8jhbw2LUj36vpeUd8Obc4
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
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
---
# Upgrade instructions for the 4.3.1.5 release

This article covers the upgrade instructions and the  compatibility matrix for 4.3.1.5 release of Adobe Experience Manager Guides.


For the list of issues that have been fixed in this release, view [Fixed issues in the 4.3.1.5 release](../release-info/fixed-issues-4-3-1-5.md).




## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by Experience Manager Guides 4.3.1.5 release. 

### Adobe Experience Manager

**4.3.1.5 Non-UUID**
Version 6.5 Service Pack 18, 17, 16, 15, 14

**4.3.1.5 UUID**
Version 6.5 Service Pack 18, 17, 16, 15, 14

For more details, view the *Technical requirements* section in the On-Premise Installation and Configuration Guide .

### FrameMaker and FrameMaker Publishing Server

|Release| FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
|4.3.1.5 (Non-UUID)| 2022 or higher |2020.2 or higher* | 2022 or higher | 2020.3 or higher |
|4.3.1.5 (UUID) | 2022 or higher | 2020.2 or higher*  | 2022 or higher | 2020.4 or higher |
| | | | | |

*Baseline and conditions created in AEM are supported in FMPS releases starting from 2020.2.

### Oxygen Connector

| Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.3.1.5 (Non-UUID)|  2.3-regular-5| 2.3-regular-5 |  1.6 | 1.6  |
| 4.3.1.5 (UUID) | 3.2-uuid-5|3.2-uuid-5 |2.3 | 2.3  |
|  |  |   | | |



### Knowledge base template version

|Components package name| Components version | Template version|
|---|---|---|
|Experience Manager Guides Components Content Package for Cloud Service|dxml-components.all-1.2.2| aem-site-template-dxml.all-1.0.15|



## Upgrade to 4.3.1.5 release of Experience Manager Guides


You can easily upgrade your current version of  Guides to version 4.3.1.5. Before you proceed with upgrading to version 4.3.1.5 of Experience Manager Guides, you must consider the following points:


- If you are using version 4.3.1 or 4.3.1.x then you can directly upgrade to version 4.3.1.5.
- If you are using version 4.3.0 or 4.2 (Hotfix 4.2.1.3)  then you need to upgrade to version 4.3.1 before upgrading to version 4.3.1.5.

- If you are using version 4.1 or 4.1.x then you need to upgrade to version 4.3.1 before upgrading to version 4.3.1.5.


- If you are using version 4.0 you need to upgrade to version 4.2 before upgrading to version 4.3.x.
- If you are using version 3.8.5, you need to upgrade to version 4.0 before upgrading to version 4.2.
- If you are on a version prior to 3.8.5, refer to the Upgrade Experience Manager Guides section in the product-specific installation guide available on [Adobe Experience Manager Guides help PDF archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).



>[!NOTE]
>
>You must install AEM service pack before upgrading Experience Manager Guides version.

For details, view [Upgrade instructions for the On-premise releases](../install-guide/upgrade-xml-documentation.md) of Experience Manager Guides.
