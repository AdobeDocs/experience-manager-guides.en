---
title: Create topics
description: Learn to create types of DITA topics using custom templates in the web editor of AEM Guides.
exl-id: 84e9cfdf-e188-487f-9181-68708029c101
---
# Create topics {#id2056AL00O5Z}

AEM Guides allows you to create DITA topics of type — topic, task, concept, reference, glossary, DITAVAL, and more. Apart from creating topics based on the out-of-the-box templates, you can also define your custom templates. These templates must be added to the folder profile to show up in the template selection Blueprint and the Web Editor.

Note that Global and Folder Profile configuration is only available to folder-level administrative users. For the details on setting up global and folder-level profiles, see *Configure authoring templates* in  Install and configure Adobe Experience Manager Guides for your setup.

Perform the following steps to create a topic:

1.  In the Assets UI, navigate to the location where you want to create the topic.

1.  To create a new topic, click **Create** \> **DITA Topic**.

1.  On the Blueprint page, select the type of DITA document you want to create and click **Next**.

    ![](images/create_dita_topic.png){width="800" align="left"}

    By default, AEM Guides provides the most commonly used DITA topics templates. You can configure more topic templates as per your organizational requirements, see *Configure authoring templates* in  Install and configure Adobe Experience Manager Guides for your setup.

    >[!NOTE]
    >
    > In the list view of Assets UI, the DITA topic type is shown in the Type column as Topic, Task, Concept, Reference, Glossentry, or DITAVAL. The DITA map is shown as Map.

1.  On the Properties page, specify the document **Title**.

1.  \(Optional\) Specify the file **Name**.

    If your administrator has configured automatic file name based on UUID setting, then you will not see the option to specify the file name. A UUID-based file name is automatically assigned to the file.

    If the file naming option is available, then also the name is automatically suggested based on the **Title** of your document. If you want to manually specify the document name, then ensure that the **Name** does not contain any spaces, apostrophe, or braces and ends with .xml or.dita. By default, AEM Guides replaces all special characters with hyphens. See the Filenames section in the Best practices guide for best practices around naming DITA files.

1.  Click **Create**. The Topic Created message appears.

    You can choose to open the topic for editing in the Web Editor, or the save the topic file in the AEM repository.

    Every new topic that you create from the Assets UI **Create** \> **DITA Topic** or the Web Editor is assigned a unique topic ID. The value of this ID is the file name itself. Also, a new document is saved as the latest working copy of the topic in DAM. Until you save a revision of a newly created topic, you will not see any version number in the Version History. If you open the topic for editing, the version information is shown in the right top corner of the topic file's tab:

    ![](images/topic-version-none_cs.png){width="550" align="left"}

    The version information for a newly created topic is shown as *none*. When you save a new version, then it is assigned a version number as 1.0. For more information about saving a new version, see [Save As New Version](web-editor-features.md#save-as-new-version-id209ME400GXA).


>[!NOTE]
>
> If your administrator has configured your Web Editor to check out files before editing, then you will not be able to edit a file until you check it out. Similarly, if configured, you will be asked to check-in any checked-out file before closing it.

>[!IMPORTANT]
>
> Once you have created your DITA topic, keep saving the changes to your working copy and create a new version once you have completed the updates to your topic.

**Parent topic:**[Create and preview topics](create-preview-topics.md)
