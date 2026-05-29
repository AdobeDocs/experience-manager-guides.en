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

## Prerequisites

Before you start the Experience Manager Guides 5.2.0 upgrade process, ensure that you have:

1. Upgraded to Experience Manager Guides version 5.0.0, 5.0.3, 5.1.0, 5.1.3, or 5.1.4.
1. (Optional) Closed all translation tasks.
1. Changed the log level to **INFO** for `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` class and append these logs in a new log file, for example, `logs/translation_upgrade.log`.

## Upgrade path for Experience Manager Guides 5.2.0 

You can easily upgrade your current version of Experience Manager Guides to version 5.2.0 on **AEM 6.5** or **AEM 6.5 LTS**. 

>[!IMPORTANT]
>
> - **For AEM 6.5 LTS**: Experience Manager Guides 5.2.0 is supported only with AEM 6.5 LTS Service Pack 2. 
> - **For AEM 6.5**: Experience Manager Guides 5.2.0 is supported only with AEM 6.5 Service Pack 24, 23, and 22.
> - If you are currently on AEM 6.5 and plan to move to AEM 6.5 LTS, make sure to complete the AEM upgrade first before proceeding with the Experience Manager Guides 5.2.0 upgrade. For details, view [Upgrading to Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade). 

Before you proceed with upgrading to version 5.2.0 of Experience Manager Guides, you must consider the following points:

- If you are using version 5.0.0, 5.0.3, 5.1.0, 5.1.3 or 5.1.4, then you can directly upgrade to version 5.2.0.
- If you are using version 4.6.3, 4.6.4, 5.0.x, then you can directly upgrade to version 5.1.0. 
- If you are using version 4.6.0, 4.6.1, then you need to upgrade to version 4.6.3 or 4.6.4 or 5.0.0 before upgrading to version 5.1.0. 
- If you are using version 4.3.x, 4.2, 4.2.1 (Hotfix 4.2.1.3), 4.1, or 4.1.x then you need to upgrade to version 4.4 before upgrading to version 5.1.0.
- If you are using version 4.0 you need to upgrade to version 4.2 before upgrading to version 4.3.x.
- If you are using version 3.8.5, you need to upgrade to version 4.0 before upgrading to version 4.2.
- If you are on a version prior to 3.8.5, refer to the Upgrade Experience Manager Guides section in the product-specific installation guide available on [Adobe Experience Manager Guides help PDF archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

## Upgrade process for Experience Manager Guides 5.2.0 

>[!IMPORTANT]
>
> The post-processing and indexing may take a few hours. We recommend you to start the upgrade process during the off-peak hours.

1. Download the 5.2.0 version package from [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Install the version package on which you want to upgrade and wait till the bundle is installed.
1. *(Optional)* Upgrade Oxygen connector plugin released with version you are upgrading to.
1. Clear the browser cache after installing the package.
1. If you have enabled the setting `Enable markup find and replace` to access the Find and replace feature in source view for previously captured content, you must reindex the `guidesAssetLucene` index. For details, view [Reindexing for Find and replace](../install-conf-guide/custom-indexing-on-prem.md).
1. Update the system configuration to incorporate the new settings introduced in version 5.2.0, ensuring support for the following enhancements:


| Configurations added|Configuration file | Display label of the setting|Name of the setting|
|-----|-----|------|-----|
|Enable or disable the New Editor|`com.adobe.fmdita.config.ConfigManager`|Enable Editor 2.0|`enable.markup.editor`|
|Enable or disable the New Baseline|`com.adobe.fmdita.config.ConfigManager`|Enable faster Baseline (v2)|`enable.baseline.v2`|
|Ignore metadata properties for marking a version as dirty|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|Ignore metadata property for dirty version|`xmleditor.dirtychecker.ignoremetadata`|
|Find and replace feature in Source view|`com.adobe.fmdita.config.ConfigManager`|Enable markup find and replace|`enable.markup.findreplace`|
|Enable or disable skipping of peer links for old Baseline|`com.adobe.fmdita.config.ConfigManager`|Skip peer links for Baseline V1| `guides.baseline.v1.skip.peer.links`|
|Enable or disable initialization of destination copies with source content in translation workflow. This is applicable only when legacy translation workflow is disabled. |`com.adobe.fmdita.config.ConfigManager`|Initialize destination language copy with source content| `translation.workflow.propagate.source.content`|
|Reference store cleanup|`com.adobe.fmdita.config.ConfigManager`|Guides btree deletion enabled|`btree.deletion.enabled`|
|DITA assets replication|`com.adobe.fmdita.config.ConfigManager`|Replicate DITA assets|`publish.replicate`|
|Asset processing|`com.adobe.fmdita.config.ConfigManager`|Enable Guides asset processing scheduled job|`enable.asset.processing.scheduler`|

For detailed information on these configuration settings, view [Configuration updates](../install-conf-guide/configuration-on-prem.md).







