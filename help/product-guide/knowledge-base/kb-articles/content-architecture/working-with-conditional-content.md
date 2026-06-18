---
title: Working with conditional content
description: Learn how to create conditions, then setup conditional content generation in [!DNL AEM Guides]
role: User
exl-id: a86007e3-48d1-458b-84a7-b683e113e5b2
feature: Publishing
TQID: https://experienceleague.adobe.com/3Gz6-sJn7dvzJSlnKgRoRqpFTqtj5fiVlAjOv0lbD1o
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
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Working with conditional content

**Use case**

* Authors can set conditions on a piece of content so they can control whether it is displayed in the output.

* Authors can choose upon publication to show/hide different conditions.

* For example, authors can add attributes as version 1.0 and version 2.0 in the content, and use conditions to include version 1.0 for release 1.0 and exclude version 2.0.

**Step 1**

Define conditions relevant to the documentation in [!UICONTROL Folder Profiles]: 
Refer to section **Configure conditional attributes for global or folder-level profiles** in [Page 69 of the Installation and Configuration Guide](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

![Configure Conditions in Folder Profiles](assets/conditions-in-profiles.png)

**Step 2**

Select the **[!UICONTROL Folder Profile]** defined in Step 1 in **User Preferences** in XML Editor: 
Refer to section **User Preferences** in [Page 41 of User Guide](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)


**Step 3** 

Use the conditions to conditionalize sections of content : 
Refer to section **Conditions** in [Page 90 of User Guide](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)

![Use Conditions in Editor](assets/conditions-in-web-editor.png)

**Step 4** 

Define condition presets at map level to choose which conditions to enable in the output : 
Refer to section **Use condition presets** in [Page 249 of User Guide](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-2/Adobe-Experience-Manager-Guides_User-Guide_EN.pdf)
