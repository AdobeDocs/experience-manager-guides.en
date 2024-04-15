---
title: Release Notes | What's New in the Adobe Experience Manager Guides, 2024.4.0 release
description: Learn the new and enhanced features in 2024.4.0 release of Adobe Experience Manager Guides as a Cloud Service.
---
# What's new in the 2024.4.0 release 

This article covers the new and enhanced features in the 2024.2.0 release of Adobe Experience Manager Guides.

For the list of issues that have been fixed in this release, view [Fixed issues in the 2024.4.0 release](fixed-issues-2024-2-0.md).

Learn about [upgrade instructions for the 2024.4.0 release](upgrade-instructions-2024-2-0.md).

## Create translation groups to translate into multiple languages

Experience Manager Guides allows you to translate your content into a group of languages. This feature helps you organize and manage translations according to the needs of your organization. For example, if you need to translate your content for some countries in Europe, you can create a language group for European languages like English (EN), French (FR), German (DE), Spanish (ES), and Italian (IT).

These language groups help you quickly translate your DITA content into the selected languages under various language groups.

![translation panel](assets/translation-languages-2404.png){width="300" align="left"}

*Select the language groups or languages in which you want to translate your documents.* 

Your admin can create language groups and configure them to particular folder profiles. As a user, you can view the language groups that are configured to your folder profile.


Overall, creating language groups enhances the efficiency and scalability of translation projects, ultimately improving the localization process across multiple languages.



Learn how to [translate documents from the Web Editor](../user-guide/translate-documents-web-editor.md).


## Delete or disable the translation project automatically after translation

Now, Experience Manager Guides allows you to disable or delete a translation project after it is complete. As an administrator, you can configure the translation projects to be disabled or deleted automatically after the translation is completed. 

You can disable the translation projects if you want to use them later. Deleting a project permanently deletes all files and folders present in the project.

This feature helps you optimize the resources and efficiently manage the files after completing the translation. Deletion of the translation projects also enables you to free up the occupied disk space. 

![](assets/editor-setting-translation.png){width="550" align="left"}


*Configure language groups and the settings for translating the content.*


Learn more about how to  [automatically delete or disable the translation project](../user-guide/translate-documents-web-editor.md#automatically-delete-or-disable-a-completed-translation-project).

## UI improvements and a separate tab to change the appearance of the Web Editor

Now you can view a separate tab on appearances in the **User Preferences**. This helps to change your preferences easily. The new **Appearance** tab is better organized and more user-friendly. You can configure to view the files by title or filename, and change the theme of the application and the source view. It also helps you configure the settings to locate an open file in the repository view and to handle the non-breaking spaces.

![appearance tab of user preferences](assets/user_preference_editor_appearance.png){width="550" align="left"}

*Cusotmize the appearance accoording to your preferences.*

## Locate an open file in the repository view of the Web Editor

You can effeciently navigate and locate your file in the repository view while you are editing it. This feature also helps you quickly view the  file's location within the repository hierarchy.  

For more details, view [locate an open file in the repository view](../user-guide/web-editor-edit-topics.md#locate-an-open-file-in-the-repository-view)


## Improved handling of non-breaking spaces in Web Editor

Experience Manager Guides allows you to display an indicator while editing documents in the Web Editor. It also improves the handling of non-breaking spaces. 
To preserve the WYSIWYG view of the Web Editor, it converts multiple consecutive white spaces into a single space. This also helps improve the overall appearance and professionalism of the document.


For more details, view the [other features of the Web Editor](../user-guide/web-editor-other-features.md).


## Enhancements in the data source connectors

### Connect to Salsify, Akeneo, and Microsoft Azure DevOps Boards (ADO) data sources

Besides the out-of-the-box connectors, Experience Manager Guides also provides the connectors for Salsify, Akeneo, and Microsoft Azure DevOps Boards  (ADO) data sources. As an administrator you can download and install them. After  installing, you can configure these connectors.  

### Copy and paste the sample query to create a content snippet or topic

You can easily copy and paste the sample data query to create a content snippet or topic using the generators. With this feature, you don't have to remember the syntax or create a manual query.   Instead of manually typing out the query, you can copy and paste a sample query, edit it, and use it to fetch the data per your requirements. 

![insert content snippet dialog box](assets/insert-content-snippet.png){width="800" align="left"}

 *Edit and insert a data snippet.*

### Connect to JSON data files using a file connector 

Now as an adminsitrator, Experience Guides allows you to easily connect to JSON data files using a file connector. You can use the JSON files from your computer or from the Adobe Experience Manager assets. Then as an user, create the content snippets or topics using the generators.

This feature helps you utilize the data stored in your JSON files, reuse it across various snippets, and also update it dynamically.  

### Connect to multiple resources and use the data to create content snippets or topics

As an adminsitrator you can add or use multiple resources based on different URLs for some connectors like Generic REST Client, Salsify, Akeneo, and Microsoft  Azure DevOps Boards  (ADO). 

Then, as an user connect with them to create content snippets or topics using the generators for them. This feature is handy as you do not have to create data source for each URL. It helps you to quickly fetch data from any of the resources for a particular data source in a single content snippet or topic. 

View more details about the data source connectors and how to [configure a data source connector from the user interface](../cs-install-guide/https://experienceleague-review.corp.adobe.com/docs/experience-manager-guides/using/install-guide/cs-ig/web-editor-configs-cs/conf-data-source-connector-tools.html?lang=en).

Learn how to [use data from your data source](../user-guide/web-editor-content-snippet.md).

## Improved performance while checking files in bulk  from the Map Editor

The performance and experience of the checking-in feature for bulk files from the Map Editor have been improved. This will help you check in files in bulk more quickly. 
You can also view the progress of checking in the topics from the **Save As New Version and Unlock** dialog box. Finally, the success message appears after all selected checked out files are checked in. 

![Save as new version and unlock dialog box](./assets/save-version-lock.png){width="300" align="left"}

*View the list and status of the files getting checking in bulk from the Map Editor.*

## Revamped experience to search and fitler files in the repository view

Now you have a very enhanced experience while filtering files. The revamped filter functionality provides an improved way to search and navigate through files effortlessly. Enjoy benefits such as better organization of  quicker access to relevant files, streamlined organization, and a more intuitive user interface, making your search experience smoother and more efficient. 

![search files in repository view](assets/repository-filter-search-2404.png){width="300" align="left"}

*Apply filters to search for the files containing the text `general purpose.`*