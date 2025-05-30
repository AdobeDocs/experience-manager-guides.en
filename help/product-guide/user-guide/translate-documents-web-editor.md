---
title: Translate documents from the Map Console
description: Translate your content into multiple languages from the web editor. Learn how to create a translation project, add rules, view versions, and dismiss out-of-sync files in AEM Guides.
exl-id: 321c5442-92eb-4662-ab61-d4d4f05eeb39
feature: Authoring, Features of Web Editor, Translation
role: User
---
# Translate documents from the Map Console {#id21BKF0Z0YZF}

>[!TIP]
>
> It is recommended to use this Translation feature from the Editor if you have upgraded to Adobe Experience Manager Guides as a Cloud Service February 2022 release or later.

Experience Manager Guides comes with a powerful feature in the Editor that enables you to translate your content into multiple languages. You can create a new translation project and later add the translation jobs to the existing translation project. You can also create a multi-lingual translation project which includes translation jobs for all the selected languages.

>[!NOTE]
>
> Your administrator can configure the Manage tab \(used for translation\) in the Editor. For more details, view *Configure the translation feature in the Editor* section in the Install and configure Adobe Experience Manager Guides as a Cloud Service.

## Before you begin 

Before performing steps in this procedure, ensure that you have created the required language root and target folders

1.  Create a root folder to store your source content. The root folder must be created with the language name \(such as English\) or language code \(en\).
1.  Create the destination folders to which you want to translate your content. For example, if you want to translate your content into German or French, then you must create folder named as -de \(for German\) or -fr \(for French\).

>[!NOTE]
>
> The root folder and the destination folders must be created at the same level.

## Create a translation project 

1.  In the **Repository** panel, open the DITA map file in Map View.
1.  Select the **Open in map console** icon. 
1. On the Map console page, navigate to the **Translation** tab. The **Translation panel** displays the available language groups.

1. As a user, you can view the language groups configured to your folder profile. The language groups display the language folders along with their language codes. For example, the language group named G1 contains Italian \(it\), German \(de\), French \(fr\), and English \(en\) language folders.

    ![translation panel](images/translation-languages.png){width="300" align="left"}

    *Select the language groups or languages in which you want to translate your documents.* 


    >[!IMPORTANT]
    >
    > You can only select and translate to the languages for which you have created the target folder parallel to the source language. A language folder created at any other level, such as one level down from the source language folder is also not shown. Ensure that you create all your target language folders at the same level as your source language folder.

    

1. You can select any language group as a target for the translation. If you **Select all**, the selected files are translated into all the available languages within the existing language groups.

    The language folder option appears grayed out and shows a warning sign:

    - If the target folder for a language is missing.
    - If the target language is the same as the source. 


    >[!NOTE]
    >
    > If you create the target folder for a language after creating the language group, refresh the browser to enable the language in the language groups.  

1. If you choose a particular language, it appears as selected under all language groups you have selected. So, when you translate to any language, it's translated in one go for all the language groups. For example, if German is present in both G1 and G2 language groups, it's selected for both. 

1. From the **Other languages**, you can choose any language for which you have created the target folder but isn't a part of any language groups. 

1.  You can also select one the following options to translate your project:

    **None** Select this option to translate the default versions of the files. This option is selected by default. 

    **Use Baseline:** You can select a baseline to translate your project. Select **Use Baseline** and choose a baseline created on the map. All files that are a part of the selected Baseline are shown in the Translation page. Once your content is translated, you can export the translated Baseline. For more details about exporting the translated Baseline, view [Export translated Baseline](generate-output-use-baseline-for-publishing.md#id196SE600GHS).

    **Use Latest Version as on**: Choose to filter the version of topics based on their creation date and time. When you select a date and time only the latest version of the files created on or before the selected date and time are shown.

1.  Select **Apply**. A list with details of topics and associated assets is shown.
1.  Select the topics that you want to send for translation. You can also use the topic filtering options for the following columns:

    -   **Title**: Title of the source file.  Hover over the title of the source file to view the title of the target or translated file.
    -   **File Name**: Name of the source file
    -   **File Type**: Type of the source file. The available options are Map, Topic, and Image.
    -   **Reference Type**: Direct or Indirect references
    -   **Version**: Version number of the source file
    -   **Version Label**: Label for the selected version of the source file
    -   **Target Version**: Version number of the target file
    -   **Document State**: State of the source file. The available options are Draft, In-Review, and Reviewed.
    -   **Target Language**: The language to which you want to translate the source file
    -   **Translation Status**: The available options are: Out of Sync, Missing Copy, In Progress, and In Sync.
    -   **Target Label**: Label for the selected version of the target file
1.  Select **Send for Translation** on the top right corner.

    ![](images/translation-send.png){align="left"}

1.  From the dropdown, select **Create a New Translation Project**.

    ![](images/translation-project-types.png){width="350" align="left"}

    Besides a new translation project, you also can select from the following options:

    -   You can choose to **Create structure only** for the translation project.
    -  You can choose to **Create a new XLIFF translation project** to convert the XML content into the XML Localization Interchange File Format (XLIFF). XLIFF is an open XML-based format that is used to standardize the data transfer between various tools used in the content translation process. Experience Manager Guides supports XLIFF version 1.2.
    In an XLIFF project, the content is exported to the industry standard XLIFF format, which can be provided to Translation vendors. XLIFF format empowers potential reuse of segments that you have already translated during the translation phase.  
    After the XLIFF content is translated, it can be imported into Experience Manager Guides, creating a translated version of the original DITA project. 

    >[!NOTE]
    >
    > XLIFF export only works with human translation configuration. 

    -   You can select **Create a new multi-lingual translation project** which will include translation jobs for all languages that you have selected for translation. For example, if you have selected French, German, and Spanish it will create a project which contains translation jobs for all three languages.
    -   If you already have a translation project, you can add topics to that project. Select **Add to existing translation project** option from the Project list and choose a project from the Existing Translation Project list. You can sort these projects by most recent, ascending, or descending order.

    - If you select **Add to existing translation project**, this operation updates the existing asset entry in the project if the asset is already added and the related translation job state is in the *Draft* state.
        - If the destination language is not present in the project, a new project is created for the single-language translation project, and a new job is created for multi-language translation project.

        - If the job is already present for the destination language and the job status isn't in the *Draft* state, a new job is created within the same project to add the assets for translation.

    >[!NOTE]
    >
    > If your existing project is a scoping project, it has '\(Scoping\)' appended in its name.

    - If you need to create the scope for a project to be translated, you can select **Create a new scoping translation project**. This will not send the copies for translation and the original translation status of the files is maintained. There is no impact on the destination language copy of the referred topics which are sent for scoping.

1. In the **Project Title** field, enter a title for the project.
1. Select **Submit** to create a new translation project.

A new translation project is created with the selected version of the topics. At this time, a pop-up message is displayed confirming that the translation project has been created. Once all target language copies are available in the translation project, you get a notification in the Inbox. Once the target language copies are available in the translation project, you can then go ahead and start the translation job. For details view, [Start the translation job](translation-first-time.md#id225IK030OE8).

>[!NOTE]
>
> If you reject the translation for one or more topics in a translation job, the **In Progress** translation status of all the rejected topics reverts to their original status. The status of the referred topics is checked and reverted according to the latest translation state. Also, the translation files created in the destination project are not deleted even if the translation is rejected for them.

## Add the translation rules  

Experience Manager Guides allows your administrators to configure the translation rules. The SRX (Segmentation Rules eXchange) format is a standard for exchanging segmentation rules between different users and different translation environments. You can create a folder and add your custom SRX files to it.  

SRX files should be named as `<language-code>.srx`. For example, en-US, or ar-AE.  

>[!NOTE]
> 
> The title is not case-sensitive, so you can have 'en-US' or 'en-us' or 'EN-us'. Also, Experience Manager Guides can resolve '-' (hyphen) or '_' (underscore). So, you can have 'en-US' or 'en_US'. 

Also, you can put these files inside any folder under Adobe Experience Manager assets root that is `./content/dam`. 

Once you've created the folder which contains the SRX files, you can add the folder path in the Translation SRX location configuration inside your folder profile.  

It is recommended that for a better performance you should keep only SRX files in the folder that is configured in the folder profile. 
 
Experience Manager Guides picks the SRX rules according to the source language of the translation project. It looks for a custom SRX file for a language, and if you do not define a custom SRX file, then it picks the rules as per the out of the box translation rules. 

For details on setting up global and folder-level profiles, view *Configure authoring templates* section in Install and configure Adobe Experience Manager Guides as a Cloud Service. 

## Pass the version label to the target version 

Experience Manager Guides allows you to pass the label of the source file to the target file. This will help you easily identify the source version for the translated file.

To add the source version label in the target copy, your system administrator must enable the **Propagate source version labels to the target version** option under the **Translation** tab in **Settings**.

For example, if you have some source files with the version label `Release 1.0` applied to them, then you can also pass on the source label \(`Release 1.0`\) to the translated file.

![](images/translation-pass-source-label.png){width="650" align="left"}

>[!NOTE]
>
> The source label is only attached to one target version. If you move the source label to another version, it is automatically reflected in the latest target label.

## View version difference for Out of Sync files  

Experience Manager Guides provides the feature to check the differences between the selected version and the last translated source version of the topics. You can choose to translate the **Out of Sync** files based on the changes made.

![](images/translation-version-diff.png){width="650" align="left"}

Select the **Show difference**icon \(![](images/show-difference-icon.svg)\) for a topic to view the differences between the last translated version and the current version of the selected file.

>[!NOTE]
>
> **Show difference** icon \(![](images/show-difference-icon.svg)\) appears only for DITA files that have the translation status as **Out of Sync**.

The **Version Difference** dialog appears. It shows the **Last translated version** and the **Selected version** number on the left. The preview window displays the differences between the last translated version and the selected version of the topic.

![](images/version-diff.png){width="650" align="left"}

## Dismiss out of sync assets 

If you make changes in some of the assets, then those assets become Out of Sync. You can either re-translate the modified assets or choose to dismiss Out of Sync status. For example, if you have made some very minor changes which really don't need a translation you can mark their status to In Sync.

To dismiss the Out of Sync status, perform the following steps:

1.  Select the out of sync assets for which you want to change the status.
1.  Select the **Mark In Sync** button \(![](images/translation-mark-in-sync-icon.svg)\) on top. The **Mark In Sync** dialog appears.

    ![](images/translation-mark-in-sync.png){width="550" align="left"}

1.  Select **Force Sync**. It sets the status to In sync for the selected Out of sync assets.

>[!NOTE]
>
> **Mark In Sync** button \(![](images/translation-mark-in-sync-icon.svg)\) appears only for assets that have the translation status as Out of Sync.

## View In Progress translation projects for a map or topic 

Some of the references on your translation dashboard might be in progress status. These references have a **In Progress** link under **Translation Status** column. When you select the link, the **In Progress Projects** dialog opens. In the dialog, you can view the list of all In Progress translation projects \(along with the target language\) which contain the selected reference.

>[!NOTE]
>
> You can view the In Progress link for the translated projects created in Adobe Experience Manager Guides as a Cloud Service February 2023 release or later.

Select the name of the reference in the dialog to open it in preview mode. You can also select the translation project to start the translation.

![](images/translation-in-progress.png){width="550" align="left"}


## Automatically delete or disable a completed translation project 

>[!NOTE]
> 
>This feature is available for the new translation projects you create using Experience Manager Guides 2404 release or later.  It will not impact any existing projects.

Your administrator can configure the **Translation project cleanup after completion** option under the **Translation** tab in **Editor Settings** to disable or delete the translation projects automatically. 

For effecting document management, Experience Manager Guides provides the ability to delete the translation projects after you have completed the translation. 

You can also disable the translation projects if you want to use them later. Deleting a project deletes all files and folders present in the project. Disabling a project doesn't delete it but maintains it in the repository. But you can't update or edit a disabled project.  Deletion or disabling a project will not impact the translation status of any references.


**Parent topic:**[Introduction to the Editor](web-editor.md)
