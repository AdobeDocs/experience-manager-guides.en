---
title: Release Notes | What's New in the Adobe Experience Manager Guides, 2024.2.0 release
description: Learn the new and enhanced features in 2024.2.0 release of Adobe Experience Manager Guides as a Cloud Service.
---
# What's new in the 2024.2.0 release 

This article covers the new and enhanced features in the 2024.2.0 release of Adobe Experience Manager Guides.

For the list of issues that have been fixed in this release, view [Fixed issues in the 2024.2.0 release](fixed-issues-2024-2-0.md).


Learn about [upgrade instructions for the 2024.2.0 release](upgrade-instructions-2024-2-0.md).



## AI-powered Smart Suggestions to add content references while authoring content

Now, you can enhance your authoring journey with Smart Suggestions, a new AI-based feature in the Web Editor. While you author your content, this intelligent feature provides real-time suggestions for content references, improving your workflow, adding accuracy, and ensuring unparalleled efficiency.

 
To keep your content correct and consistent, the search and suggestions are limited to the content owned by your organization and closely matched to the keywords that you search for.  

![Smart suggestions panel in the Web Editor ](assets/web-editor-smart-suggestion.png) {width="800" align="left"}


*View Smart Suggestions to find and add matching content references from your content repository.*

You can also compare the current content with similar content in the other topics. Then, you can easily pick the pieces of content from various topics and add them as content references into your current topic. Adding the content references makes updates more manageable, especially in larger documentation projects. For example, you are creating a brochure about the latest features of your product. In that case, you can quickly add the updated specifications as content references from the related feature documents.

Using this intelligent feature reduces the manual effort of searching related content and helps you focus on new content creation.  It also helps maintain consistency and also facilitates better team collaboration.  

## Revamped version history feature in the Web Editor

Now Experience Manager Guides provides an enhanced version history feature which allows you to compare the changes made to a document over time. In the new side by side view, you can easily compare the content and the metadata of the current version with any previous version of the same document. You can also view the labels and comments for the compared versions. As an administrator, you can control the version metadata of the topic and their values to be displayed in the **Version History** dialog box. 

![Version history dialog box](assets/version-history-dialog-web-editor.png){width="800" align="left"}
  *Preview the changes in the different versions of a topic.*


Learn more about the **Version History** feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section. 

## Improved user experience in the Translation panel

The **Translation** panel has been improved.  You can view the **Available Languages** list and quickly select the locale in which you want to translate your project. With a single selection, you can also choose **Select all** to translate your project into all the available languages.

![translation panel](assets/translation-languages-4.4.png){width="300" align="left"}

*Select the locales in which you want to translate your project. Choose the default, baseline, or the latest version of files for translation.*

Learn more about how to [translate content](../user-guide/translation.md).


## Improved search logic in the Insert Element dialog box

You can now easily find the elements in the Insert Element dialog box.  You can type a string in the search box and get a list of all the valid elements that begin with the entered string.

For example, while editing a paragraph you want to insert an element, then you can search a character 't' to get
all valid elements that begin with ‘t’.


![Insert dialog box](assets/insert-element.png){width="300" align="left"}

*Type a character to search for all valid elements that begin with the character.*


For more details, view the **Insert Element** feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section. 


## Ability to split the current list and start with a new list item at the same level

Now, you can easily split your list in the Web Editor. Select the **Split List** option from the context menu of a list item to split the current list. A new list is created at the same level, starting with the list item you selected for the split.  

![translation panel](assets/context-menu-split-list.png){width="300" align="left"}

*Select the option to split the current list.*

For more details, view the **Insert List** feature description in the [Left Panel](../user-guide/web-editor-features.md#id2051EA0M0HS) section. 

## Access file properties in the source mode of authoring 

Now, you can access the right panel's **File Properties** feature in all four modes or views:  Layout, Author, Source, and Preview.  This helps you view your file's properties even when you switch between the different modes.

For more details, view the **File Properties** feature description in the [Right Panel](../user-guide/web-editor-features.md#id2051EB003YK) section. 

## Ability to publish multiple output presets with dynamic baselines in parallel 

Experience Manager provides the feature to create baselines by automatically picking the topics according to the label applied to them. Now, you can also seamlessly publish multiple output presets with automatic baselines of the same DITA map. You don’t have to publish only one preset at a time but can easily publish multiple output presets in parallel.


## Native PDF enhancements

The following Native PDF enhancements have been done in the 2024.2.0 release:

### Pass assets metadata to the PDF output

Experience Manager now provides the capability to pass the assets' metadata properties from the DITA map  to the PDF output. 
From the Native PDF output preset, you can choose the metadata that you want to pass to PDF publishing process. You can select both the custom and the default properties.  The selected metadata properties are passed to the PDF file generated using Native PDF.

This feature is handy as it helps you  keep your asset properties such as author, creation date, or document title consistent. This makes it easier to organize, search, and categorize your documents.

For more details, view the **Advanced** settings in the [Publish PDF output](../web-editor/native-pdf-web-editor.md).


### Use metadata added in the `topicmeta` element for the PDF output

Metadata feature in Native PDF publishing helps in content management and helps in searching files on the internet. 
<img src="assets/pdf-metadata-4-4.png" alt="metadata tab" width=800>

*Select an option to add and customize metadata options.*

Now Experience Manager Guides provides the option to use the metadata that you have added in the `topicmeta` element of the DITA map to populate the metadata fields of the PDF output. This option is selected by default.

This feature helps in better document management, ensures consistency, and makes your documents searchable.

To know more, view the **Metadata** tab in the [Publish PDF output](../web-editor/native-pdf-web-editor.md).