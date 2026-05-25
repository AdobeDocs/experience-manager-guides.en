---
title: Set up custom DITA-OT in [!DNL AEM Guides]
description: Learn how to set up custom DITA-OT in [!DNL Adobe Experience Manager Guides]
role: Admin
exl-id: f479c2cf-5b8b-4517-be97-81303468007a
feature: DITA-OT Configuration
TQID: https://experienceleague.adobe.com/EaU6rkZL-RBkkYDhKxHNkizIVSqNzEDd-TtFlJAmREw
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
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
    internal-label: Profiles
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
---
# Set up custom DITA-OT in [!DNL AEM Guides] for AEM

The steps to add a custom DITA-OT are documented in the section _Use custom DITA-OT plug-ins_ of the _Installation and Configuration Guide_.

On a high level the steps are:

+ Get the basic DITA-OT
  + If you want to obtain copy of out-of-the-box DITA-OT from [!DNL AEM Guides], download it from path `/etc/fmdita/dita_resources/DITA-OT.zip`
  + If you want to obtain a different version then you can download from [dita-ot repo](https://www.dita-ot.org/download)
+ Make changes into DITA-OT like [adding new plugin](https://www.dita-ot.org/dev/topics/plugins-installing.html), or customizing existing plugins (refer example in related links section below)
+ Upload `DITA-OT.zip` received to `/apps/<project-folder>/dita_resources` (create a custom project folder is a recommended approach)
+ Add DITA Profile through **[!UICONTROL Tools]** > **[!UICONTROL Guides]** > **[!UICONTROL DITA Profiles]** (use the DITA-OT path where the custom DITA-OT is uploaded, refer screenshot below)
![DITA Profiles](assets/dita-profile.png)

>[!MORELIKETHIS]
>
>+ [Customizing DITA-OT plugin samples](https://www.dita-ot.org/dev/topics/pdf-customization.html)
