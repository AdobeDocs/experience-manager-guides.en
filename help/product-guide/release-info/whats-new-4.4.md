---
title: Release Notes | What's New in Adobe Experience Manager Guides 4.4 release
description: Learn about the new and enhanced features in 4.4 releases of Adobe Experience Manager Guides
---
# What's new in 4.4 release of Adobe Experience Manager Guides (January 2024)

This article covers the new and enhanced features in version 4.4 of Adobe Experience Manager Guides (later referred as *Experience Manager Guides*).

For more details on the upgrade instructions, compatibility matrix, and the issues fixed in this release, see [Release notes](./release-notes-4.4.md).



## Enhancement in the Translation UI

The **Translation** panel has been improved.  You can view the **Available Languages** list and quickly select the locale to which you want to translate your project. You can also choose Select all to translate your project into all the available languages.
![translation panel](assets/translation-languages-4.4.png){width="300" align="left"}

*Select the locales to which you want to translate your project.*
To learn more about translation, view [](../user-guide/translation.md)

## Split a list at the same level

Now, you can easily split your list in the Web Editor. You can select the **Split List** option from the context menu of a list item to split the current list and begin a new list at the same level. 

![translation panel](assets/context-menu-split-list.png){width="300" align="left"}

*Select the option to split the current list.*

For more details, view the **Insert List** feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section. 

## Pass assets metadata to the PDF output

Now, Experience Manager provides the capability to pass the assets' metadata properties from the DITA map  to the PDF output. 
From the Native PDF output preset, you can choose the metadata that you want to pass to Native PDF publishing. You can select both the custom and the default properties.  The selected metadata properties are passed to the PDF file generated using Native PDF.

This feature is handy as it helps you  keep your asset properties such as author, creation date, or document title consistent. This makes it easier to organize, search, and categorize your documents.

For more details, view the **Advanced** settings in the [Publish PDF output](../web-editor/native-pdf-web-editor.md).

## Use metadata added in the `topicmeta` element for the PDF output

Metadata feature in Native PDF publishing helps in content management and helps in searching files on the internet. 
<img src="assets/pdf-metadata-4.4.png" alt="metadata tab" width=800>

*Select an option to add and customize metadata options.*

Now Experience Manager Guides provides the option to use the metadata that you have added in the `topicmeta` element of the DITA map to populate the metadata fields of the PDF output. This option is selected by default.

This feature helps in better document management, ensures consistency, and makes your documents searchable.

To know more, view the **Metadata** tab in the [Publish PDF output](../web-editor/native-pdf-web-editor.md).

## Enhanced version history

Now Experience Manager Guides provides an enhanced version history feature which allows you to track changes made to a document over time. You can easily compare the content and the metadata of the current version with any previous version of the same document. You can also view the labels and comments for the compared versions. As an administrator, you can control the version metadata of the topic and their values to be displayed in the **Version History** dialog box. 

![Version history dialog box](assets/version-history-dialog-web-editor.png){width="800" align="left"}
  *Preview the changes in the different versions of a topic.*

This feature facilitates content reviews by displaying the added and the deleted content. It also enhances collaboration by helping the authors and reviewers monitor the changes in the different versions of the document.

Learn more about the **Version History** feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section. 

## Search exact matching elements in the Insert Element dialog box

Now you can easily find the elements in the Insert Element dialog box.  You can type a string in the search box and search for the elements that begin with the entered string.
For example, you want to insert an element within a paragraph.  Enter ‘t’ to search for all valid elements that begin with ‘t’.

![Insert dialog box](assets/insert-element.png){width="300" align="left"}
*Type a string to find elements beginning with the string.* 

For more details, view the **Insert Element** feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section. 

## Access file properties in all modes of Web Editor

Now, you can access the right panel's **File Properties** feature in all four modes or views:  Layout, Author, Source, and Preview.  This helps you view your file's properties even when you switch between the different modes.

For more details, view the **File Properties** feature description in the [Right Panel](../user-guide/web-editor-features.md#id2051EB003YK) section. 