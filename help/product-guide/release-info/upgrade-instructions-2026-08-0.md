---
title: Release Notes | Upgrade instructions and fixed issues in Adobe Experience Manager Guides, 2026.08.0 release
description: Learn about the compatibility matrix and how to upgrade to the 2026.08.0 release of Adobe Experience Manager Guides as a Cloud Service.
---
# Upgrade instructions for the 2026.08.0 release 

This article covers the upgrade instructions and the compatibility matrix for the 2026.08.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2026.08.0 release](whats-new-2026-08-0.md).

For the list of issues fixed in this release, view [Fixed issues in the 2026.08.0 release](fixed-issues-2026-08-0.md).

## Compatibility matrix

This section points the compatibility matrix for the software applications supported by the 2026.08.0 release of Experience Manager Guides as a Cloud Service. 

### Java SDK resources

Use the following resources when developing custom Java plugins or integrations with Experience Manager Guides. Ensure that the SDK version matches your installed Experience Manager Guides release. 

|Release|Java SDK version|Maven Central| Java API reference| 
|---|---|---|----|
|2026.08.0|2026.8.0|[AEM Guides SDK API 2026.8.0 ](https://central.sonatype.com/artifact/com.adobe.aem/aem-dox-sdk-api/2026.8.0)|[Javadoc 2026.8.0](https://javadoc.io/doc/com.adobe.aem/aem-dox-sdk-api/latest/index.html)|

For more details, view [Configure and use the API JAR from Maven Central repository](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/api-reference/introduction).

### FrameMaker and FrameMaker Publishing Server

| Experience Manager Guides as a Cloud Release| FMPS | FrameMaker | Oxygen Author |
| --- | --- | --- | --- |
| 2026.08.0 | Not compatible | 2022 or higher | 26.1 |


### Oxygen Connector

| Experience Manager Guides as a Cloud Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2026.08.0| 3.8 -uuid 1|   3.8 -uuid 1 | 2.3 | 2.3 |


### AEM Site template version

|Components version | Site version|
|---|---|
|guides-components.all-1.5.1| aemg-sites-template-1.3.0|

### Knowledge base template version

|Components package name| Components version | Template version|
|---|---|---|
|Experience Manager Guides Components Content Package for Cloud Service|guides-components.all-1.4.0| aem-site-template-dxml-1.0.17|

## Upgrade to 2026.08.0 release

Experience Manager Guides is upgraded automatically upon upgrading to the latest release of Experience Manager as a Cloud Service.

>[!IMPORTANT]
>
> The release includes updates to folder profile settings (ui_config.json). If you are using custom settings, ensure to take a back up of those before upgrading. After the update, review and adjust your settings to align with the changes introduced in the latest version.

Review and validate your setup configurations to confirm they are correctly implemented. If you have introduced any custom configuration changes, view [Additional configuration for upgrading Cloud Service](../install-conf-guide/additional-config-for-upgrade.md) for any additional procedures applicable to the version you are upgrading from.
