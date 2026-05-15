---
title: Create a map
description: Create a map with Map Editor in AEM Guides. Find the steps to create a map file based on a map template.
feature: Authoring, Map Editor
role: User
hide: true
exl-id: 981ecaeb-9b1f-4c7a-8336-7746a739bedc
TQID: https://experienceleague.adobe.com/ezadQbcoT3y2-owiIZ5MgsnBbNegmCb2lCIwxgwhcAE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
subfeature_v2:
  - id: a7bba4a6-624b-4427-a9b8-dd411a1bfd41
    internal-label: Map Editor
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Create a map {#id176FEN0D05Z}

AEM Guides provides two out-of-the-box map templates - DITA map and Bookmap. You can also create your own map templates and share those with your authors to create map files.

Perform the following steps to create a map file:

1.  In the Assets UI, navigate to the location where you want to create the map file.

1.  Click **Create** \> **DITA Map**.

1.  On the Blueprint page, select the type of map templates you want to use and click **Next**.

    >[!NOTE]
    >
    > The way the topics are referred in a map file depend on the map template. For example, if you select the Map template, then the topic references \(`topicref`\) are used to refer to topics. In case of a Bookmap, topic references are created using the `chapter` element in DITA.

    ![](images/map-template.png){width="650"}

1.  On the Properties page, specify the map **Title**.

1.  \(Optional\) Specify the file **Name**.

    If your administrator has configured automatic file name based on UUID setting, then you will not see the option to specify the file name. A UUID-based file name is automatically assigned to the file.

    If the file naming option is available, then also the name is automatically suggested based on the Title of your map. If you want to manually specify the map file name, then ensure that the file name does not contain any spaces, apostrophe, or braces and ends with `.ditamap`.

1.  Click **Create**.

    The Map Created message appears.

    Every new map file that you create from the Assets UI **Create** \> **DITA Map** or the Web Editor is assigned a unique map ID. Also, the new map is saved as the latest working copy in DAM. Until you save a revision of a newly created map, you will not see any version number in the Version History. If you open the map for editing, the version information is shown in the right top corner of the map file's tab:

    ![](images/first-version-map-none.png){width="650"}

    The version information for a newly created map is shown as *none*. When you save a new version, then it is assigned a version number as 1.0. For more information about saving a new version, see [Save As New Version](web-editor-features.md#save-as-new-version-id209ME400GXA).

    You can choose to open the map for editing in the configured map editor, or save the map file in the AEM repository.

    >[!NOTE]
    >
    > To use the Advanced Map Editor, access the map file in the Web Editor. In case your administrator has configured the Advanced Map Editor as the default editor in the map files, then the map file is opened directly in the Advanced Map Editor for editing. See *Set the Advanced Map Editor as default* section in Install and configure Adobe Experience Manager Guides as a Cloud Service.


**Parent topic:**[Work with the Map Editor](map-editor.md)
