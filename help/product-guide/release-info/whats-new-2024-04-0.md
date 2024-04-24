---
title: Release Notes | What's New in the Adobe Experience Manager Guides, 2024.4.0 release
description: Learn the new and enhanced features in the 2024.4.0 release of Adobe Experience Manager Guides as a Cloud Service.
---
# What's new in the 2024.4.0 release 

This article covers the new and enhanced features of the 2024.4.0 release of Adobe Experience Manager Guides.

For the list of issues fixed in this release, view [Fixed issues in the 2024.4.0 release](fixed-issues-2024-04-0.md).

Learn about [upgrade instructions for the 2024.4.0 release](upgrade-instructions-2024-04-0.md).

## Ability to translate content into multiple languages using preconfigured language groups

Experience Manager Guides now allows you to create language groups and easily translate your content into multiple languages. This feature helps you organize and manage translations according to your organization's needs. 

For example, if you need to translate your content for some countries in Europe, you can create a language group for European languages like English (EN), French (FR), German (DE), Spanish (ES), and Italian (IT).



![translation panel](assets/translation-languages-2404.png){width="300" align="left"}

*Select the language groups or languages you want to translate your documents.* 

>[!NOTE]
>
>If a language's target folder is missing or the target language is the same as the source, it's grayed out and shows a warning sign.

As an administrator you can create language groups and configure them to multiple folder profiles. As an author, you can view the language groups that are configured on your folder profile.


Overall, creating language groups enhances the efficiency and productivity of translation projects, ultimately improving the localization process across multiple languages.


Learn how to [translate documents from the Web Editor](../user-guide/translate-documents-web-editor.md).



## Delete or disable the translation project automatically after the translation

Now, as an administrator, you can configure the translation projects to be disabled or deleted automatically after completing the translation. This feature helps you efficiently use resources and manage files after completing the translation. 

Deleting a project permanently removes all files and folders present in the project. Deletion of the translation projects also enables you to free up the occupied disk space. 

You can disable the translation projects if you want to use them later. 

![](assets/editor-setting-translation.png){width="550" align="left"}


*Configure language groups and the cleanup settings for translation projects.*


Learn more about how to [automatically delete or disable the translation project](../user-guide/translate-documents-web-editor.md#automatically-delete-or-disable-a-completed-translation-project).


## Activate the output for your maps in bulk activation collection on Preview instance

Now, in addition to activating the output for your bulk activation collection on the publish instance, Experience Manager Gudies as Cloud Services provides the feature to activate it on the **Preview** instance. 


This feature helps you activate your content to a preview instance, allowing you to check how it looks and works before activating it to the **Publish** instance.


 ![ created bulk activation collection audit history tab](assets/bulk-collection-audit-history.png){width="800" align="left"}

*View the information about the activated map outputs in the **Audit History** tab.*


Learn more about  [bulk activation](../user-guide/conf-bulk-activation-publish-map-collection.md).

## Enhancements in the data source connectors

The following enhancements have been made to the data source connectors for the 2024.4.0 release:

### Connect to Salsify, Akeneo, and Microsoft Azure DevOps Boards (ADO) data sources

In addition to the existing out-of-the-box connectors, Experience Manager Guides also provides connectors for Salsify, Akeneo, and Microsoft Azure DevOps Boards (ADO) data sources. As an administrator, you can download and install these connectors. Then, configure the installed connectors.

### Copy and paste the sample query to create a content snippet or topic

You can easily copy and paste a sample data query in the generator to create a content snippet or topic. With this feature, you don't have to remember the syntax or create a  query manually. Instead of manually typing the query, you can copy and paste a sample query, edit it, and use it to fetch the data per your requirements. 

![insert content snippet dialog box](assets/insert-content-snippet.png){width="800" align="left"}

 *Copy and edit a sample query to create the content snippet.*

### Connect to JSON data files using a file connector 


Now, as an administrator, you can configure a JSON file connector to use JSON data files as a data source. Use the connector to import the JSON files from your computer or the Adobe Experience Manager Assets. Then, as an author, you can create content snippets or topics using the generators.

This feature helps you use the data stored in your JSON files and reuse it across various snippets. The content is also updated dynamically whenever you update the JSON files.

### Configure multiple resource URLs for a connector to create content snippets or topics

As an administrator, you can configure multiple resource  URLs for some connectors like Generic REST Client, Salsify, Akeneo, and Microsoft Azure DevOps Boards (ADO).

Then, as an author, connect with the data sources to create content snippets or topics using the generators. This feature is handy as you don't have to create a data source for each URL. It helps you to quickly fetch data from any of the resources for a particular data source in a single content snippet or topic.

View more details about the data source connectors and how to [configure a data source connector from the user interface](../cs-install-guide/conf-data-source-connector-tools.md).

Learn how to [use data from your data source](../user-guide/web-editor-content-snippet.md).

## Customize your Web Editor experience with new UI of user preferences

The **User Preferences** dialog box in the Web Editor now includes a new **Appearance** tab. This new tab allows you to conveniently configure the most common look-and-feel preferences in the Web Editor interface.

You can configure to view the files by title or filename, and change the theme of the application and the source view. It also helps you configure the settings to locate an open file in the repository view and to handle the non-breaking spaces.

![appearance tab of user preferences](assets/user_preference_editor_appearance.png){width="550" align="left"}

*Customize the appearance according to your preferences.*

Learn more about the **User preferences** feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.

## Locate an open file in the repository view of the Web Editor

Select the **Always locate files in the repository** option in the **User Preferences** to quickly navigate and locate your file in the repository view. You don't have to manually search for it. 

While editing, this feature also helps you easily view the file's location within the repository hierarchy.

For more details, view [locate an open file in the repository view](../user-guide/web-editor-edit-topics.md#locate-an-open-file-in-the-repository-view).


## Improved handling of non-breaking spaces in the Web Editor

Experience Manager Guides allows you to show a non-breaking space indicator while editing documents in the Web Editor. It also improves the handling of non-breaking spaces. 
It converts multiple consecutive white spaces into a single space to preserve the WYSIWYG view of the document in the Web Editor. This feature also helps improve the overall appearance and professionalism of the document.


For more details, view the [other features of the Web Editor](../user-guide/web-editor-other-features.md).




## Disable the postprocessing for selective folders on Adobe Experience Manager Assets


As an administrator, you can now disable the postprocessing and generation of UUIDs for selective folders on Experience Manager Assets. This configuration might be helpful, especially when dealing with many assets or complex folder structures. It also helps multiple users quickly upload the assets concurrently without interfering with each other.  

Disabling postprocessing for a folder also affects all its child folders. However, Experience Manager Guides now offers the ability to selectively enable postprocessing for individual child folders within the ignored folder.

Learn how to [disable postprocessing for a folder](../cs-install-guide/conf-folder-post-processing.md).

## Revamped experience to search and filter files in the repository view

Now, you have an enhanced experience while filtering files. The revamped functionality to filter files provides an improved way to effortlessly search and navigate through files. 


![search files in repository view](assets/repository-filter-search-2404.png){width="300" align="left"}

*Search for the files containing the text `general purpose.`*

Enjoy benefits such as quicker access to relevant files and a more intuitive user interface, making your search experience smoother and more efficient. 

![quick search filter ](assets/repository-filter-search-quick.png) {width="300" align="left"}

*Use the quick filters to search for DITA and Non-DITA files.*

Learn more about the **Filter Search** feature in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section.

## Segregated list to view and insert valid elements according to their position

While editing a document in the Web Editor, you can now view a segregated list of elements that are valid at the current location and outside of the current location. Based on your requirements, you choose an element from the following options:

* **Valid elements at the current location** that you can insert at the current cursor location itself.
* **Valid elements outside the current location** that you can insert after any of the parents for the current element within the element hierarchy.

![Insert element dialog](assets/insert-element-dialog.png){width="300" align="left"}

*View the segregated lists of valid elements to insert an element at the current location.* 


This split list of valid elements helps you maintain the content structure and follow the DITA standards. 

Learn more about the **Insert Element** feature in the [Secondary toolbar](../user-guide/web-editor-features.md#2051ea0j0y4) section. 


## Content Properties Type appears as a dropdown menu

Now, the Content Properties **Type** appears as a dropdown menu. You can view and select the tags of the complete hierarchy for the current tag from the dropdown.

This dropdown menu helps you quickly access the relevant tags within the hierarchical structure.


 ![type dropdown menu in content properties](assets/content-properties-type.png){width="300" align="left"}

 *Select a tag from the hierarchy for the current tag.*

Learn more about the **Content Properties** feature in the [Right Panel](../user-guide/web-editor-features.md#id2051eb003yk) section. 



## Improved performance while checking files in bulk from the Map Editor

Experience Manager Guides improves the performance and experience of the bulk files check-in feature from the Map Editor. This improvement helps you check in the files in bulk more quickly. 
You can also view the progress of the check-in operation for the files from the **Save As New Version and Unlock** dialog box. Finally, the success message appears after the operation is complete and all selected checked-out files are checked-in.

![Save as new version and unlock dialog box](./assets/save-version-lock.png){width="300" align="left"}

*View the list and status of the files checked in bulk from the Map Editor.*

Learn how to [work with the Advanced Map Editor](../user-guide/map-editor-advanced-map-editor.md)

## Download the temporary file while generating the output through DITA-OT

You can also download the temporary files generated when you publish the AEM Site, HTML, Custom, JSON, or PDF output through DITA-OT. This feature helps you to analyze any issues that might occur during the output generation process and troubleshoot effectively.  
You can also download the metadata.xml file if you have selected any metadata properties that have been passed to the output generated using DITA-OT. 

For more details about the presets, view [Understanding the output presets](../user-guide/generate-output-understand-presets.md).


## Replace IMS JWT credentials with IMS OAuth credentials for Microservice-based publishing
 

The Service Account (JWT) credentials have been deprecated in favor of the **OAuth Server-to-Server** credentials. Your applications using the Service Account (JWT) credentials will stop working after Jan 1, 2025. You must migrate to the new credential by Jan 1, 2025, to ensure that your application continues functioning. 


The cloud publishing service for Experience Manager Guides is now secured by Adobe IMS OAuth-based authentication. Learn how to [configure microservice-based publishing with OAuth authentication](../knowledge-base/publishing/configure-microservices-imt-config.md). 
