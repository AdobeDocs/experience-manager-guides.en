---
title: Map Editor features
description: Know the features of the Map Editor in Adobe Experience Manager Guides. Edit topics through a DITA map and use layout view, author view, and preview mode.
exl-id: e58e3705-2c3b-48cc-b2c8-2596e9751c85
feature: Authoring, Map Editor
role: User
---
# Map Editor features {#id1942D0S0IHS}

The toolbar in the Map Editor is similar to the topic Editor. The basic operations like toggling the left panel, saving map, creating a new version of map, undo/redo last operation, and delete the selected elements are common in both editors. For detail about how these operations work, view [Toolbar in the Editor](web-editor-toolbar.md#) section.

The options that you view in the editor toolbar are based on the Map Editor view. There are four views that are available in the Map Editor:

- [Layout](#layout-view)
- [Author](#author-view)
- [Source](#source-view)
- [Preview](#preview)
    
The following sections cover the toolbar options available in the different views of the Map Editor:

## Layout view

When you open a map for editing it opens the Layout view of the Map Editor. The Layout view displays the map hierarchy in a tree view and allows you to organize the topics in a map.

>[!NOTE]
>
> The Layout view only displays the references present in a map. If any references are broken, then a small cross symbol is displayed on the left of the reference

The following options are available on the toolbar in the Layout view:

**Topic reference** - ![](images/topic-reference.svg)

Displays the topic search dialog. Navigate to the topic/map file that you want to insert and choose **Select** to add it to the map. 

![](images/insert-topic-reference-dialog.png){align="left"}


**Topic group** – ![](images/topic-group.svg)

Insert the `topicgroup` element. For more information about grouping topics, view the [topicgroup](https://docs.oasis-open.org/dita/v1.0/langspec/topicgroup.html) documentation in OASIS DITA Language Specification.

**Key definition** – ![](images/key-definition.svg)

Displays the Insert Keydef dialog. Use this dialog to define any key definition that you want to use in the map.

![](images/insert-key-definition-dialog.png){width="300" align="left"}

**Insert Before/Insert After** – ![](images/insert_element_before_icon.svg) / ![](images/insert_element_after_icon.svg)

Displays the Insert Element dialog. Select the element that you want to insert in the map. Depending on the operation, the new element is inserted before or after the current element in the map.

**Insert Front matter** - ![](images/frontmatter.svg)

This icon is displayed when you open a bookmap for editing. You can insert components in the beginning of the book like a Table of contents, an Index, and a List of Tables.

**Insert Back matter** - ![](images/backmatter.svg)

This icon is displayed when you open a bookmap for editing. You can insert components for at the end of the book like an Index, a Glossary, and a List of Figures.

**Move the selected item left/right** - ![](images/move-left.svg) / ![](images/move-right.svg)

Select the left arrow to move the topic towards the left side in the hierarchy. This essentially promotes the respective topic one level up in the hierarchy. For example, selecting the left arrow while a child topic is selected, make it the sibling of the topic above it. Similarly, if you select the right arrow, the topic is pushed towards the right side making it the child of the topic above it.

**Move the selected item up/down** ![](images/move-up.svg) - / ![](images/move-down.svg)

Select the up or down arrow icons' to move the topic up or down in the hierarchy.

>[!NOTE]
>
> You can also drag-and-drop the references to move them in a map.

**Lock/Unlock**  

Gets a lock on the map file and release the lock. If you have unsaved changes in your map file, then at the time of releasing the lock, you are prompted to save the map file. The changes are saved in the current version of the map file.

**Merge** - ![](images/merge.svg)

For more details about merging content from a different version of the same or a different file, view [Merge](web-editor-features.md#menu-dropdown) in the Editor.

**Version history** - ![](images/version-history-web-editor-ico.svg)

Check the available versions and labels on your active topic, and revert to any version from the editor itself.

**Version label** - ![](images/version-label.svg)

Displays the version label management dialog. Select a version from the dropdown list. Choose the label you want to apply to the selected version and select **Add label** to add it.

**Show filename**

Shows the filename of the titles of the topics.

>[!NOTE]
>
> When you hover your pointer over a topic's title, you are shown the file path.

**Show line numbers**

Shows or hides the line number for each topic. The line numbers are shown depending on the level in the hierarchy.

**Show checkbox**

Shows or hides a checkbox for each topic. You can use the checkbox to select the topic\(s\) and perform various tasks using the Options menu. 

**Options menu in the layout view**

In addition to organizing topics in the map file, you can also perform the following actions using the Options menu that appears on hovering over a file or right-clicking within the editor in the layout view:

![](images/map-editor-options-menu.png){width="650" align="left"}

-   **Add**: You can choose to add a new topic or an empty reference from the Map Editor:
    -   **Empty reference**: This option allows you to add an empty reference in your DITA map. You can double-click the inserted empty reference later and add the Topic details. 
    -   **New topic**: When you choose to create a new topic from the menu, you get the **New topic** dialog box. In the **New topic** dialog box, provide the required details and select **Create**. 
-   **Move**: You can choose to move a topic up/down/right/left in the hierarchy. You can also drag-and-drop a topic or a map from the repository panel to the map opened in the Map Editor.
-   **Undo**: Undo the last operation in the Layout view.
-   **Redo**: Redo the last operation in the Layout view.
-   **Copy**: Copy the selected reference from the map file.

    >[!NOTE]
    >
    > You can show and then select the checkboxes to copy multiple references.

-   **Paste**: Paste the copied references at the current location in the hierarchy.
-   **Delete**: Delete the selected references from the map file.

    >[!NOTE]
    >
    > You can show and then select the checkboxes to delete multiple references.

**View topics based on conditional filters**

If you have applied any conditions on a topic, a filter icon is displayed on the right of the topic. When you hover your pointer over a filter icon, you are shown the applied condition and its attribute value.

## Author view

The **Author** view allows you to edit your DITA map in the Editor. This shows the WYSIWYG view of the Map Editor and some of the icons displayed in Author view are same as the Layout view. 

![](images/map-editor-author-view.png){align="left"}

In addition, you can view the following icons and perform the related tasks from the Author view:

**Insert before/Insert after** - ![](images/insert_element_before_icon.svg) / ![](images/insert_element_after_icon.svg)

Displays the **Insert element before or **Insert element after dialog box. Select the element that you want to insert in the map. Depending on the operation, the new element is inserted before or after the current element in the map.

**Element** - ![](images/Add_icon.svg)

Displays the **Insert element** dialog box. Select the element that you want to insert. You can use the keyboard to scroll through the list of elements and press Enter to insert the required element. Alternatively, you can select the element to insert it in the map.




<!-----------------------------------------------------------

**Relationship table** - ![](images/relationship_table_icon.svg)

Inserts a relationship table in the map.

Perform the following steps to work with relationship tables in the Basic Map Editor:

1.  In the Assets UI, navigate to the DITA map in which you want to create the relationship table.

1.  Select the DITA map to open it in DITA map console.

1.  Select the **Topics** tab to view a list of topics available in the DITA map.

    >[!TIP]
    >
    > The Topics tab gives you an option to download the map file with its dependents. For more details, view [Export a DITA map file](authoring-download-assets.md#id218UBA00IXA).

1.  In the main toolbar, select **Edit**.

    The map file is opened in the Advanced Map Editor.

1.  Select **Reltable** from the toolbar.

    ![](images/reltable.png){width="650" align="left"}

1.  Drag-and-drop topics from the topic list to the Reltable editor.

    >[!NOTE]
    >
    > You can add topics from any folder in the References rail.

    ![](images/create-reltable.png){width="550" align="left"}

1.  To add a header to your relationship table, click **Add Relheader**.

1.  To add a column to your relationship table, click **Add a Column**.

    ![](images/complete-reltable.png){width="550" align="left"}

1.  Click **Save**.


You can also perform the following actions from the relationship table editor:

**Delete rows or columns**

If you want to delete a column from your table, select the checkbox in the column header and click Delete. If you want to remove a row from table, select the checkbox in the first column of the respective row and click Delete.

**Delete a topic**

If you want to delete a topic from your table, click the cross icon next to the topic.

**Delete the relationship table**

If you want to delete the relationship table, click anywhere outside the relationship table and click Delete. For details, view [Work with relationship tables in the Map Editor](map-editor-basic-map-editor.md).
----->

**Reusable content** - ![](images/reusable-content.svg)

Displays the **Reuse content** dialog box. Use this dialog to insert the content that you want to reuse in your map.

**Refresh navigation title attribute** - ![](images/refresh.svg)

Allows you to keep the `@navtitle` attribute and the `title` element of a referenced file in sync. You can add different types of files to a map, such as topics, tasks, references, or submaps. Most of these support the `@navtitle` attribute, which controls how the file name appears in the map or table of contents. If a file contains the `@navtitle` attribute, then the `@navtitle` attribute for the same file in map is updated. In case the `@navtitle` attribute is not present, then the `@navtitle` attribute is added to that reference file and its `title` is also updated to display the `@navtitle`.

>[!NOTE]
>
> Your administrator can choose to show or hide this button in the Map Editor toolbar using a configuration property. They can also enable automatic addition of the `@navtitle` attribute when files are added to a map. For more details, view [Include @navtitle attribute by default](../cs-install-guide/auto-add-navtitle.md)* in Install and configure Adobe Experience Manager Guides as a Cloud Service.

**Tags** 

Shows or hides the XML tags. The tags serve as visual cues indicating an element's boundary. In this mode, if you want to insert a topic/map reference, then drag-and-drop the desired file before or after the tag. The horizontal bar is not shown in the Tags View mode.

**Track changes** - ![](images/track-changes.svg)

You can keep a track of all updates made in the map file by enabling the Track Changes mode. After enabling the track changes, all insertions and deletions are captured in the document. For more details, view [Track changes](web-editor-features.md#track-changes) in the Editor.

**Create review task** - ![](images/create-review-task.svg)

You can create a review task of the current topic or map file directly from the Editor. Open the file for which you want to create the review task and select **Create review task** to initiate the review creation process. Follow the instructions given in the [Introduction to review](review.md#) for more details.

## Source view

This view allows you to edit content in its raw format, providing full control over the structure and formatting.

![](images/map-editor-source-view.png){align="left"}


In this view, the toolbar provides basic content editing and insertion options available under the **Menu** dropdown including Cut, Copy, Undo, Redo, Delete, Find and replace, Version label, Merge, Save as new version, Lock and Unlock.

## Preview

The Preview mode renders the content as it will appear in the final output, enabling you to review the layout and formatting before publishing it. 

In addition to be able to view the position of each topic file within a map, it is desirable to view the map content in one consecutive flow. The Preview map feature allows you to view the entire content of the map file in a single click. You don't have to generate an output of the map file to view how the entire map will look like once published. You can simply access the map's preview and all topics and sub-maps are rendered in the form of a book.

![](images/map-editor-preview.png){align="left"}

>[!NOTE]
>
> No content editing or insertion options are available in the toolbar in the Preview mode. You can not edit the content in this view. However, you can use the **Save as new version** and **Lock** or **Unlock** features. 

You can perform the following additional tasks in the preview mode:

-   Right-click on a topic, and select **Edit** to open the topic for editing in a new tab.

    >[!NOTE]
    >
    > If you don't have editing rights, then the topic will open in read-only mode.

-   Jump to the desired topic by selecting the topic title in the map tree \(in left panel\).

-   The current topic in map preview is also highlighted in the map tree.

**Other ways to preview a map file**

You can access a map's preview from:

-   **Assets UI**: In the Assets UI, navigate to the map location, select the map file, and choose **Preview Map** in the Toolbar. The map's preview is shown in a new tab. You can view the content of all topics in the preview mode. In this view, you cannot edit any topic.

    >[!NOTE]
    >
    > If the *Preview Map* option is not visible in the main toolbar, it might have moved under the **More** toolbar menu.

-   **Map Editor**: In the Map Editor, select **Preview** from the options menu to view the preview of the current map.

    ![](images/map-preview-icon.png){width="650" align="left"}

    The preview of the map is displayed in a pop-up box. 

    ![](images/map-editor-preview-pop-up.png){width="500" align="left"}

**Map properties**

Displays the Map Properties dialog wherein you can set the attributes and metadata information for the map.


## Edit topics through DITA map {#id17ACJ0F0FHS}

Editing an individual topic doesn't give the complete context to the author. An author would have no information about where a topic is placed in a DITA map. Without this contextual information, it becomes a bit difficult for authors to create content.

Experience Manager Guides allows authors to open a DITA map in the Editor and view the placement of topics within the map. This helps authors to know exactly where the topic is placed within the map and create more relevant content. Also, if there are multiple authors working on a project, they can know what all topics are available in the map and reuse content, wherever required.

To edit topics through a DITA map, perform the following steps:

1. In the Repository panel, navigate to and open the DITA map file that you to want to edit. 

    The map file opens in the Map view. 

>[!NOTE]
>
> You can also use the Assets UI to open a DITA map file. Navigate to the DITA map file that contains the topics you want to edit and select **Edit Topics** in the main toolbar to launch the Editor.

1. Select any topic link to open it in the Editor for editing.

    You can open multiple topics in the editor and each topic is opened in a new tab in the editor. Even if your DITA map contains sub-maps, topics from the sub-maps are also opened in a new tab for editing. If you want to view the topics under a sub-map, you can select and expand the sub-map.

    ![](images/web-editor-multiple-topics.png){align="left"}

    If you select a map file, the map is opened in a new tab of the Editor.

1.  Once you have finished editing the topics, you can do the following:

    -   You can save them individually. If you close without saving your topics, you will view a dialog box prompting you to save the unsaved topics:

        ![](images/save-multiple-topics-new.png){width="300" align="left"}

        You can choose to save all selected topics or deselect the topics that you do not want to save.

    -   You can unlock the topic using the **Save as new version** option. When you save a version of the topic, a new version is created and the lock is also released.

        It's recommended to save your changes before unlocking the files.  When you save the changes, the XML file is validated.

    - You can also view the progress of the topics from the **Save as new version** dialog box. A success message is shown when the files are unlocked. 

    -   If your administrator has enabled the option of unlocking files on close, then you will be shown a prompt to save files whenever the locked files are closed. With this option enabled, when you close the editor with changed files, you are shown the list of locked files that need to be saved. The locked files are shown with a lock icon:

        ![](images/save-on-close-new.png){width="350" align="left"}

## Right panel in the Map Editor 

The right panel displays the Content Properties and the Map Properties in the Layout view of the Map Editor.

**Content properties**

The Content properties panel contains information about the type of currently selected topic in the map, its link URL, and its attributes. For more details, view [Content Properties](web-editor-features.md#right-panel) in the Editor.

-   **Other Attributes** If your administrator has created a profile for attributes, then you'll get those attributes along with their configured values. Using the content properties panel, you can choose those attributes and assign them to relevant content in your topic. You can also assign attributes configured by your administrator under **Display attributes**. The attributes defined for an element are displayed in the Layout and the Outline view. This helps you to have a quick look at all the topics in a map for which a particular attribute is defined. For example, all topics which have the `audience` attribute are defined as `US`.

    ![layout view](images/layout-inline-attributes.png){width="650" align="left"}

   
    For more details, view  [Display attributes](../cs-install-guide/workspace-settings.md#display-attributes).

-   **Metadata** Using the metadata , you can set the metadata information. You can define the Nav Title, Link Text, Short Description, and Keywords.

For more information about the standard topic attributes and metadata, view the [topicref](https://docs.oasis-open.org/dita/v1.2/os/spec/langref/topicref.html) documentation in OASIS DITA Language Specification.
 



**Parent topic:** [Introduction to the Map Editor](map-editor.md)
