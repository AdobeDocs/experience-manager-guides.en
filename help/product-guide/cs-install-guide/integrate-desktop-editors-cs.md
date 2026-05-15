---
title: Integrate desktop-based XML editors
description: Learn how to Integrate desktop-based XML editors
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
exl-id: 86ba53fa-0e08-4791-9018-09fe974691da
TQID: https://experienceleague.adobe.com/4cejVcInzwcFBWgxobUvn7g2teizpQCCeTC2Z5CZ1K8
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
  - id: bf79f6d3-0ad0-4d82-99e4-42ce98324d60
    internal-label: Publishing FrameMaker documents
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Integrate desktop-based XML editors 

There are a lot of XML editors available on the market, and you could be using one already. Adobe FrameMaker is one of the most powerful XML editors, which comes with AEM connector. Using the AEM connector in FrameMaker, you can easily connect with the AEM repository, check-out and check-in files, and edit files directly in FrameMaker. You can also configure Experience Manager Guides to launch FrameMaker from the Web Editor. Once you have the file opened in FrameMaker, you can edit and check the file back into the AEM repository.

## Enable file editing in FrameMaker from the Web Editor 

You can use FrameMaker or any other DITA editor to create and update DITA content. However, if your organization uses FrameMaker as DITA editor, then you can give your users an option to open DITA documents directly in FrameMaker from AEM.


By default, your users do not see the **Open in FrameMaker** button on the AEM toolbar. Perform the following steps to add this button on the AEM toolbar:

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to add this button on the AEM toolbar:


|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`xmleditor.openinframebuttonshow`|Boolean \(true/false\). If you want to show the **Open in FrameMaker** button, then set this property to true. <br> **Default value**: false |



If you are using version 2409 and FrameMaker 2022 September release - Update 3, you must enable the **FrameMaker Version 2022 Update 3 or above** config for your users to pass on the Experience Manager Guides server details to FrameMaker.  By default it is disabled.


|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`xmleditor.openinframe2022above`|Boolean \(true/false\). If you are using FrameMaker 2022 September release - Update 3 , then set this property to true. <br> **Default value**: false |



When you set *openinframebuttonshow* property to true, then the **Open in FrameMaker** button is shown on selecting any DITA file in the AEM repository. When this property is not set to *true*, the **Open in FrameMaker** button is shown only when you select a .fm or a .book file in the repository.
