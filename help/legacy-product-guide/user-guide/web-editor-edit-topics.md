---
title: Edit topics in the Web Editor
description: Learn to edit topics in the web editor. Know about various editing features to modify your topic files in AEM Guides.
feature: Authoring, Web Editor
role: User
hide: yes
exl-id: 0341bdec-9635-4ced-b1c6-789b4e1aded8
---
# Edit topics in the Web Editor {#id2056B040VUI}

The Web Editor comes with a range of editing features that let you easily create or modify your topic files. Broadly, you would perform the following steps to edit a topic in the Web Editor.

>[!IMPORTANT]
>
> If you encounter an application error while working on the Web Editor, refresh the page to continue working.

1.  To make changes in your topic, click within the text boundary of the required element and start making edits.

1.  To insert a specific element, click at the end of the element after which you want to insert the new element and click the required element icon in the toolbar. You can also use the keyboard shortcut `Alt+Enter` to invoke the **Insert Element** popup.

    A list of element appears that can be used in the topic. AEM Guides does an intelligent placing of elements as per their valid location in the topic.

    >[!NOTE]
    >
    > You can also choose which icon to be displayed in the toolbar by configuring the `ui_config.json` file located at - `/etc/designs/fmdita/clientlibs/xmleditor/`. For more information about customizing features, contact your system administrator.

1.  Once you have finished editing your document, click **Save**.

    >[!NOTE]
    >
    > If you do not wish to commit changes into AEM repository, click **Close**, and then click **Close Without Saving** in the Unsaved Changes dialog.


## Partial selection of content across elements

Experience Manager Guides also allows you to select content across elements. After selecting the content, you can perform the following operations:

- Formatting and deletion: Make the selected content bold, italics, underline, or even delete the selected content. The content from the valid open tags is then merged and appears under a single element. For example, you can select the content within a paragraph and extend the selection to another paragraph. Then, if you make the selected content bold, all the bold content from the open tags is merged and appears under a single paragraph element.

Similarly, if you delete the selected content, the remaining content after the deletion in the open tags is merged. 

- Surround the content with a valid element: Perform the following steps to wrap the content with a valid element:

    - Select the content within an element.
    - Select the ![add](images/Add_icon.svg) icon from the secondary toolbar on the top to view the **Surround with Element** dialog box. The dialog box lists the valid elements for the selected content.
        >[!NOTE]
        >
        > You can also view the Surround with element dialog box by selecting the context menu of the selected content.

    - Select an element from the dialog box. The selected content is wrapped under that element. For example, if you select the content in a paragraph and then choose the `<note>` element from the **Surround with element** dialog box, the selected content appears under a note.  
    ![surround element dialog box](./images/surround-element.png) {width="300" align="left"}  

## Refresh browser while editing the files

Experience Manager Guides provides the support to refresh the browser while you edit your content in the Web Editor. This feature helps you continue editing content in case you encounter an application error while working. If you hit the browser refresh while one or more files with unsaved changes are opened for editing, you are warned that the unsaved changes may be lost. You are given an option to cancel the refresh operation and save your files to preserve your changes.

Even on refreshing the browser, the views of the left and the right panel are retained in the Web Editor. Experience Manager Guides restores the last saved state of the files opened in the Web Editor when you refresh the browser. For example, the files opened in the Repository panel are opened again. The map panel is retained along with the previously opened map.

The active topic or DITA map is reopened in the content editing area.

The right panel is also reopened and displays the same view as before the refresh.

## Working copy indicator

AEM Guides provides the working copy indicator which shows whether the current \(working copy\) of file is in sync with the saved version or not. If you have made any changes to your current copy and have not saved your file, a \* mark appears along with the title on the topic's file tab. This indicator acts as a reminder to save your changes and disappears when you save your file.

![working copy indicator](images/working-copy-text-update-indicator.png){width="550" align="left"}

AEM Guides also indicates if the last saved \(working\) copy of the file is in sync with the saved version or not. If you have some unsaved changes between the working copy and the last saved version, a \* mark appears along with the version information shown in the right top corner of the topic's file tab. This indicator acts as a reminder to save and create a version from your current \(working\) copy of the file.

![Version update indicator](images/version-update-indicator.png){width="550" align="left"}


## Open locked files in Author and Source modes

When a DITA or Markdown file is locked or checked out by another user, editing or modifying the content is not possible. However, you can still view the file in a read-only format in both the **Author** and **Source** modes, in addition to the **Preview** mode.

In the read-only mode, you have the ability to view the content, tags, and attributes within the **Author** or **Source** modes. You can also modify the file properties.

The toolbar displays the following icons for read-only access:

- Toggle Tags view
- Version History
- Version Label

Experience Manager Guides also displays a **Read only access** indicator near the version number.
 
![view read only file in author mode](images/locked-file-editor.png)

You can access the **Layout** view for read-only DITA maps. This view lets you see the DITA map and its properties but prevents edits.

>[!NOTE]
>
> Your folder-level administrative users must update *ui_config.json* so that you can harmoniously access the read-only files in the  Author, Source, and Layout modes.

## Locate an open file in the Repository View

While you open a file in the Web Editor, Experience Manager Guides provides the feature to locate the file in the Repository View. For example, it locates the current topic while you are editing it. 
   
You can turn off the feature to locate the file with the **Always locate files in repository** option from the **Appearance** tab of the **User preferences**. 


**Parent topic:**[Work with the Web Editor](web-editor.md)
