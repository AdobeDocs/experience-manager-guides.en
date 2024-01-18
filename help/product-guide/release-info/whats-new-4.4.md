---
title: Release Notes | What's New in Adobe Experience Manager Guides 4.4 release
description: Learn about the new and enhanced features in 4.4 releases of Adobe Experience Manager Guides
exl-id: 14db7453-ccc1-4709-903f-677f55c263b2
---
# What's new in 4.4 release of Adobe Experience Manager Guides (October 2023)

This article covers the new and enhanced features in version 4.4 of Adobe Experience Manager Guides (later referred as *Experience Manager Guides*).

For more details on the upgrade instructions, compatibility matrix, and the issues fixed in this release, see [Release notes](./release-notes-4.4.md).

## Support for AI-based smart suggestions to author content
Now, you can enhance your authoring journey with Smart Suggestions, a new AI-based feature in the Web Editor. While you author your content, this intelligent feature provides real-time suggestions for content references, improving your workflow and ensuring unparalleled efficiency.

 
To keep your content correct and consistent, the search and suggestions are limited to the content owned by your organization and closely matched to the keywords that you search for.  

You can also compare the current content with similar content in the other topics. Then, you can easily pick the pieces of content from various topics and add references for them to your current topic.  Adding the content references makes updates more manageable, especially in larger documentation projects. For example, if you are creating a brochure about the latest features of your product, you can quickly pick and add real-time and updated specifications from the related documents.

Using this intelligent feature not only reduces the manual effort of searching related content and helps you focus on new content creation.  It also helps maintain consistency and also facilitates better team collaboration.  

Incorporating AI-based smart suggestion features in DITA authoring can transform your content creation process, making it more efficient and accurate. 

## Publish content to Adobe Edge Delivery Services platform
Adobe Edge Delivery Services is a suite of services that offer considerable flexibility in content authoring for your website. It helps you easily create websites that are lightweight, contain well-organized blocks, and deliver high performance.

Now Experience Manager Guides allows you to publish your DITA content to a website on the Adobe Edge Deliver Services platform.  As an administrator, you can create a publish profile for the Edge Deliver Services server. Then, as an author or a publisher, you can choose that publish profile in the output preset to publish the output to the specified server.
 
This feature helps you seamlessly integrate content directly from your DITA maps. You can easily transform your documents into pages on your website. 
Edge Delivery Services uses GitHub, so Adobe also helps you manage and deploy code directly from your  GitHub repository. You can also transfer the elements such as headings, lists, images, and font styles from the blocks in your GitHub repository to the website. 

## Enhancement in the Translation UI
The **Translation** panel has been improved.  You can view the **Available Languages** list,  and quickly select the locale to which you want to translate your project. You can also choose Select all to translate your project into all the available languages.
![translation panel](assets/translation-languages-4.4.png){width="300" align="left"}

*Select the locales to which you want to translate your project.*


## Split a list at the same level
Now you can easily split your list in the Web Editor. You can select the **Split List** option from the context menu of a list item to split the current list and begin a new list at the same level. 

![translation panel](assets/context-menu-split-list.png){width="300" align="left"}

*Select the option to split the current list.*

## Use metdata added in topicmeta for the PDF output

Metadata feature in Native PDF publishing helps in content management and helps in searching files on the internet. 
<img src="assets/pdf-metadata-4.4.png" alt="metadata tab" width=600>

*Select an option to add and customize metadata options.*

Now Experience Manager Guides provides the option to use the metadata that you have added in the topicmeta element of the DITA map to populate the metadata fields of the PDF output. This option is selected by default.


## Enhanced version history
Now Experience Manager Guides provides an enhanced version history feature which allows you to track changes made to a document over time. You can easily compare the content and the metadata of the current version with any previous version of the same document. You can also view the labels and comments for the compared versions. As an administrator, you can control the version metadata of the topic and their values to be displayed in the **Version History** dialog box. 

![Version history dialog box](assets/version-history-dialog-web-editor.png){width="550" align="left"}
  *Preview the changes in the different versions of a topic.*

This feature facilitates content reviews by displaying the added and the deleted content. It also enhances collaboration by helping the authors and reviewers monitor the changes in the different versions of the document.

