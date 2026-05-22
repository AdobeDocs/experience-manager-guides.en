---
title: Release Notes | Upgrade instructions for Adobe Experience Manager Guides 5.2.0 release
description: Learn about the compatibility matrix and how to upgrade to the 5.2.0 release of Adobe Experience Manager Guides.
---
# Upgrade instructions for the 5.2.0 release (May 2026)

This article covers the upgrade instructions and the  compatibility matrix for 5.2.0 release of Adobe Experience Manager Guides.

For more information about the new features and enhancements, view [What's new in the 5.2.0 release](../release-info/whats-new-5-2-0.md).

For the list of issues that have been fixed in this release, view [Fixed issues in the 5.2.0 release](../release-info/fixed-issues-5-2-0.md).

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by Experience Manager Guides 5.2.0 release. 

|AEM Guides| AEM Version| Service Pack |
| --- | --- | --- |
|5.2.0 (UUID) | 6.5 LTS | 2  |
|5.2.0 (UUID) | 6.5  | 24, 23, 22 |

For more details, view the [Technical requirements](../install-guide/download-install-technical-requirements.md) section in the On-Premise Installation and Configuration Guide.

### FrameMaker and FrameMaker Publishing Server

|Release| FMPS| FM |
| --- | --- | --- |
|5.2.0 (UUID) | Supported | 2026 or higher  |

### Oxygen Connector

| Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac |
| --- | --- | --- |--- |--- |
| 5.2.0 (UUID) | 3.8-uuid.1|3.8-uuid.1 |2.3 | 2.3  |

### Knowledge base template version

|Components package name| Components version | Template version|
|---|---|---|
|Experience Manager Guides Components Content Package for Cloud Service|guides-components.all-1.4.0| aem-site-template-dxml-1.0.17|

### New AEM Site template version


|AEM Guides | AEM version | Components version | Site version|
|---|---|---| ---|
|5.2.0 UUID |6.5 LTS | guides-components.all-1.4.1|NA|
|5.2.0 UUID |6.5 | guides-components.all-1.4.0| aemg-sites-template-1.3.0|


### Configuration changes

With 5.2.0 release, new configuration settings have been introduced to enable and support new features. These configurations include settings for the following:

- New editor
- New baseline
- Ignore metadata property

For detailed information about these configuration settings, see [Configuration changes for On-Premise].

## Upgrade to Experience Manager Guides 5.2.0 

You can easily upgrade your current version of Experience Manager Guides to version 5.2.0 on **AEM 6.5** or **AEM 6.5 LTS Service Pack 2**. 

>[!NOTE]
>
> - AEM 6.5 LTS Service Pack 2 is intended for use with the Experience Manager Guides 5.2.0 release and excludes support for earlier versions. <br>
> - If you are currently on AEM 6.5 and plan to move to AEM 6.5 LTS, make sure to complete the AEM upgrade first before proceeding with the Experience Manager Guides 5.2.0 upgrade. For details, view [Upgrading to Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade). 

Before you proceed with upgrading to version 5.2.0 of Experience Manager Guides, you must consider the following points:

- If you are using version 5.0.0, 5.0.3, 5.1.0 or 5.1.3, then you can directly upgrade to version 5.2.0.
- If you are using version 4.6.3, 4.6.4, 5.0.x, then you can directly upgrade to version 5.1.0. 
- If you are using version 4.6.0, 4.6.1, then you need to upgrade to version 4.6.3 or 4.6.4 or 5.0.0 before upgrading to version 5.1.0. 
- If you are using version 4.3.x, 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1, or 4.1.x then you need to upgrade to version 4.4 before upgrading to version 5.1.0.
- If you are using version 4.0 you need to upgrade to version 4.2 before upgrading to version 4.3.x.
- If you are using version 3.8.5, you need to upgrade to version 4.0 before upgrading to version 4.2.
- If you are on a version prior to 3.8.5, refer to the Upgrade Experience Manager Guides section in the product-specific installation guide available on [Adobe Experience Manager Guides help PDF archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

>[!NOTE]
>
>You must install AEM service pack before upgrading Experience Manager Guides version.

After upgrading to the 5.2 release, reindex the `guidesAssetLucene` index to enable the Find and replace in Source view feature for previously captured content. For details, view []

For additional details on the upgrade workflows, prerequisites, and troubleshooting scenarios, view [Upgrade instructions for the On-premise releases](../install-conf-guide/upgrade-aemg-latest-version.md) of Experience Manager Guides.