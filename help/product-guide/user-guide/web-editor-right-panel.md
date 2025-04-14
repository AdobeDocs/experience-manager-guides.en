---
title: Right panel in Editor  
description: Get to know the Right panel in the Editor. Learn about Editor interface and features in Adobe Experience Manager Guides.
feature: Authoring, Features of Web Editor
role: User
---
# Right panel in the Editor 

The right panel contains information about the currently selected document.

>[!NOTE]
>
> The right panel is resizable. To resize the panel, bring the cursor on the panel boundary, the cursor changes to a double-headed arrow, select and drag to resize the panel width.

The right panel gives you access to the following features:

- [Content properties](#content-properties)
- [File properties](#file-properties)
- [Review](#review)
- [Track changes](#track-changes)
- [Schematron](#schematron)

## Content properties

You can access the **Content properties** feature by selecting the **Content properties** icon in the right panel. The **Content properties** panel contains information about the type of currently selected element in the document and its attributes. 

**Type**: You can view and select the tags of the complete hierarchy for the current tag from the dropdown.

**Attributes**: The **Attributes** dropdown panel is available in Layout, Author, and Source views. You can easily add, edit, or delete the attributes.

<details>
    <summary> Steps to add attributes </summary>


1. Select **Add**. 

    ![attrubutes in content properties](images/properties-tab-attributes_cs.png){width="300" align="left"}

1. In the **Attribute** dropdown panel, select the attribute from the dropdown list and specify an attribute's value.  Then select **Add**. 

    ![attributes panel with multiple attributes ](images/attributes-multiple-properties.png){width="300" align="left"}

1. To edit the attribute, hover over it and select **Edit** ![edit-icon](images/edit_pencil_icon.svg).   

1. To delete the attribute, hover over it and select **Delete** ![delete-icon](images/Delete_icon.svg). 

</details>


>[!NOTE]
>
> Even if your topic contains referenced content, you can add attributes on it using the properties panel.

If your administrator has created a profile for attributes, then you will get those attributes along with their configured values. Using the content properties panel, you can choose those attributes and assign them to relevant content in your topic. This way you can also create conditional content, which can then be used to create conditional output. For more information about generating output using conditional presets, view [Use condition presets](generate-output-use-condition-presets.md#).



## File properties

View the properties of the selected file by selecting the File properties icon in the right panel. The File properties feature is available in all four modes or views: Layout, Author, Source, and Preview.

The File properties have the following two sections:

**General**

The General section gives you access to the following features:

![file-properties](images/file-properties-general.png){width="300" align="left"}

- **File name**: Displays the filename of the selected topic. The filename is hyperlinked to the properties page of the selected file.
- **ID**: Displays the ID of the selected topic.
- **Tags**: These are the metadata tags of the topic. They are set from the tags field in the properties page. You can type or select them from the dropdown.  The tags appear under the dropdown. To delete a tag, select the cross icon next to the tag. 
-  **Edit more properties**: You can edit more properties from the file properties page.  
- **Language**: Shows the language of the topic. It is set from the language field in the properties page.
- **Created on**: Displays date and time on which the topic was created.
- **Modified on**: Displays the date and time on which the topic was modified. 
- **Locked by**: Shows the user who locked the topic.
- **Document state**: You can select and update the document state of the currently opened topic. For more details, view [Document State](web-editor-document-states.md#).

>[!NOTE]
>
> You can copy the attribute values of the various fields in the File properties to the clipboard.

**References**

The References section gives you access to the following features:

![](images/file-properties-references.png){width="300" align="left"}

- **Used in**: The Used in references list the documents where the current file is being referred or used.
- **Outgoing links:** The Outgoing links list the documents that are referred to in the current document.

By default, you can view the files by titles. As you hover over a file, you can view the file title and the file path as a tooltip.   

>[!NOTE]
>
> As an administrator, you can also choose to view the list of files by filenames in the Editor. Select the **File name** option of the **Editor files display configuration** section in **User preferences**.

>[!NOTE]
>
> All Used in and Outgoing references are hyperlinked to the documents. You can easily open and edit the linked documents.

In addition to opening files, you can also perform many actions using the **Options** menu in the References section. Some of the actions that you can perform include Edit, Preview, Copy UUID, Copy Path, Add to collections, Properties.

## Review

Selecting the Review icon opens the review panel wherein you can select a review task for the currently opened document and view comments.

![](images/review-panel-before-opening.png){width="300" align="left"}

If you have created multiple Review projects, you can select one from the drop-down and access the review comments.

Using the review panel, you can view and post replies to the comments given on the topic. You can accept or reject the comments one by one.

>[!NOTE]
>
> The comment box and reply box support multi-line entries and allows users to expand it as needed for providing comprehensive comments as well as detailed reply to the comments. You can use **Shift** + **Enter** to go to the next line while writing the comments or replies.

For more information, view [Address review comments](review-address-review-comments.md#).

## Track changes 

Using the Tracked changes feature of the right panel, you can view the information of all updates made in a document. You can also search for any specific updates made to the document.

>[!NOTE]
>
> Tracked changes feature shows all updates that have been tracked using the Enable/Disable Track Changes feature of the [Tab bar](#tab-bar).

## Schematron

"Schematron" refers to a rule-based validation language used to define tests for an XML file. The Editor supports Schematron files. You can import the Schematron files and also edit them in the Editor. Using a Schematron file you can define certain rules and then validate them for a DITA topic or a map.

Learn how to work with Schematron files in Experience Manager Guides, refer to [Support for Schematron files](./support-schematron-file.md).



**Parent topic:**[Introduction to the Editor](web-editor.md)
