---
title: Release Notes | Adobe Experience Manager Guides as a Cloud Service, October 2022 release
description: October release of Adobe Experience Manager Guides as a Cloud Service
exl-id: 38638080-625c-49c3-9e54-56cc23831546
feature: Release Notes
role: Leader
TQID: https://experienceleague.adobe.com/w-fw81jYGDRDrmn98Dzn-hYIkOZzT0B3-4-y-bcxdz4
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
    internal-label: FrameMaker Publishing Server
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
---
# October release of Adobe Experience Manager Guides as a Cloud Service 

## Upgrade to the October release

Upgrade your current Adobe Experience Manager Guides as a Cloud Service (later referred as *AEM Guides as a Cloud Service*) setup by performing the following steps:
1. Check out the Cloud Services' Git code and switch to the branch configured in the Cloud Services pipeline corresponding to the environment that you want to upgrade.
1. Update `<dox.version>` property in `/dox/dox.installer/pom.xml` file of your Cloud Services Git code to 2022.10.183.
1. Commit the changes and run the Cloud Services pipeline to upgrade to the October release of AEM Guides as a Cloud Service.

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by AEM Guides as a Cloud Service October 2022 release. 

### FrameMaker and FrameMaker Publishing Server

| FMPS | FrameMaker |
| --- | --- |
| Not compatible | 2020 Update 4 and above |
| | |

*Baseline and conditions created in AEM are supported in FMPS releases starting from 2020.2.

### Oxygen Connector

| AEM Guides as a Cloud Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac |
| --- | --- | --- | --- | --- |
| 2022.10.0 | 2.7.13 | 2.7.13 | 2.3 | 2.3 |
|  |  |  |  |  |


## New features and enhancements

AEM Guides as a Cloud Service provides enhancements and new features in the October release:


### Quick Generate panel

Now AEM Guides provides the **Quick Generate** panel which helps you quickly generate and view the output for presets created for your DITA map.

![Quick Generate icon](assets/quick-generate-icon.png)

In the **Quick Generate** panel, you can see the list of all the output presets created for your DITA map. 

![Quick Generate panel](assets/quick-generate-panel.png)

Select one or more presets and quickly generate the output. You can also quickly view the output generated for the presets. A success message is displayed on the generation of the output. An error message is shown if the output generation fails. You can also view the error log to see the details of the error that occurred in the generation process.   


## Fixed issues

The bugs fixed in various areas are listed below:

* Native PDF | Error occurs on the removal of resource-only topics from the PDF output. (10554)
* Native PDF | Empty Keyrefs appear in the PDF output. (10553)
* Native PDF | `navtitle` for `topichead` is not honored. (10509)
* Native PDF | Support needed for amd64 JDK flavors. (10465)
* Native PDF | Not able to hide frontmatter topics from the Table of contents. (10355)
* Native PDF | Restarting the page number in the chapter layout randomly starts numbering from the end of the previous chapter. (10154)
* Chrome browser | Screen is getting blank on dragging and dropping any element from the UI. For example, on dragging a condition from the Conditions panel. (10524)
* Node properties are getting removed after the copy-paste operation of an asset. (10053)
* On clicking  **Close** users were being redirected to assets - the experience has been corrected to take users to the AEM homepage. (9654)
