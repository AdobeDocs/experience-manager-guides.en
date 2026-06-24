---
title: Release Notes | Upgrade instructions and fixed issues in Adobe Experience Manager Guides, 2026.06.0 release
description: Learn about the compatibility matrix and how to upgrade to the 2026.06.0 release of Adobe Experience Manager Guides as a Cloud Service.
---
# Upgrade instructions for the 2026.06.0 release 

This article covers the upgrade instructions and the compatibility matrix for the 2026.06.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2026.06.0 release](whats-new-2026-06-0.md).

For the list of issues fixed in this release, view [Fixed issues in the 2026.06.0 release](fixed-issues-2026-06-0.md).

## Compatibility matrix

This section points the compatibility matrix for the software applications supported by the 2026.06.0 release of Experience Manager Guides as a Cloud Service. 

### FrameMaker and FrameMaker Publishing Server

| Experience Manager Guides as a Cloud Release| FMPS | FrameMaker | Oxygen Author |
| --- | --- | --- | --- |
| 2026.06.0 | Not compatible | 2022 or higher | 26.1 |


### Oxygen Connector

| Experience Manager Guides as a Cloud Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2026.06.0| 3.8 -uuid 1|   3.8 -uuid 1 | 2.3 | 2.3 |


### AEM Site template version

|Components version | Site version|
|---|---|
|guides-components.all-1.5.1| aemg-sites-template-1.3.0|

### Knowledge base template version

|Components package name| Components version | Template version|
|---|---|---|
|Experience Manager Guides Components Content Package for Cloud Service|guides-components.all-1.4.0| aem-site-template-dxml-1.0.17|

## Upgrade to 2026.06.0 release

Experience Manager Guides is upgraded automatically upon upgrading to the latest release of Experience Manager as a Cloud Service.

>[!IMPORTANT]
>
> The release includes updates to folder profile settings (ui_config.json). If you are using custom settings, ensure to take a back up of those before upgrading. After the update, review and adjust your settings to align with the changes introduced in the latest version.

Review and validate your setup configurations to confirm they are correctly implemented. If you have introduced any custom configuration changes, view [Additional configuration for upgrading Cloud Service](../install-conf-guide/additional-config-for-upgrade.md) for any additional procedures applicable to the version you are upgrading from.
