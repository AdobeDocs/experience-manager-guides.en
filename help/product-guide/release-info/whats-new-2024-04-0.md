---
title: Release Notes | What's New in the Adobe Experience Manager Guides, 2024.4.0 release
description: Learn the new and enhanced features in the 2024.4.0 release of Adobe Experience Manager Guides as a Cloud Service.
---
# What's new in the 2024.4.0 release 

This article covers the new and enhanced features of the 2024.4.0 release of Adobe Experience Manager Guides.

For the list of issues fixed in this release, view [Fixed issues in the 2024.4.0 release](fixed-issues-2024-04-0.md).

Learn about [upgrade instructions for the 2024.4.0 release](upgrade-instructions-2024-04-0.md).

## Create language groups to translate into multiple languages

Experience Manager Guides allows you to translate your content into a group of languages. This feature helps you organize and manage translations according to your organization's needs. For example, if you need to translate your content for some countries in Europe, you can create a language group for European languages like English (EN), French (FR), German (DE), Spanish (ES), and Italian (IT).

These language groups help you quickly translate your DITA content into the selected languages under various language groups.

![translation panel](assets/translation-languages-2404.png){width="300" align="left"}

*Select the language groups or languages you want to translate your documents.* 

Your admin can create language groups and configure them to particular folder profiles. As a user, you can view the language groups configured to your folder profile.


Overall, creating language groups enhances the efficiency and scalability of translation projects, ultimately improving the localization process across multiple languages.


Learn how to [translate documents from the Web Editor](../user-guide/translate-documents-web-editor.md).



## Delete or disable the translation project automatically after the translation

Now, Experience Manager Guides allows you to disable or delete a translation project after completion. As an administrator, you can configure the translation projects to be disabled or deleted automatically after completing the translation. 

You can disable the translation projects if you want to use them later. Deleting a project permanently removes all files and folders present in the project.

This feature helps you efficiently use resources and manage files after completing the translation. Deletion of the translation projects also enables you to free up the occupied disk space. 

![](assets/editor-setting-translation.png){width="550" align="left"}


*Configure language groups and the settings for translating the content.*


Learn more about how to [automatically delete or disable the translation project](../user-guide/translate-documents-web-editor.md#automatically-delete-or-disable-a-completed-translation-project).


## Activate your bulk activation map collection on the publish instance

With the Bulk Activation feature, you can quickly and easily activate your content from the authoring instance.  Now, in addition to activating the output for your bulk activation map collection on the publish instance, Experience Manager Gudies as Cloud Services provides the feature to activate it on the Preview instance. 

It also provides the following enhancements for your bulk activation map collection:

* Once the output is activated for the selected map files, the **Audit History** tab is updated, and the latest activated output appears on top. 

* If you generate the output on Experience Manager Guides as a Cloud Service, you can view the output's destination as **Publish** or **Preview**.

* The **Published** column is updated with the publishing date and time.

* The filters in the left panel are updated when you switch from the **Maps and Presets** tab to the Audit History tab and vice versa.

This feature helps you activate your content to a preview instance, allowing you to check how it looks and works before activating it to the **Publish** instance.


 ![ created bulk activation collection audit history tab](assets/bulk-collection-audit-history.png){width="800" align="left"}

*View the information about the activated map outputs in the **Audit History** tab.*


Learn how to [activate bulk activation map collection](../user-guide/conf-bulk-activation-publish-map-collection.md)

## Enhancements in the data source connectors

### Connect to Salsify, Akeneo, and Microsoft Azure DevOps Boards (ADO) data sources

In addition to the out-of-the-box connectors, Experience Manager Guides also provides connectors for Salsify, Akeneo, and Microsoft Azure DevOps Boards (ADO) data sources. As an administrator, you can download and install these connectors and configure them after installing them.

### Copy and paste the sample query to create a content snippet or topic

You can easily copy and paste the sample data query in the generators to create a content snippet or topic. With this feature, you don't have to remember the syntax or create a manual query. Instead of manually typing out the query, you can copy and paste a sample query, edit it, and use it to fetch the data per your requirements. 

![insert content snippet dialog box](assets/insert-content-snippet.png){width="800" align="left"}

 *Edit and insert a data snippet.*

### Connect to JSON data files using a file connector 

Now, as an administrator, Experience Guides allows you easily connect to JSON data files using a file connector. You can use the JSON files from your computer or the Adobe Experience Manager assets. Then, as a user, you can create content snippets or topics using the generators.

This feature helps you use the data stored in your JSON files, reuse it across various snippets, and update it dynamically.

### Connect to multiple resources and use the data to create content snippets or topics

As an administrator, you can add or use multiple resources based on different URLs for some connectors like Generic REST Client, Salsify, Akeneo, and Microsoft Azure DevOps Boards (ADO).

Then, as a user, connect with them to create content snippets or topics using the generators. This feature is handy as you don't have to create a data source for each URL. It helps you to quickly fetch data from any of the resources for a particular data source in a single content snippet or topic.

View more details about the data source connectors and how to [configure a data source connector from the user interface](../cs-install-guide/conf-data-source-connector-tools.md).

Learn how to [use data from your data source](../user-guide/web-editor-content-snippet.md).

## UI improvements and a separate tab to change the appearance of the Web Editor

You can now view a separate tab on appearances in the **User Preferences**, which helps you change your preferences easily. The new **Appearance** tab is better organized and more user-friendly. You can configure to view the files by title or filename, and change the theme of the application and the source view. It also helps you configure the settings to locate an open file in the repository view and to handle the non-breaking spaces.

![appearance tab of user preferences](assets/user_preference_editor_appearance.png){width="550" align="left"}

*Customize the appearance according to your preferences.*

Learn more about the **User preferences** feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.

## Locate an open file in the repository view of the Web Editor

While editing, you can efficiently navigate and locate your file in the repository view. This feature also helps you quickly view the file's location within the repository hierarchy.

For more details, view [locate an open file in the repository view](../user-guide/web-editor-edit-topics.md#locate-an-open-file-in-the-repository-view).


## Improved handling of non-breaking spaces in Web Editor

Experience Manager Guides allows you to display an indicator while editing documents in the Web Editor. It also improves the handling of non-breaking spaces. 
It converts multiple consecutive white spaces into a single space to preserve the WYSIWYG view of the Web Editor. This feature also helps improve the overall appearance and professionalism of the document.


For more details, view the [other features of the Web Editor](../user-guide/web-editor-other-features.md).




## Disable the post processing for a folder uploaded to the Adobe Experience Manager Assets server


As an administrator, you can now disable the post processing and generation of UUIDs when uploading your files and folders to the Experience Manager Assets server. This configuration might be helpful, especially when dealing with many assets or complex folder structures. It also helps multiple users quickly upload assets concurrently without interfering with each other.  

If you disable the post-processing for a folder, all its child folders are also ignored. However, Experience Manager Guides also allows you to enable the post processing of a child folder under the ignored folder. 



## Revamped experience to search and filter files in the repository view

Now, you have a an enhanced experience while filtering files. The revamped filter functionality provides an improved way to effortlessly search and navigate through files. Enjoy benefits such as quicker access to relevant files and a more intuitive user interface, making your search experience smoother and more efficient. 

![search files in repository view](assets/repository-filter-search-2404.png){width="300" align="left"}

*Apply filters to search for the files containing the text `general purpose.`*


## Clear list to view and insert valid elements according to their position

While editing a document in the Web Editor, you can view a clearly split list of valid elements and insert them at the current location. 

 - **Valid elements at the current location** that you can insert at the current cursor location itself.
 - **Valid elements outside the current location** that you can insert after any of the parents for the current element within the element hierarchy.

![Insert element dialog](assets/insert-element-dialog.png){width="300" align="left"}

This split list of valid elements helps you maintain the content structure and follow the DITA standards. 

Learn more about the **Insert Element** feature description in the [Secondary toolbar](../user-guide/web-editor-features.md#2051ea0j0y4) section. 

## Content Properties Type appears as a dropdown menu

Now the Content Properties **Type** appears as a dropdown menu. You can view and select the tags of the complete hierarchy for the current tag from the dropdown.

This dropdown menu helps you quickly access the relevant tags within the hierarchical structure.


 ![type dropdown menu in content properties](assets/content-properties-type.png){width="300" align="left"}

 *Select a tag from the hierarchy for the current tag.*

Learn more about the **Content Properties** feature description in the [Right Panel](../user-guide/web-editor-features.md#id2051eb003yk) section. 



## Improved performance while checking files in bulk from the Map Editor

Experience Manager Guides improves the performance and experience of the checking-in feature for bulk files from the Map Editor. This improvement helps you check in files in bulk more quickly. 
You can also view the progress of checking in the topics from the **Save As New Version and Unlock** dialog box. Finally, the success message appears after all selected checked out files are checked-in. 

![Save as new version and unlock dialog box](./assets/save-version-lock.png){width="300" align="left"}

*View the list and status of the files checked in bulk from the Map Editor.*

## Download the temporary file while generating the output through DITA-OT

You can also download the temporary files generated when you publish the AEM Site, HTML, Custom, JSON, or PDF output through DITA-OT. This feature helps you to analyze any issues that might occur during the output generation process and troubleshoot effectively.  
You can also download the metadata.xml file if you have selected any metadata properties that have been passed to the output generated using DITA-OT. 




For more details about the presets, [Understanding the output presets](../user-guide/generate-output-understand-presets.md).