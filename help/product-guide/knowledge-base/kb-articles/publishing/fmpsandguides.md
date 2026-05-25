---
title: Publishing using FrameMaker Publishing Server(FMPS) in AEM Guides
description: Publishing with FMPS using AEM Guides
exl-id: 05d4d876-f83b-473c-bf31-14d6565e80e2
feature: AEM Guides FrameMaker Publishing Server
author: Pulkit Nagpal(punagpal)
role: User, Admin
TQID: https://experienceleague.adobe.com/-qkx3TRKOd-kPx1tFrguuWvBY4hIIyqLdCfKDQzR5jg
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
    internal-label: FrameMaker Publishing Server
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
---
# Publishing using FrameMaker Publishing Server(FMPS) in AEM Guides

AEM Guides integration with FrameMaker Publishing Server could be your solution if you are looking for high-quality automated publishing.  
Article helps you in setting up and running FMPS with AEM Guides.

## Compatibility of FMPS with AEM Guides

-   Compatibility with 4.1 AEM Guides: [4.1 compatibility matrix ](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/release-notes/on-prem-release-notes/release-notes-4.1.html?lang=en/#compatibility-matrix)
-   Compatibility with 4.0 AEM Guides: [4.0 compatibility matrix](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html/#Compatibility%20matrix)
-   Latest Release: [Latest release info](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/latest-release-info.html?lang=en)

## Installation

Refer following for AEM Guides and FMPS installation and configuration

### AEM Guides

Installation and configuration refer: [ 4.1 installation & configurations ](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

### FMPS

For FMPS installation you can refer given [YouTube link ](https://www.youtube.com/watch?v=2deelyM5VA8&t) or [FMPS installation & configuration ](https://help.adobe.com/en_US/framemaker/server/index.html#t=fmps-user-guide%2Finstall_config_fmps.html%23install_config_fmps&rhtocid=_2)

## Required Configurations

FrameMaker Publishing Server (FMPS) can be used to generate your DITA content. FMPS supports a wide range of output formats. Modify the following properties of the "com.adobe.fmdita.config.ConfigManager bundle" in the Web Console to configure AEM Guides to use FMPS.

To open the Web Console, go to the URL Access http://\<server name\>:\<port\>/system/console/configMgr.

**Configuration properties and their description** [4.1 installation and configuration ](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf#page=89)

## Running Test:

Using FMPS, you may automatically publish **PDF, Responsive HTML5**, and **Epub** for your DITA and FM Assets.

From the "Generate PDF using" menu, choose FrameMaker Publishing Server.

The user can provide "settings File(.sts)" and "ditaval". Filtering is done using ditaval based on the conditions you supply.

-   **Setting file**: A FrameMaker /FMPS Publish setting file that contains all of the settings that you want FMPS to respect when publishing. For instance, creating output with a customised template, creating Marks and Bleeds (PDF), and creating PDF with TOC.
-   **FMPS preset:** It is pre-defined combination of ditaval and settings file. Instead of giving separate ditaval and settings files, the User can pre-create FMPS preset which can be re-used for publishing needs.

**Note:** The default system setting is be used by FMPS to publish if you don't choose any of the settings or the FMPS preset.

It is a conflict if you chose the FMPS preset and also provided custom settings or a ditaval file from AEM. In this case, the FMPS preset takes precedence over the custom settings or ditaval file.

### Baseline Publishing using FMPS:

You can publish your already created baselines with FMPS2020.0.2 or higher version.

**Sample FMPS settings file(.sts file) to get started:** [Sample FMPS  settings file ](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:ef750752-7a7e-4e51-923e-6b7d9861ed54) (unzip this file)

## FAQ and Troubleshooting:

### FMPS publishing fails with "Timeout Exception"

>Check and increase the value of "FMPS timeout" (Seconds) in /system/console/configMgr/com.adobe.fmdita.config.ConfigManager"

### Unable to get FMPS preset in the dropdown

>Make Sure you have a pre-defined FMPS preset created on Server and that your connection settings are correct.

### I am getting Blank PDFs when publishing

>If you are using UUID, then make sure you have checked "Use UUID based referencing" in FrameMaker Edit Preferences and conversely for non-UUID AEM guides.

### My settings/ditaval are not getting applied in the final published output 

>Verify that you are not simultaneously choosing the FMPS preset and the setting/diaval file. Use FrameMaker to manually check output.

### The baseline not getting published from FMPS

>FMPS2020.0.2 or later versions are compatible with baseline publishing.
>Make sure that your baseline was properly created; to check, go to the Map Dashboard-- Topics-- Download  Map and choose "Use Baseline".

### Publish Tasks from FMPS takes more time than other Engines

>When publishing from FMPS, the ideal fixed header time is approximately 3-4 minutes; if you believe it is longer, check with your FMPS administrator or contact Adobe Support.

## Other Resources:

[FMPS Learn and Support](https://helpx.adobe.com/support/framemaker-publishing-server.html)

[AEM Guides Learn and Support](https://helpx.adobe.com/in/support/xml-documentation-for-experience-manager.html)

[FrameMaker and FMPS community](https://community.adobe.com/t5/framemaker/ct-p/ct-framemaker?page=1&sort=latest_replies&lang=all&tabid=all)

[AEM Guides Community](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation)
