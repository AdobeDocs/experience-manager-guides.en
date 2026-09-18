---
title: Release Notes | Upgrade instructions for Adobe Experience Manager Guides 5.2.0 Service Pack 1 release
description: Learn about the compatibility matrix and how to upgrade to the 5.2.0 Service Pack 1 release of Adobe Experience Manager Guides.
---
# Upgrade instructions for the 5.2.0 Service Pack 1 release (September 2026)

This article covers the upgrade instructions and the compatibility matrix for 5.2.0 Service Pack 1 release of Adobe Experience Manager Guides.

For more information about the new features and enhancements, view [What's new in the 5.2.0 Service Pack 1 release](../release-info/whats-new-5-2-0-sp1.md).

For the list of issues that have been fixed in this release, view [Fixed issues in the 5.2.0 Service Pack 1 release](../release-info/fixed-issues-5-2-0-sp1.md).

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by Experience Manager Guides 5.2.0 Service Pack 1 release. 

|AEM Guides| AEM Version| Service Pack |
| --- | --- | --- |
|5.2.0 Service Pack 1 (UUID) | 6.5 LTS | 2  |
|5.2.0 Service Pack 1 (UUID) | 6.5  | 24, 23, 22 |

For more details, view the [Technical requirements](../install-conf-guide/aemg-technical-requirements.md) section in the On-Premise Installation and Configuration Guide.


### Java SDK resources

Use the following resources when developing custom Java plugins or integrations with Experience Manager Guides. Ensure that the SDK version matches your installed Experience Manager Guides release. 

|Release|Java SDK version|Maven Central|Java API reference|
|---|---|---|----|
|5.2.0 Service Pack 1 (UUID)|5.2.2|[AEM Guides SDK API 5.2.2 ](https://central.sonatype.com/artifact/com.adobe.aem/aem-guides-sdk-api/5.2.2/)|[Javadoc 5.2.2](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api/latest/index.html)|

For more details, view [Configure and use the API JAR from Maven Central repository](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/api-reference/introduction).


### FrameMaker and FrameMaker Publishing Server

|Release| FMPS| FM |
| --- | --- | --- |
|5.2.0 Service Pack 1 (UUID) | Supported | 2026 or higher  |

### Oxygen Connector

| Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac |
| --- | --- | --- |--- |--- |
| 5.2.0 Service Pack 1 (UUID) | 3.8-uuid.1|3.8-uuid.1 |2.3 | 2.3  |

### Knowledge base template version

|Components package name| Components version | Template version|
|---|---|---|
|Experience Manager Guides Components Content Package for Cloud Service|guides-components.all-1.4.0| aem-site-template-dxml-1.0.17|

### New AEM Site template version


|AEM Guides | AEM version | Components version | Site version|
|---|---|---| ---|
|5.2.0 Service Pack 1 UUID |6.5 LTS | guides-components.all-1.4.1|NA|
|5.2.0 Service Pack 1 UUID |6.5 | guides-components.all-1.4.0| aemg-sites-template-1.3.0|

## Prerequisites

Before you start the Experience Manager Guides 5.2.0 Service Pack 1 upgrade process, ensure that you have:

1. Upgraded to Experience Manager Guides version 5.2.0.
1. (Optional) Closed all translation tasks.
1. Changed the log level to **INFO** for `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` class and append these logs in a new log file, for example, `logs/translation_upgrade.log`.

## Upgrade path for Experience Manager Guides 5.2.0 Service Pack 1

You can easily upgrade your current version of Experience Manager Guides to version 5.2.0 Service Pack 1 on **AEM 6.5** or **AEM 6.5 LTS**. 

>[!IMPORTANT]
>
> - **For AEM 6.5 LTS**: Experience Manager Guides 5.2.0 Service Pack 1 is supported only with AEM 6.5 LTS Service Pack 2. 
> - **For AEM 6.5**: Experience Manager Guides 5.2.0 Service Pack 1 is supported only with AEM 6.5 Service Pack 24, 23,and 22.
> - If you are currently on AEM 6.5 and plan to move to AEM 6.5 LTS, make sure to complete the AEM upgrade first before proceeding with the Experience Manager Guides 5.2.0 upgrade. For details, view [Upgrading to Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade). 

Before you proceed with upgrading to version 5.2.0 Service Pack 1 of Experience Manager Guides, you must consider the following points:

- If you are using version 5.2.0, then you can directly upgrade to version 5.2.0 Service Pack 1.
- If you are using version 5.0.0, 5.0.3, 5.1.0, 5.1.3 or 5.1.4, then you can directly upgrade to version 5.2.0.
- If you are using version 4.6.3, 4.6.4, 5.0.x, then you can directly upgrade to version 5.1.0. 
- If you are using version 4.6.0, 4.6.1, then you need to upgrade to version 4.6.3 or 4.6.4 or 5.0.0 before upgrading to version 5.1.0. 
- If you are using version 4.3.x, 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1, or 4.1.x then you need to upgrade to version 4.4 before upgrading to version 5.1.0.
- If you are using version 4.0 you need to upgrade to version 4.2 before upgrading to version 4.3.x.
- If you are using version 3.8.5, you need to upgrade to version 4.0 before upgrading to version 4.2.
- If you are on a version prior to 3.8.5, refer to the Upgrade Experience Manager Guides section in the product-specific installation guide available on [Adobe Experience Manager Guides help PDF archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

## Upgrade process for Experience Manager Guides 5.2.0 Service Pack 1

>[!IMPORTANT]
>
> The post-processing and indexing may take a few hours. We recommend you to start the upgrade process during the off-peak hours.

1. Download the 5.2.0 Service Pack 1 version package from [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Install the version package on which you want to upgrade and wait till the bundle is installed.
1. *(Optional)* Upgrade Oxygen connector plugin released with version you are upgrading to.
1. Clear the browser cache after installing the package.
1. If you have enabled the setting `Enable markup find and replace` to access the Find and replace feature in source view for previously captured content, you must reindex the `guidesAssetLucene` index. For details, view [Reindexing for Find and replace](../install-conf-guide/custom-indexing-on-prem.md).







