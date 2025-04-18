---
title: Know the Editor features
description: Discover features of the Editor in Adobe Experience Manager Guides. Know the editor's interface, including the Header bar, tab bar, toolbar, left panel, content editing area, and right panel.
exl-id: 340cf72e-e44d-4df2-8312-50d00ac651b7
feature: Authoring, Features of Web Editor
role: User
hidefromtoc: yes
hide: yes
---
# Know the Editor features {#id176NC500V5Z}

This section walks you through the various features that are available in the Editor. We can divide the Editor into the following sections or areas:

- [Header bar](#header-bar)
- [Tab bar](#tab-bar)
- [Toolbar](#toolbar)
- [Left panel](#left-panel)
- [Content editing area](#content-editing-area)
- [Right panel](#right-panel)

The following subsection cover in details the various sections of the Editor.

## Header bar

The header bar is the top bar of the Editor that displays the Adobe Experience Manager logo (or a Unified Shell if you are using the Unified Shell as your Experience Manager Guides UI). When you select the logo, it directs you to the Experience Manager Navigation page.

![](./images/aem-home-header.png)

Use the **Expand** icon in the toolbar to hide the header bar and maximize the content area. To restore the standard view, select **Exit the expanded view**.


## Tab bar

The Tab bar is at the top of the Editor's interface and it provides access to the following features:

![](./images/tab-bar.png)

**Tabs**

Displays the currently opened topics in the Editor as file tabs. You can have multiple topics opened at the same time, which are displayed in their respective tabs in the tab bar. By default, you can view the file titles in the tabs. As you hover over a file, you can view the file title and the file path as a tooltip.

>[!NOTE]
>
> As an administrator, you can also choose to view the list of files by filenames in the tabs. Select the **Filename** option of the **Editor files display configuration** section in [User preferences](./intro-home-page.md#user-preferences).

Selecting the file tab opens a context menu featuring Save as new version, Copy, Locate in, Add to, Properties, Split, Download as PDF, and Close options. 

**Save all** 

Saves the changes you have made in all opened topics. If you have multiple topics opened in the Editor, selecting **Save all** or using the **Ctrl**+**S** shortcut keys saves all documents in one click. You do not have to individually save each document.

>[!NOTE]
>
> The **Save all** operation does not create a new version of your topics. To create a new version, use the **Save as new version** option.

**AI Assistant**

A powerful, AI-driven tool designed to enhance your productivity through smart help and authoring features. It brings together two robust AI features — **Authoring** and **Help** — into the Experience Manager Guides interface, enabling you to author content and access information from Experience Manager Guides documentation faster and more efficiently. 

>[!NOTE]
>
>The AI Assistant feature is currently available for Adobe Experience Manager Guides as a Cloud Service.

**Expand view**: Allows you to expand the page view using the **Expand** icon. In this view, the header bar containing the Adobe Experience Manager logo, is hidden. This maximizes the content space for editing. To return to the standard view, use the **Exit the expanded view** icon.

**More actions**: Allows you to navigate to the **Assets** and **Settings**. 

The **Assets** option takes you to a destination based on your setup:

- **Cloud Services**: If you are using Cloud Services, selecting the **Assets** option takes you to the AEM Navigation page.

- **On-premise Software**: If you are using Adobe Experience Manager Guides (4.2.1 and later), selecting the **Assets** option takes you to your current file path in the Assets UI.


The **Settings** option is available only for administrators and folder profile administrators, and allows configuring the following settings:

>[!NOTE]
>
> If you are updating any default settings, you should reopen documents for the changes to come into effect.

- **General**: The General settings allow you to configure the dictionary to use with the Editor. This tab contains four sections: **Spell check**, **Condition**, **Authoring**, and **Citations** .

    ![](images/editor-setting-general.png){width="650" align="left"}

    - **Spell check**: There are two options — **AEM spell check** and **Browser spell check**. By default, the editor uses the Browser spell check feature, wherein the spell-check is performed using the browser's in-built dictionary. You can switch to AEM spell check to use Adobe Experience Manager's dictionary, which can also be customized to add your custom word list. For more information about customizing AEM dictionary, view [Customize AEM's default dictionary](../cs-install-guide/customize-aem-custom-dictionary.md) section in the Install and configure Adobe Experience Manager Guides as a Cloud Service.        

    - **Condition**

      - **Highlight conditional text in the Author view**: Select this to highlight the conditional text in the author view. The conditional content is highlighted using the color defined for the condition.

      - **Validate with condition attributes**: Select this to allow the validation of the values defined for the attributes. This prevents you from adding any incorrect value.

      - **Show key with the title in the Subject Scheme panel**: Select this to show the keys along with titles in the subject scheme. If you do not select this option only the titles are shown. For example, here the keys 'os', 'audience', and 'other' are also shown along with titles.

        ![](images/subject-scheme-title.png){width="550" align="left"}

      - **Show subject scheme in the Conditions panel**: Select this to view a subject scheme in the conditions panel. If you deselect this, the defined conditions are shown in the conditions panel.

    - **Authoring**

      - **Enable Replace All**: Select this to view the **Replace All** icon in the **Find and replace** panel.        

    - **Citations**
       Change the style of citations. Choose the citation style from the drop-down you want to use in your project. For more details, view [Change citation styles](./web-editor-apply-citations.md#change-citation-style).

    - **AI Assistant**
       Select this to enable the [AI Assistant](./ai-assistant.md) feature in the Experience Manager Guides. Unselect to disable the feature. 

**Panels**: This setting controls the panels that are shown in the left and right panels of the Editor and Map console. You can toggle the button to show or hide the desired panel. 

![](images/editor-setting-panel.png){width="650" align="left"}

You can also define the order in which the features present in panels are displayed. To change the default order of the available features in the panels, select the dotted bars to drag and drop the feature tabs at the desired location. A feature can also be moved from the **More** section to the main section of a panel, and vice versa as per the requirement. Once re-ordered, the features appear in the same sequence in the respective right and left panel. 

![](images/panels-screen.png){width="650" align="left"}


A maximum of eight panels can be displayed at a time. Any changes made to the panel settings are applied immediately. 


>[!NOTE]
>
> If a custom panel has been configured, then it also appears in the list of panels. You can toggle the switch to show or hide the custom panel. 

- **Elements list**: As an administrator, you can control the list of elements that an author can insert into a file and also define the display name for the element. The Elements list setting allows you to specify the element's name as per DITA specifications and a label that you want to use instead of the DITA defined element name:

  ![](images/editor-setting-element-list.png){width="650" align="left"}

In the above screenshot, the `p` element has been given a label of Paragraph, and `codeblock` is given a label of Code Block along with some other elements.. If you select the **Use only above elements** option, then only the valid elements \(at current insertion point\) from this list will be shown in the **Insert element** dialog box.

In the following screenshot, only 3 out of 4 configured elements from the previous screenshot are shown in the current context:

![](images/editor-setting-insert-element-list.PNG){width="300" align="left"}

- **Attributes list**: Similar to the elements list, you can control the list of attributes and their display names to be displayed in the attributes list of an element. In the following screenshot, only 3 attributes have been configured to be shown in an element's attribute list:

  ![](images/editor-setting-attributes-list.png){width="650" align="left"}

  With this setting, when you try to add an attribute to an element, you only view the list of attributes configured in the list.

  ![](images/editor-setting-add-attributes-list.png){width="300" align="left"}

- **Colors**: Displays a list of pre-configured background colors for **Conditions**. Users can select a background color when applying a condition to a topic. As an administrator, you can also create and add custom background colors to the list. To add a new color, enter the desired name in the **Color Name** field, choose a custom color, and select the **+** icon. The custom color will appear at the end of the color list.

- **Publish profiles**: This contains the Profiles that can be used to publish the **Knowledge Base** output. You can create a new profile for a target knowledge base. For example, Salesforce or ServiceNow.

  - **Create a Salesforce profile**

    **Prerequisites**
        
    - Create a connected app for Salesforce. For more details, refer to [Enable OAuth Settings for API Integration](https://help.salesforce.com/s/articleView?id=sf.connected_app_create_api_integration.htm&type=5).
        
    - While configuring the connected app ensure the following:

       - Specify the callback. 
            
         `URL: http://<server name>:<port>/bin/dxml/thirdparty/callback/salesforce`

       - Select the following OAuth Scopes:
          - Full access (full)
          - Select Manage user data via APIs (api)

    Once the app is configured, Salesforce provides a **Consumer Key** and **Consumer Secret**. These can be used to create the Salesforce profile. 
     

  - To create a Salesforce profile, select the **Salesforce** Knowledge Base from the **Server type** dropdown. Enter a profile Name. In the **Site URL**, enter the consumer site you would use to publish the output and then add the **Consumer Key** and **Consumer Secret** provided by the Salesforce consumer site. Then, **Validate** and **Save** the newly created profile.

    ![salesforce publish profile in editor settings](./images/salesforce-publish-profile.png){width="550" align="left"}

    >[!NOTE]
    >
    >To configure a proxy for Salesforce in Experience Manager Guides, use Apache HTTP Components Proxy Configuration in AEM. Learn how to [configure proxy for the AEM Link Checker](https://helpx.adobe.com/experience-manager/kb/How-to-configure-proxy-for-the-AEM-Link-Checker-AEM.html).


  - **Create a ServiceNow profile**

    **Prerequisites**

    Configure the ServiceNow server to upload the assets.
    - Connect to the **ServiceNow** server.
    - Navigate to **System Properties** > **Security**. 
    - Uncheck the following option:

      **This property must be set to activate MIME type checking for uploads (All versions Eureka and up). Enables (true) or disbles (false) mime type validation for the file attachments. File extensions configured via glide.attachment.extensions will be checked for MIME type during upload.**  
    
    - Select **Save**.
    
     Once you have configured the app, create the **ServiceNow** profile.

  - To create a profile, select the ServiceNow Knowledge Base from the **Server type** dropdown. Enter a profile **Name**. In the **ServiceNow URL**, enter the consumer site you would use for publishing the output and then add the **Username** and **Password** provided by the ServiceNow consumer site. Then, **Validate** and **Save** the newly created profile.
 
    ![ServiceNow publish profile](./images/service-now-publish-profile.png){width="550" align="left"}

   After you validate, you can select the Publish Profile in the output presets of a DITA Map and use it to generate the output to the  **Salesforce** or **ServiceNow** server that you have chosen. 

   Learn more about the [Knowledge Base](../user-guide/generate-output-knowledge-base.md) output preset. 


- **Validation**: This tab contains options to configure the Schematron validations in the Editor. You can enable the following features:

    - **Run validation check before saving the file**: Select this to run Schematron validations using the selected Schematron file(s) before any save operation. You can add a Schematron file by selecting the + icon. The selected Schematron file(s) are listed.

       >[!NOTE]
       >
       >The selected Schematron file(s) will persist for the selected folder profile.

       ![Validation in editor settings](./images/editor-setting-validation.png){width="550" align="left"}

       This prevents the users from saving any file which breaks a rule defined in the selected Schematron file(s). If this is not selected the file will not be validated before saving the changes.

    - **Allow all users to add schematron files in validation panel**: Select this to allow the users to add any Schematron file in the Validation panel of the Editor. This allows the users to add Schematron files and then validate the topics against the Schematron file. If this is not selected, the option to add schematron file **Add Schematron File** button is not available to the users in the **Validation panel** of the Editor.


- **Display attributes**: Like the Attributes list, you can control the list of  attributes to be displayed in the attributes list of an element. By default, four **Display attributes** — audience, platform, product, and props have been configured to be shown in an element's attribute list. You can also add a display attribute using the **Add** icon on the top. You can also delete any of the display attributes using the **Delete** icon.

    The attributes defined for an element are displayed in the Layout and the Outline view.

    ![](images/editor-settings-display-attributes.png){width="550" align="left"}

- **Translation**: This tab contains the options to create language groups, propagate the source labels to the target version, and clean up the translation project. 

     ![](images/editor-setting-translation.png){width="550" align="left"}

    - **Language Groups**: As an administrator, you can create a group of languages and use them as a set to translate the content. 

      Perform the following steps to create a new language group: 
    
      1. Select **Add**. 
      1. Enter the language group name. Each language should have a unique name. You can view an error if the name field is empty or if the name isn't unique. 
      1. Select the languages from the dropdown. You can select multiple languages.
        
         Type the first few characters of the language, or the language code to filter the desired languages. For example, type 'en' to filter all the languages that contain 'en' at the beginning of their name or code.
        
      1. Select the Done icon to add the selected languages to the group. The languages are displayed. When you add three or more languages, the **Show more** option is displayed. You can select **Show more** to view all the languages present in the group.

         >[!TIP]
         >
         >Toggle **Show more** to **Show less** and view only a few languages.

      1. Hover over the languages in a group to edit ![edit icon](images/edit_pencil_icon.svg) or delete ![delete](images/Delete_icon.svg) the language groups.
      1. Save the **Settings**.

         >[!NOTE]
         >
         >As a user, you can view the language groups configured to your folder profile.

    - **Propagate source version labels to the target version**: Select this option to pass the label of the source file version to the translated file. By default, this is disabled.
    - **Translation project cleanup after completion**: Select this option to configure the translation projects to be disabled or deleted automatically after the translation. By default, **None** is selected, so that the project exists after translation.
    
       You can disable the translation projects if you want to use them later. Deleting a project permanently deletes all files and folders present in the project.
       

- **Metadata**: You can control the version metadata of the topic and their values to be displayed in the **Version history** dialog box.  In the metadata path, specify the location of the nodes from which you want to pick the metadata. You can also define a custom name for the metadata as the label. The default properties are Title, Document State, and Tags.

    The metadata can be picked from any property under the `/jcr:content` node of the asset, so you can add the path of the property as the Metadata path.
    

    An error is displayed if the metadata path is blank. If you leave the label blank, the last element is picked as the label.     


    ![metadata tab in the editor settings](images/editor-setting-metadata.png){width="550" align="left"}

    *Configure the metadata for the **Version History** dialog box.*
 
    
    
    You can also define the order in which these metadata tags are displayed. To change the default order of these tags, select the dotted bars to drag and drop the tags at the desired location.
    The metadata labels appear in the same sequence in the **Version history** dialog box of the Editor. 

## Toolbar
  
The toolbar appears when you open a topic or map for editing in the Editor. Features available in the toolbar are as follows:

- [Menu dropdown](#menu-dropdown)
- [Content insertion options](#content-insertion-options)
- [Version information and  Save as new version button](#save-as-new-version)
- [Lock/unlock](#lockunlock)

>[!NOTE]
>
> The features listed above are applicable only for topic files. When working with a map file, different options are displayed in the toolbar based on the current Map editor view. Learn about the Map editor toolbar options in the [Map editor features](./map-editor-advanced-map-editor.md) document.

### Menu dropdown 

The Menu dropdown provides access to the editing actions, Find and replace, Version history, Version label, Merge, Create review task, Track changes, and Tags feature. 

The detailed explanation of these features is as follows:

**Editing actions**

When editing a topic in the Editor, access the various editing actions such as **Cut** or ***Ctrl***+***X*** , **Copy** or ***Ctrl***+***C*** , **Undo** or ***Ctrl***+***Z*** , **Redo** or ***Ctrl***+***Y*** and **Delete** present in the Menu dropdown. 
     

**Find and replace**

The **Find and replace** feature is available in Author and Source view modes. When enabled, the Find and Replace text bar appears at the bottom of the topic editing area. You can use the shortcut keys **CTRL**+**F** to invoke the Find and replace bar.

![](images/find-replace-bar.png){align="left"}

Using the settings icon \(![](images/settings-find-replace-icon.svg)\), you can toggle the **Ignore case** and **Whole word only** search options. To perform the case-insensitive search, turn on (or select) the **Ignore case** option. Else, if you want to perform the case-sensitive search, turn off (or deselect) the **Ignore case** option. You can also choose to search a whole word.

The search is instantaneous, which means that as you type the search phrase or word in the **Find** field, the term is immediately searched and selected in the topic. Similarly, for replacing a text in your topic, enter the search term and its replacement in the respective fields and select the **Replace** or **Replace All** button.

In the Source view, the **Find and replace** feature is extremely useful for searching for a specific element or attribute. For example, if you want to replace the value of the `@product` attribute, it can be easily done from the Source view. The Author view does not allow you to search on the basis of an attribute or element. However, you must use caution while using the **Replace All** feature, as it might overwrite the XML code.

**Version history**

The **Version history** feature in the Editor allows you to check the available versions of your DITA files, compare them, and revert to any version from the Editor itself. You can compare the content and metadata of the current version (which can also be a working copy) with any previous version of the same file. You can also view the labels and comments for the compared versions.

>[!NOTE]
>
> The Version history options only appear if there are changes made to the first version of the topic or map. 

To access the version history and revert to a specific version of your topic, perform the following steps:

1. Open a topic in the Editor.
1. Select **Version history** from the **Menu** dropdown.

   The **Version History** dialog box appears.

   ![Version history dialog box](images/version-history-dialog-web-editor.png){width="550" align="left"}
    
    *Preview the changes in the different versions of a topic.*

1. Choose a version of the topic that you want to compare or revert to in the **Compare with** dropdown list.

    >[!NOTE]
    >
    > If a version has labels applied to it, they are also shown \(in brackets\) along with the version number.
    
1. Enable the **View labels and comments** option to view the labels and comments applied to the current and the compared versions.
1. You can also view the following information in the **Version history** dialog box:
    
    **Preview** tab: The newly added content is in green font, and the deleted content is in red font. 

    **Metadata** tab: The newly added metadata is in green font, and the deleted metadata is in red font.

    ![Metadata difference for versions ](images/metadata-version-diff.png){width="550" align="left"}
    
    *Compare the metadata of different versions in the Version history.*

    >[!NOTE]
    >
    > Your system administrator can change the metadata to be shown from the Metadata tab in the **Settings**. For details, refer to the **More actions** section of the [Tab bar](#tab-bar).

    You can also view the user and time details of the current and the compared version.
  
    Once you choose a version from the drop-down list, the **Revert to selected version** option is made available. The preview window displays the differences between the current version and the selected version of the topic.

1. Select **Revert to selected version** to revert your working copy with the selected version of the topic.

    The Revert Version dialog box appears.

    ![](images/version-history-revert-dialog-save-working-copy.png){width="550" align="left"}

1. \(*Optional*\) Provide a reason for reverting to an earlier version. You can also create a new version of the currently active working copy of your topic.

1. Select **Confirm.**

    Your working copy of the file is reverted to the selected version. If you choose to create a new version of the currently active working copy, then a new version of the file is also created with all working changes.

    When you revert to an earlier version, a visual cue is shown indicating that the version you are currently working on is not the latest version.

    ![](images/older-version-visual-cue.png){align="left"}

**Version labels**

Labels help you identify the stage in which a particular topic is in the DDLC (Document Development Life Cycle). For example, when you are working on a topic, you could set the label as "Approved". Once a topic is published and made available to customers, you can assign "Released" label to that topic.

Experience Manager Guides allows you to specify labels in a free-form text format or use a set of predefined labels. The custom label would allow any author in the system to specify a label as per their choice. This gives flexibility; however, it introduces inconsistent labels in the system. To overcome this issue, administrators can configure a set of predefined labels. For more information about configuring predefined labels, view *Configure and customize the XML Web Editor* in the Install and configure Adobe Experience Manager Guides as a Cloud Service.

These labels are shown in the form of a drop-down list to authors wherever they need to specify a label. This ensures that only predefined, consistent labels are used in the system.

There are different methods through which you can apply labels to your topics - [Version history](web-editor-use-label.md) panel in Assets UI, [Baselines](/help/product-guide/user-guide/generate-output-use-baseline-for-publishing.md) UI, and the Editor. The Version Label feature in the Editor gives authors a quick and easy way to assign labels to their topics.

To add labels to your topic from the Editor, perform the following steps:

1. Open a topic in the Editor.

1. Select **Version labels** from the Menu dropdown.

    The Version Label Management dialog box is displayed.

    ![](images/version-label-management-dialog.png){width="650" align="left"}

    The Version Label Management dialog box is split into two parts — the left panel has a list of versions available for the topic along with label drop-down list \(or a text box to enter a label\) and the right panel with a preview of the topic.

1. Select a version on which you want to apply labels.

    When you choose a different version of the topic from the version list, then the preview panel displays the changes in-between the current version and the selected version of the topic

    >[!NOTE]
    >
    > If a label is already applied on a version, it is displayed next to the version number in the drop-down list and below the Select Version list. You can remove an existing label by selecting the \(**x**\) icon next to the label.

1. In case your administrator has defined a list of labels, then you are shown a drop-down list of the labels from where you can choose the labels that you want to apply. You can select multiple labels from the drop-down list.

    Else, you are shown a text box, wherein you can enter the labels that you want to add to your topic.

    >[!NOTE]
    >
    > You cannot apply the same label on multiple versions of a topic. If you try to associate an existing label, then you are given an option to remove it from the existing version and apply it on the selected version of the topic.

1. Select **Add Label**.

1. In the Apply Label confirmation message, select the **Move label(If used on another version)** option to move labels from an existing version to the selected version. If you do not select this option and there are labels that are assigned to a different version of the topic, then they are not moved to the selected topic's version. Such labels are ignored in the label application process.

**Merge**

When you work in a multi-author environment, it becomes difficult to track what changes the other authors have made in a topic or map. The Merge feature gives you more control over not only viewing the changes, but also what changes are retained in the latest version of the document.

- **Merge topic files**

  To merge changes in a topic, perform the following steps:

    1. Open a topic in the Editor.

    1. Select **Merge**.

       The Merge dialog appears.

        ![](images/merge-changes-in-topic.png){width="550" align="left"}

    1. *\(Optional\)* You can also browse and select a new file from some other location in your repository.

    1. Select a version of the file with which you want to compare the current version of the file.

    1. From the Options, choose:

        - **Track changes from selected version**: This option shows all content updates in the form of tracked changes. You can then choose to accept or reject changes in the document one at a time or all in one go.

        - **Revert to selected version**: This option reverts the current version of the document to the selected version. This option does not give you any control on what content is accepted or rejected.

    1. Select **Done**.

    1. If you selected the **Track changes from selected version** option, then all changes from the selected version are shown in the Tracked changes feature of the right panel.

       You can choose to accept or reject all comments from the Tracked changes panel or accept or reject individual comment.


 - **Merge map files**

    To merge changes in a map file, perform the following steps:

    1. Open a map in the Editor.

    1. Select **Merge**.

       The Merge dialog box appears.

        ![](images/merge-changes-in-map.png){width="550" align="left"}

    1. *\(Optional\)* You can also browse and select a new file from some other location in your repository.

    1. Select a version of the file with which you want to compare the current version of the file.

    1. From the Options, choose:

        - **Track changes from selected version**: This option shows all content updates in the form of track changes. You can then choose to accept or reject changes in the document one at a time or all in one go.

        - **Revert to selected version**: This option reverts the current version of the document to the selected version. This option does not give you any control on what content is accepted or rejected.

    1. Select **Done**.

    1. If you selected the **Track changes from selected version** option, then all changes from the selected version are shown in the Tracked changes panel \(on the right\).

        You can choose to accept or reject all changes from the Tracked Changes panel or accept or reject individual change in the map file.


**Create review task** 

You can [create a review task](./review-send-topics-for-review.md) of the current topic or map file directly from the Editor. Open the file for which you want to create the review task and select **Create review task** from the Menu dropdown to initiate the review creation process.

**Track changes**

You can keep a track of all updates made on a document by enabling the Track changes mode. After enabling the track changes, all insertions and deletions are captured in the document. All deleted content is highlighted using Strikethrough and all insertions are highlighted in green color text. In addition, you also get the change bars at the edge of the topic page. Again, a red bar is shown for deleted content and a green bar is shown for added content. In case there is an addition and deletion on the same line, then both green and red bars are shown.

The following screenshot highlights the deleted and inserted content along with the change bars:

![](images/track-changes-content.png){width="650" align="left"}

A typical use case for tracking changes in a document can be for doing peer review. You can enable track changes and share your document for review, and the reviewer then makes changes with track changes ON. When you receive the document, you should then have a mechanism to view the suggested updates along with a convenient way to accept or reject changes.

Experience Manager Guides provides the Tracked changes feature that contains information about the updates made in the document. The Tracked changes feature provides information about what updates were made, who made them, and at what time. Using the Tracked changes feature, you can also easily accept or reject the suggested updates in the document.

To access the feature, select the **Track changes** icon in the right panel.

![](images/changes-panel_cs.png){width="300" align="left"}

Selecting a tracked change selects the changed content in the document. You can accept a change by selecting the Accept Change icon or reject it by selecting the Reject Change.

If you want to accept or reject all changes with a single click, select **Accept all changes** or **Reject all changes**.

>[!NOTE]
>
> The Preview mode allows you to view the document with or without the changed content's markups. For more details, view the [Preview](web-editor-views.md#preview-mode-id19AAGL00163) mode.

**Tags**

The **Tags** feature in the Editor is a toggle button that controls the visibility of DITA elements. When enabled, it displays structural tags within the content, allowing you to view and manage the underlying DITA elements more effectively. When disabled, the editor hides these tags, providing a cleaner and more focused authoring environment.

The following screenshot shows a document with the Tags view enabled:

![](images/tags-view.png){width="650" align="left"}

The following operations can be performed in a document with Tags:

- **Select an element**: Select the opening or closing tag of an element to select its content.

- **Expand or collapse tags**: Select the + or - sign in a tag to expand or collapse it.

- **Use the context menu**: The context menu provides options to cut, copy, or paste the selected element. You can also insert an element before or after the selected element. The other options allow you to Generate ID or open the Properties panel for the selected element.

- **Drag-and-drop elements**: Select an element's tag and easily drag-and-drop it on your document. If the drop location is a valid location where the element is allowed, the element is placed at the dropped location.


>[!NOTE]
>
> If a user enables the Tags view from the Editor, it remains enabled even across the sessions. This means that you don't have to enable the Tags view again to access it later. The default value for Tags view for a new user's session is determined by the `tagsView` property in the `ui\_config.json` file. For more details, view the [Configure default value for Tags View](../cs-install-guide/configure-default-value-tags-view.md) section in Install and configure Adobe Experience Manager Guides as a Cloud Service.

### Content insertion options

**Element** - ![](images/Add_icon.svg)

Inserts a valid element at the current or next valid location. You can also use the keyboard shortcut ***Alt***+***Enter*** to open the Element dialog box. For example, you are editing a paragraph, then in the **Element** dialog box, a list of elements appears that can be inserted in the paragraph. Select the element that you want to insert. You can use the keyboard to scroll through the list of elements and press ***Enter*** to insert the required element. 

You can view two types of valid elements: 

- **Valid elements at the current location**: The list displays the elements that you can insert at the current cursor location itself.  

- **Valid elements outside the current location**: The list displays the elements that you can insert after any of the parents for the current element within the element hierarchy.    

For example, if you are within the inline `<b>` element, you can insert elements like `<u>`, `<xref>`, `<i>` at the current location. In contrast, you can insert elements like `<table>` and `<topic>` outside the current location. 

You can also type a character or string in the search box and search for the elements that begin with it.
 
![insert element](images/insert-element.png){width="300" align="left"}

*Enter 't' to search for all valid elements that begin with 't'.*

If you are working inside a block element like a `note`, then use the Insert element icon to insert a new element after the `note` element. In the following screenshot a note element has been inserted inside the p \(paragraph\) element:

![Insert element in a block element](images/note-in-para-insert-element_cs.png){align="left"}

If you press Enter in the note element, a new paragraph is created within the note element itself. To insert a new element outside note, select the p element \(highlighted in screenshot\) in the elements breadcrumb and then select the Element icon or press ***Alt***+***Enter*** to open the Insert element dialog box. Then, select the desired element and press Enter to insert the selected element after the note element.

You can also add an element between two elements when a blinking block cursor appears. 


![](images/Block-cursor.png){width="300" align="left"}

For example, if you are working on a DITA topic, and the block cursor is blinking between the short description and the body, you can add `prolog` element and then add copyright, author, and other details.

Another way of entering a new element is by using the context menu. Right-click at any place in your document to invoke the context menu. From this menu choose **Insert Element** to display the **Insert element** dialog box and choose the element that you want to insert.

![](images/insert-element-before-after.png){width="300" align="left"}

**Paragraph** - ![](images/Paragraph_icon.svg)

Insert paragraph element at the current or next valid location.

**Bulleted list** - ![](images/BulletList_icon.svg)

Creates a bulleted list at the current or next valid location. If you are on a bulleted list and select this icon, the item is converted into a normal paragraph.

**Numbered list** - ![](images/TextNumbered_icon.svg)

Creates a numbered list at the current or next valid location. If you are on a numbered list and select this icon, the item is converted into a normal paragraph. 

>[!NOTE]
>
>You can also select the **Split list** option from the context menu of a list item to split the current list and begin a new list at the same level.

**Table** - ![](images/Table_icon.svg)

Inserts a table at the current or next valid location. Select the Table icon to open the Insert Simple Table dialog box. 

![](images/table-properties.png){width="550" align="left"}

>[!NOTE]
>
> You can also copy a table from MS Word or Excel and paste it into the Experience Manager Guides topic file. The copied table will be pasted as either `<simpletable>` or `<tgroup>` depending on the settings configured in the XML Editor Configuration. For more details, view [Configure the display of pasted tables](../cs-install-guide/conf-pasted-tables.md). 

You can specify the number of rows and columns required in the table. If you want to keep the first row as the table header, select the **Set first row as header** option. To add a title to your table, enter it in the Title field.

Once a table is inserted, you can modify the table using the context menu.

![](images/table-context-menu_cs.png){width="550" align="left"}



Using the table's context menu, you can:

- Insert cells, rows, or columns

- Merge cells in right and down directions

- Split cells horizontally or vertically

- Delete cells, rows, or columns

- Generate IDs


You can also define attributes on multiple cells, entire row, or column of a table. For example, to align table cell, drag and select the required cell. In the Content Properties panel (on the right), the property **Type** changes to **entry**.

1. In the **Attributes** section, select **+Add**. 
1. Select the `@valign` attribute from the **Attribute** dropdown list. 
1. From the value dropdown list, select the desired text alignment you want to apply on the selected table cells. 
1. Select **Add.**

![](images/align-table-cell_cs.png){align="left"}

**Image** - ![](images/Image_icon.svg)

Inserts an image at the current or next valid location. Select the Image icon to open the Insert Image dialog box and then search and select the image you want to insert.

>[!NOTE]
>
> You can also add an image by dragging and dropping it from your local system on to your article. In this case, the image file is added using the **Upload Assets** workflow.  For more details, view the **Upload Assets** workflow in the [Left panel](#left-panel) section. 


![](images/insert-image.png){width="650" align="left"}

You can add an image/Figure Title and Alternate Text for the image in the Insert Image dialog box.

>![NOTE]
>
> When you insert an image and specify an alternate text for the same, it is added within the `<alt>` element in accordance with the latest DITA standards. The use of the `@alt` attribute for alternate text is deprecated, but it remains supported in previous DITA versions.

Using the **Select File** option, you can search for the required image file by file name. You can also filter the search results by Path \(to search in\), Collections, File Type, and Tags. Once you have found the required image file, select the file and choose **Select** to insert the image in your document. You can insert various formats of image files, such as `.png`, `.svg`, `.gif`, `.jpg`, `.eps`, `.ai`, `.psd`, and more.

Once you have inserted an image, you can change the height, width, placement, and attributes from the Content properties panel. Select the image file and then make changes in the Content properties panel in the right panel.

![](images/image-properties.png){align="left"}

The Source field displays the UUID of the inserted image file. You can find the complete path of the inserted image file by hovering the mouse pointer over the Source field. The path is displayed in the tooltip.

You can resize an image by providing either Height or Width value for the image file. The aspect ratio of the image is maintained automatically. If you want, you can also choose not to maintain the aspect ratio of the image file by selecting the lock icon \(of Maintain Aspect Ratio\) and providing Height and Width values.

You can also specify the Placement setting for the image as Inline or Break. In case you choose to use the Break placement option, you can then choose where to align the image (Left, Center, or Right).

You can also add other properties for an image file by selecting the required properties in the **Attributes** field.

>[!NOTE]
>
>You can also define clickable areas \(image map\) in your image. For more details, view the **Insert/Edit Image Map** feature description in the [Left panel](web-editor-features.md#left-panel) section. 

**Context menu for image or media files**

You can also perform some common operations for images and media files using the context menu. Right-click at any place on your image to invoke the context menu.

The context menu provides options to cut, copy, or paste the image or media. You can insert an element before or after the selected element. You also have the option to rename or unwrap an element. You can locate the selected image or media in the repository or view the preview of the file in Assets UI.

The other options in the context menu allow you to copy a path, edit an image map, rename element, create a snippet, or generate IDs for the selected element.

**Insert/Edit Image Map** 

Inserts an image map on the selected image. An image with clickable areas that link to topics or web pages is called an image map.

Select an image in the current topic and select the Insert/Edit Image Map icon to open the insert Image Map dialog box.

![](images/insert-image-map.png){width="650" align="left"}

Choose the preferred shape Rectangle ![](images/imagemap-rectangle-toolbar.png), Circle ![](images/imagemap-circle-toolbar.png), or Polygon ![](images/imagemap-polygon-toolbr.png) to define an area over an image that you want to use as a link. After defining an area, the Reference dialog appears wherein you need to specify the link to internal or external content:

![](images/reference-dialog.png){width="650" align="left"}

If areas overlap, you can bring the shape forward or send it backward by clicking on the respective icon in the toolbar. You can also remove an area by selecting it and clicking the Delete icon. Double-clicking on an area opens the Reference dialog wherein you can change the destination link. Once you have marked the required areas on your image, save the changes by selecting **Done**.


**Multimedia** 

Inserts different types of multimedia files. Select the Multimedia dropdown icon and choose the type of file you want to insert. The supported multimedia formats are:

- Audio File
- Video File
- YouTube
- Vimeo

On selecting the Audio or Video file option, you are shown the repository view to browse and select the desired file. If you choose YouTube or Vimeo, then you get the Insert Multimedia dialog. Paste the link of the video file in the Web Link field and select Insert to add the video at the current or next valid location in your document.

>[!NOTE]
>
> While adding a YouTube video link, you need to replace the string `watch?v=` with `embed` in the URL. For example, to add a YouTube video link: `https://www.youtube.com/**watch?v**=WlIKQOrmZcs`, you need to add it as: `https://www.youtube.com/**embed/**WlIKQOrmZcs`. This change ensures that the video gets embedded in the AEM Site and PDF output.

You can also add the Audio or Video File from the Insert Multimedia dialog. Select the Audio/Video File option and then, select the browse icon to launch the repository view. Select the audio or video file from the repository and select **Select** to add the link of the file in the Audio/Video File field. In case you choose a video file, then a preview of the file is also shown in the Preview area. You can play the video file to view its preview.

![](images/insert-multimedia.png){width="650" align="left"}

**Cross Reference** 

Insert references of type — Content Reference, Content Key Reference, Key Reference, File Reference, Web Link, or Email Link.

Select the **Select File** icon \(for Content Reference and File Reference\) or **Select Root Map** icon \(for Content Key Reference and Key Reference\) and select the desired file or content to link to.

![](images/insert-references.png){width="650" align="left"}

A link of the selected reference is added in the document. The context menu on the link gives you the options to:

- **Insert Element**: Shows a list of valid elements that you can insert at the given context.
- **Copy UUID**: Copies the UUID of the inserted reference.
- **Copy Path**: Copies the complete path of the inserted reference.
- **Generate IDs**: Generates unique ID for the inserted reference.

You can also search using the UUID of the file that you want to reference. For Content and Key Reference links, enter the UUID of the file that you want to link to, and the file is automatically searched and displayed in the Preview section. When you specify the UUID of the file, you need not explicitly mention the file extension for .xml files. The .xml extension is auto-appended to the UUID.

![](images/insert-content-using-uuid-search.png){width="650" align="left"}

If your administrator has enabled the UUIDs option in *XMLEditorConfig*, then you will view the UUID of the referenced content in the **Link** property.

![](images/ref-link-uuid_cs.png){align="left"}

>[!NOTE]
>
> If the **Enable UUIDs** option is not enabled, then the relative path of the referenced content is shown.

>[!IMPORTANT]
>
> Even though the relative path of the referenced content is shown in the **Link** property, internally the link is created using the UUID of the referenced content.

>[!TIP]
>
> View the References section in the Best practices guide for best practices around referencing content.

**Filter Search**

You can search for some text in the files present on the selected path of the AEM repository. For example, 'general' is searched in the given below screenshot. You can also narrow down your search using enhanced filters. You can look for all DITA Files like DITA Topics and DITA Maps present on the selected path.

You can search for Non-DITA Files like the Image Files, Multimedia, and documents in the selected path. You can also search for specific values in the attributes of DITA elements. You can also look for files which are checked out by the specified user.

![](images/reference-search-filters.png){width="650" align="left"}

>[!NOTE]
>
> Your system administrator can also configure the text filters and show or hide other filters. For more details, view *Configure text filters* section in the Install and configure Adobe Experience Manager Guides as a Cloud Service.

The list of filtered files which contain the searched text is displayed. For example, in the above screenshot the files containing the text 'general' are listed. You can also preview the content of the file.


**Reusable Content** - ![](images/reusable-content.svg)

Reuse content that exists within any other document in your project. You can insert content by directly linking to the content in a file or by using a key reference, view [Resolve key references](map-editor-other-features.md#id176GD01H05Z). When you select the Reusable content icon, you get the Reuse Content dialog box:

![](images/reuse-content-dialog.png){width="650" align="left"}

In the Reuse Content dialog box, select the DITA file for file references or the DITA map file that contains the key references. Once selected, the topic or key references are shown in the dialog. You can select the ID/key of the topic that you want to insert and select **Done** to insert the content within your topic.

For inserting Content Reference, you can also enter the UUID of the file and the reusable content from that file is listed in the Preview section.

Based on the setting for inserting links, you could either view the UUID of the inserted content or the relative path in the Properties panel or the Source code view. The link is always created using the UUID of the referenced content. View *Configure UUID-based links* in the Install and configure Adobe Experience Manager Guides as a Cloud Service.

>[!NOTE]
>
> To add content before or after the referred content, use *Alt*+*Left* Arrow or Alt+*Right* Arrow keys to move the cursor to the desired location.

You can also embed the referred content within the topic by right-clicking on the referred content and choosing **Replace Reference with Content** from the context menu.

**Symbol** - ![](images/symbol-icon.svg)

Inserts special characters in your topic. Select the Symbol icon to open the Insert Special Character dialog box.

>[!NOTE]
>
> Experience Manager Guides provides movable and resizable dialog boxes. Dialogs that have two cross lines at the bottom-right corner can be resized. The cross lines in the Special Character dialog are shown below.

![](images/insert-special-char.png){width="550" align="left"}

In the Insert Special Character dialog box, you can search for a special character using its name. All special characters are stored under various categories. Use the Select Category drop-down list and select a category. The special characters available within the selected category are displayed. You can navigate the list of special character using the arrow keys or select the desired character that you want to insert. The Name and Hex Code of the selected special character are displayed below the list. Select **Insert** to insert the selected character in your document.

**Keyword** - ![](images/Keyword_icon.svg)

Insert keyword defined in your DITA map. Select the Keyword option to open the Key Reference dialog box.

![](images/insert-keyword.png){width="550" align="left"}

The keywords are listed in alphabetical order and you can also search keyword\(s\) by typing a search string in the Search box. The search result will return the keywords containing the string in ID or Value. The keywords defined in your DITA map are listed in this dialog. Choose the keyword that you want to insert and select **Insert**.

You can also change the attributes of the inserted keyword by right-clicking on the keyword and selecting the Attributes option. The **Attributes for Keyword dialog box open:

![](images/attributes-for-keyword.png){width="550" align="left"}

You can change the keyword's attributes or add a new attribute to the keyword.

**Snippets** - ![](images/insert-snippet-icon.svg)

Insert a snippet at the current or next valid location. For this feature to work, you must have snippets defined in your system. For more information about adding a snippet, view the **Snippet** feature description in the [Left panel](web-editor-features.md#left-panel) section. 

When you select the Snippets option, you are shown the Insert Snippet catalog. The catalog is context-sensitive, which indicates that it will show the snippets only if they are allowed at the current location.

The following example shows two pre-configured snippets - Warning and Error that can be inserted at the current location in the document.

![](images/insert-snippet.png){width="300" align="left"}

When you choose a snippet from the list, it gets inserted at the current or next valid location in the document. The following screenshot shows the Error snippet inserted in the document:

![](images/error-snippet.png){width="400" align="left"}

**Citations** - ![](images/Citations_icon.svg)

Create Citations and add them to your content. Learn how to [add and manage citations in your content](./web-editor-apply-citations.md).

**Query data** - ![](images/data-sources-new-icon.svg)

Connect with your data source and use the data to create content. Learn how to [use data from your data source](./web-editor-content-snippet.md).

### Version information and Save as new version

The **Version information & Save as new version** feature combines version tracking and content saving into a single functionality.

- Version information displays the current version of the topic or map. An asterisk (*) appears next to the version number to indicate unsaved changes. 

    The version number changes with every new version that is created for the topic or map file. If you are working on a newly created document, the version information is shown as **none**.

    ![](images/version-information.png){align="left"}


- **Save as new version** is a button that saves the changes you have made in your topic and also creates a new version of your topic.

    ![](images/save-as-new-version.png){align="left"}


When you choose to save a topic or map using **Save as new version**, the following dialog box appears:

![](images/save-as-new-version-dialog.PNG){width="300" align="left"}

Enter comments and version labels to identify the changes and select **Save** to create a new version of your file.

When you choose the **Save as new version** option, the first version of the topic is created in DAM, which also becomes the currently active version of your topic. Later, if you revert to an older version of the topic, then that becomes your current active version of the topic.

If your administrator has pre-configured version labels, then you will view those labels in a drop-down list. You can choose a label from the list of available labels and save your document.

![](images/web-editor-pre-defined-labels.PNG){width="300" align="left"}

At the time of saving a topic, you can add a comment specifying the changes that you have made in the topic. This comment is shown in the topic's Version History.

If your topic is under review, your reviewers will get a notification saying that a newer version of the topic is available. They can easily access the latest revision of your document and continue reviewing the latest version of your topic.

When you hover your pointer over a topic's title, you are shown the file title, file path, and the version number.

![](images/mouse-hover-on-title_cs.png){align="left"}

>[!NOTE]
>
> Once a version of your topic is available, you can also add labels to your topic. These labels can then be used to create a baseline for publishing a specific version of your document. For more information about using labels in your topics, view [Use labels](web-editor-use-label.md#).

### Lock/unlock 

Locks or unlocks the current file. Locking a file gives you an exclusive write access to the file. This restricts other users from editing the file. Unlock the file if you want others to have editing access. When the file is unlocked, the changes are saved in the current version of the file.

![](images/web-editor-lock-button.png){align="left"}

If you are in the Map View and you expand the parent map, you can lock all files in the map with a single click. Simply expand the parent map file and select the parent file, which results in selecting all files within the map. Then you can select **Lock**  ![](images/LockClosed_icon.svg) to get the lock on all files within the map.

In the Repository panel, the locked files are displayed with a lock icon. When you hover over this lock icon, the Locked by you/username is displayed as a tooltip. 

![](images/web-editor-locked-by-icon-new.png){width="350" align="left"}

If a file is locked by another user, hovering over the lock icon in the Repository displays the name of the user who locked it. In this case, the file opens in Read-only mode, with **Read-only access** displayed next to the version information.

As an administrator, you also get access to the **Force unlock** feature that allows you to unlock the file locked by other users. Use this feature to access the editing rights on a file locked by other users. 

![](images/web-editor-force-unlock-new.png){width="350" align="left"}

## Left panel

The left panel gives you quick access to Collections, Repository view, Map view, and more features. You can expand the panel by selecting the **Expand** icon placed at the bottom-left corner of the interface. Once expanded, use the **Collapse** icon to collapse the panel. In the expanded view, it displays the names of the icons which appear as tooltips in the collapsed view.

>[!NOTE]
>
> The left panel is resizable. To resize the panel, bring the cursor on the panel boundary, the cursor changes to a double-headed arrow, select and drag to resize the panel width.

The left panel gives you access to the following features:

- [Collections](#collections)
- [Repository](#repository)
- [Map](#map)
- [Reusable content](#reusable-content)
- [Outline](#outline)

Some of the features in the left panel are available under the **More** section. Select the More icon ![](images/Smock_MoreSmallList_18_N.svg) to access the below features: 

- [Glossary](#glossary)
- [Conditions](#conditions)
- [Subject scheme](#subject-scheme)
- [Snippets](#snippets)
- [Templates](#templates)
- [Citations](#citations)
- [Language variables](#language-variables)
- [Variables](#variables)
- [Find and replace](#find-and-replace)
- [PDF templates](#pdf-templates)
- [Review](#review)


An additional option labeled as **Workfront** is also displayed in the left panel if Adobe Workfront is configured. 

For details, view [Workfront integration](./workfront-integration.md).

>[!NOTE]
>
> The features available in the left panel are managed by your administrator, allowing them to enable or disable the individual features present in the left panel. Only enabled features are displayed in the left panel. For more details, view the **Panels** section of [Tab bar](#tab-bar). 

The detailed explanation of the left panel features is as follows:

### Collections 

If you work on a set of files or folders, you can add them to your favorite list to access them quickly. **Collections** show the list of documents that you have added and other publicly accessible list of documents from the other users.

By default, you can view the files by titles. As you hover over a file, you can view the file title and the file path as a tooltip.

>[!NOTE]
>
> As an administrator, you can also choose to view the list of files by filenames in the Editor. Select the **File name** option of the **Editor files display configuration** section in **User preferences**. 

To create a new collection, Select the + icon next to Collections panel to bring up the **New collection** dialog box:

![](images/favorite-new-collection.PNG){width="300" align="left"}

Enter a title and description for the collection that you want to create. If you select **Public**, then this favorite is shown to other users as well.

>[!NOTE]
>
> You can also create a collection from the Experience Manager Guides Home page. Open the home page, navigate to the **Collections** widget in the [Overview section](./intro-home-page.md#overview), and select **New collection**.  

To add a file to collections, use any of the following methods:

- Navigate to the required file or folder in the Repository view, select the *Options* icon to open the context menu, and choose **Add to** > **Collections**. In the **Add to collections** dialog box, you can choose to add the file/folder to an existing favorite or create a new one.

  ![](images/favorite-add-file-folder.png){width="300" align="left"}

- Right-click on a file's tab in the editor to open the context menu. Choose **Add to** > **Collections** to add the file to your favorites list.

  ![](images/favorite-add-from-file-context-menu_cs.png){align="left"}
 

>[!NOTE]
>
> - To remove an item from the favorites list, select the Options icon next to the item in a Favorites collection and choose **Remove from collections**.
> - To preview the file without opening it, select a file and then select **Preview** from the Options menu. 

**Options menu for a collection**  

You can also perform many actions using the Options menu available for a Collection: 

![](images/favorites-options.png){width="650" align="left"}

- **Rename**: Rename the selected collection. 
- **Delete**: Delete the selected collection.  
- **Refresh**: Get a fresh list of files and folders from the Repository. 
- **View in Assets UI**: Show the file or folder contents in the Assets UI. 

>[!NOTE]
>
> You can also refresh the list using the Refresh icon on the top. 


### Repository 

When you select the Repository icon, you get a list of files and folders available in DAM. By default, you can view the files by titles. As you hover over a file, you can view the file title and the file name as a tooltip.   

>[!NOTE]
>
> As an administrator, you can also choose to view the list of files by filenames in the Editor. Select the **File name** option of the **Editor files display configuration** section in **User preferences**.

75 files are loaded at a time. Each time you select **Load more**… 75 files are loaded, and the button stops being displayed when all the files have been listed. This batch loading is efficient, and you can access the files faster in comparison to loading all the files existing in a folder.

You can easily navigate to the required file within DAM and open it in the Editor. If you have the required access to edit the file, then you can do so.

You can also select and play an audio or video file in the Editor. You can change the volume or
the view of the video. In the shortcut menu you also have the options to download, change playback
speed, or view picture in picture.

Select a map and press Enter or double-click to open it in the **Map view**. For more details, view the **Map view** feature description in the [Left panel](#left-panel) section. Select a topic and press Enter or double-click to open it in the [Content editing area](#content-editing-area). Being able to navigate and open a file directly from the Editor saves time and increases productivity. 

**Filter Search in Repository**

The Editor provides enhanced filters for searching text. You can search and filter for a text in the files present on the selected path of the Adobe Experience Manager repository. It searches in the title, filename, and content in the files.


![search files in repository view](images/repository-filter-search.png){width="300" align="left"}

*Apply filters to search for the files containing the text `personal spaceship.`* 

 Select the **Filter Search** \(![Search filter icon](images/filter-search-icon.svg)\) icon to open the Filter pop-up. 

>[!NOTE]
>
> When you search any text or filter any files, a blue dot appears on the **Filter Search**  \(![Search filter icon](images/filter-search-icon.svg)\) icon to indicate that we are on the search panel and that some filters have been applied.


You have the following options to filter the files and to narrow down your search in the Adobe Experience Manager repository:

- **DITA Files**: You can look for all **DITA Topics** and **DITA Maps** present on the selected path. These are selected by default.
- **Non-DITA Files**: You can search for **Ditaval Files**,  **Image Files**, **Multimedia**, **Documents**, and **JSON** in the selected path.

    ![quick search filter ](images/repository-filter-search-quick.png) {width="300" align="left"}

    *Use the quick filters to search for DITA and Non-DITA files.*

**Advanced filtering**

Select the **Advanced filtering** ![advanced filter icon](images/advanced-filter-gear-icon.svg)icon to view the **Advanced filter** dialog box. 

You can view the following options under the **General** and **Advanced** tabs.  

![advanced filter dialog box](images/repository-filter-search-advanced.png) {width="650" align="left"}


**General**

- **Search results with**: Search for some text in the files present on the selected path of the Adobe Experience Manager repository. The text is searched in the title, filename, and content in the files.

This is in sync with the search box on the repository window. For example, if you type `general purpose` in the search box on the repository panel, it also appears in the **Advanced filter** dialog box and vice versa.

- **Search in**: Select the path where you want to search the files present in the Adobe Experience Manager repository. 

**Advanced**

- **DITA Elements**: You can also search for specific values in the attributes of the specified DITA elements. 
    - Select **Add element** to add the elements, attributes, and values.  
    - Apply the filters that you have selected. 

- Select **Clear all** to clear all the applied filters. 


- Select the **Close filter** ![close icon](images/close-icon.svg) icon to close the filter and return to the tree view of the repository.

    >[!NOTE]
    >
    >Your system administrator can also configure the text filters and show or hide other filters. For more details, view *Configure text filters* section in the Install and configure Adobe Experience Manager Guides as a Cloud Service.
    >
    >The list of filtered files that contain the searched text is displayed. For example, the files containing the text `personal spaceship` are listed in the previous screenshot. You can select multiple files from the filtered list to drag and drop them into a map opened for editing.

**Options menu**

In addition to opening files from the left panel, you can also perform many actions using the Options menu available in the Repository view. You will view different options, depending on whether you choose a folder, topic file, or a media file.

**Options for a folder**

You can perform the following actions using the Options menu available for a *folder* in the Repository view:

![](images/options-menu-folder_cs.PNG){width="550" align="left"}


- **New**: Create a new DITA topic, DITA map, or a folder. 

   Steps to create a new topic:
   1. Select **New** > **Topic**.
   2. The **New topic** dialog box is displayed.
    
        ![](images/create-topic-dialog.png){width="300" align="left"}

   3. In the **New topic** dialog box, provide the following details:
        - A Title for the topic.
        - \(Optional\)* The file name for the topic. The file name is auto-suggested based on the topic Title. In case your administrator has enabled automatic file names based on UUID setting, then you will not view the Name field.
        - A template on which the topic will be based. For example, for an out-of-the-box setup, you can choose from the Blank, Concept, DITAVAL, Reference, Task, Topic, Markdown, Glossary, and Troubleshooting templates. If your folder has a Folder Profile configured on it, then you will view only those topic templates that are configured on the Folder profile.

        - Path where you want to save the topic file. By default, the path of currently selected folder in the repository is shown in the Path field.
    
    4. Select **Create**. The topic is created at the specified path. Also, the topic is opened in the Editor for editing.

    Steps to create a new DITA map:

   1. Select **New** > **DITA map**.
   2. The **New map** dialog box is displayed.
    
        ![](images/create-map-dialog.png){width="300" align="left"}

   3. In the **New map** dialog box, provide the following details:
        - A Title for the map.
        - *\(Optional\)* The file name for the map. The file name is auto-suggested based on the map title. In case your administrator has enabled automatic file names based on UUID setting, then you will not view the Name field.
        - A template on which the map will be based. For example, for an out-of-the-box setup, you can choose from the Bookmap or DITA map templates.
        - Path where you want to save the map file. By default, the path of currently selected folder in the repository is shown in the Path field.
   4. Select **Create**. The map is created and added within the folder specified in the Path field. Also, the map is opened in the Map view. You can open the map file in the Map Editor and add topic to it. For more information about adding topics to a map file, view [Create a map](map-editor-create-map.md#). Alternatively, select **Open in map console** to open the map in Map console.

    Steps to create a new folder:

   1. Select **New** > **Folder**.
   2. The **New folder** dialog box is displayed.
    
        ![](images/new-folder-dialog_cs.png){width="300" align="left"}

   3. In the **New folder** dialog box, provide the following details:
        - A Title for the folder, which is auto-converted into the folder name.
        - Path where you want to save the folder. By default, the path of currently selected folder in the repository is shown in the Path field. 
   4. Select **Create**. The folder is created and added within the folder from where the create folder option was executed.

- **Upload Assets**: Upload a file from your local system to the selected folder in Adobe Experience Manager repository. You can also drag-and-drop files from your local system onto your current working topic. This is very useful if you want to insert images from your local system into your topic.

    ![](images/upload-assets.png){width="300" align="left"}

    You can select a folder where you want to upload the file and a preview of the image is also shown. If you want to rename the file, you can do so in the file name text box. Select **Upload** to complete the file upload process. If you have dragged and dropped an image file on a topic, then the image file is added in the article, and it is also uploaded.

    If your administrator has enabled the UUIDs option in *XMLEditorConfig*, then you will view the UUID of the uploaded image in the **Source** property.

    ![](images/uuid-in-source-upload-image_cs.png){align="left"}

- **Find files in folder**: Shifts the focus to repository search wherein you can enter the search term. The search is performed under the selected folder in the repository. You can also apply a filter to return DITA Files, Image Files, or both.

    ![](images/find-files-in-folders-repo-view_cs.png){width="300" align="left"}

    You can also search using the UUID of a file. In that case, the search results display the title of the DITA/XML file and in case of the file is an image file, then the UUID of the file is displayed. In the following search example, the UUID of an image file is searched and the search results display the UUID of the original image file and the topic title of the file where that image is referenced.

    ![](images/uuid-repo-search-image-topic-file_cs.png){width="300" align="left"}

- **Collapse**: Collapse the selected folder in the repository.

    >[!NOTE]
    >
    > Use the **\>** icon next to a folder to expand it.

- **Add to collections**: Adds the selected folder to favorites. You can choose to add it to an existing or new collection.

- **Refresh**: Get a fresh list of files and folders from the repository.
- **View in Assets UI**: Show the folder contents in the Assets UI.

**Options for a file**

Get access to different options in the Options menu depending on whether you select a media file or a DITA file. Some common options available for both media and DITA files are:

- Edit
- Open in FrameMaker 
- Duplicate
- Lock/unlock
- Preview
- Move to
- Rename
- Delete
- Generate 
- Download as PDF
- Add to 
- Copy
- View in Assets UI
- Properties


![options menu of a file in the repository view](images/options-menu-repo-view-file-level.png){width="550" align="left"}

The various options in the Options menu are explained below:

- **Edit**: Open the file for editing. In case of a .ditamap/.bookmap file, it is opened in the [Map Editor](map-editor-advanced-map-editor.md#) for editing.

- **Duplicate**: Use this option to create a duplicate or a copy of the selected file. You also have the option to rename the duplicate file in the Duplicate Asset prompt. By default, the file is created with a suffix \(like filename\_1.extension\). The title of the file remains same as the source file and the new file begins with version 1.0. All references, tags, and metadata are copied while the baselines are not copied in the duplicate file.
- **Lock**: Get a lock on the selected file for editing. If the file is locked, hovering the mouse pointer over the lock icon shows **Locked by you** if you locked it, or **Locked by [username]** if another user has locked it. 

- **Preview**: Get a quick preview of the file (.dita, .xml, audio, video, or image) without opening it. You can resize the preview pane. If the content contains any `<xref>` or `<conref>`, you can select it to open it in a new tab. The title of the file appears in the window. If no title is present, then the filename appears. To close the **Preview** panel, you can either select the close icon or select anywhere outside the pane.  

    ![](images/quick-preview_cs.png){align="left"}

-  **Rename**: Use this option to rename the selected file. Enter the name of the new file in the **Rename Asset** dialog.  
    - You can rename a file of any type. 
    - You can't change the extension of a file. 
    - Two files cannot have the same name. So, you cannot rename a file to a name that already exists. An error is displayed. 

-  **Move to**: Use this option to move the selected file to another folder.  
   - You can either type the name of the destination folder or choose **Select Path** to select the destination folder.    
   - You can move a file of any type to any destination within the Content folder. 
   - Two files cannot have the same name. So, you cannot move a file to a folder where a file with the same name already exists.  

    If you try to move a file to a folder where a file with the same name but a different title exists, the Rename and move file dialog is displayed, and you need to rename the file before moving it. The moved file in the destination folder has the new file name.  

    ![](images/rename-move-asset.png){width="550" align="left"}

    >[!NOTE]
    >
    > You can also drag and drop a file to another destination folder. 

    **Exclusion scenarios**   

    Experience Manager Guides doesn't allow you to rename or move a file in the following scenarios: 

    - You cannot move or rename a file if it's part of a review or a translation workflow. 

    - If any other user locks the file, you cannot rename or move it, you will not view the Rename or Move to option for the file. 

    >[!NOTE]
    >
    > If your administrator has given you the permissions on a folder, only then the **Rename** or **Move to** options are displayed. 

    <details>
    <summary> Cloud Services </summary>

    Renaming or moving any file does not break any existing references from or to the file, as every file has a unique UUID. 
    </details>

- **Delete**: Use this option to delete the selected file. A confirmation prompt is displayed before deleting the file.

    - A confirmation prompt is displayed before deleting the file.
    - If the file is not referenced from any other file, it is deleted, and a success message is displayed.
    - If the file is locked, you cannot delete it, and an error message is displayed.

        >[!NOTE]
        >
        > If your administrator has prevented the deletion of locked files, only then the error message is displayed. For more details, view *Prevent deletion of checked out files* section in the Install and configure Adobe Experience Manager Guides as a Cloud Service.

    - If the file is added to a collection, the **Force Delete** dialog box is displayed, and you can forcefully delete it.
    - If the file is referenced from any other file then **Force Delete** dialog with the confirmation message is displayed, and you can forcefully delete the file:

        ![](images/options-menu-force-delete.png){width="300" align="left"}

        >[!NOTE]
        >
        > If your administrator has given the file delete permission, then **Force Delete** is enabled. Else, **Force Delete** is disabled and a message is displayed that you do not have permission to delete referenced files. For more details, view *Prevent deletion of referenced files* section in the Install and configure Adobe Experience Manager Guides as a Cloud Service.

    - If you delete a referenced topic and you have opened the file containing references for edit, it will show the broken link for the referenced file.

    >[!NOTE]
    >
    > You can also delete the selected file similarly using the Delete key of the keyboard.

- **Copy**: You can choose from the following options:

    - **Copy UUID**: Copy the UUID of the selected file to Clipboard.

    - **Copy Path**: Copy the complete path of the selected file to Clipboard.

- **Add to**: You can choose from the following options:
    - **Collections**: Adds the selected file to Collections. You can choose to add it to an existing or new collection.

    - **Reusable content**: Adds the selected file to the Reusable content list in the left panel.

- **Properties**: Use this to open the properties page of the selected file. This properties page can also be accessed from the Assets UI by selecting a file and then selecting Properties icon in the toolbar.

- **Open in map dashboard**: In case the selected file is a DITA map, then this option opens the map dashboard.

- **Open in map console**: In case the selected file is a DITA map, then this option opens the map console.

-  **Edit in Oxygen**: Select this option to edit the selected file in the Oxygen connector plugin. The file is opened for editing.

    >[!NOTE] 
    >
    >Contact your customer success team to get this feature enabled in the environment. This isn't enabled as a part of the out-of-the-box support. For more details, view the [Configure the option to edit in Oxygen ](../cs-install-guide/conf-edit-in-oxygen.md) section in the Installation and Configuration Guide.
 

- **View in Assets UI**: Use this to show a preview of a .dita/.xml file in the Assets UI. In case of a .ditamap/.bookmap file, all topic files within the map are shown in a single unified page-by-page view.

-  **Download as PDF**: Use the option to generate the PDF output and download it.  

- **Generate**: Use the option to publish a map or topics within a map to a Sites page, Content Fragment, or Experience Fragment.

### Map 

When you select the Map view icon, the Map view is displayed where a list of topics within the map file is displayed. If you have not opened any map file, then the Map view appears blank. Double-clicking on any map file opens the map file in this view. You can double-click on any file within the map to open it in the Editor.

By default, you can view the files by titles. As you hover over a file, you can view the file title and the file path as a tooltip.

>[!NOTE] 
>
>As an administrator, you can also choose to view the filename of the parent map which is currently opened in the map view. Select the **File name** option of the **Editor files display configuration** section in **User preferences**.


When you open a map in the map view, the title of the current map is displayed in the center of the Tab bar. If the title is too long, then an ellipsis is displayed and you can also hover over the title to view the full title in the tool tip. 

When you define key attributes for the topic or map references, you can view the title, the corresponding icon, and the key in the left panel. The key is displayed as `keys=<key-name>`. 

![Keys in map view](images/view-key-title-map-view.png){width="300" align="left"}

If you have editing rights on the map files, you will be able to edit the files as well. For more information about opening and editing a topic through DITA map, view [Edit topics through DITA map](map-editor-advanced-map-editor.md#id17ACJ0F0FHS).

The following options are available for a map file in the Map view:

- **Open in map console**: Opens the map file in the Map console.
- **Edit**: Opens the map file for editing.
- **Options**: Opens the context menu for the selected map file.

You can perform the following actions using the Options menu of the map file:

![Options menu in Map view](images/options-menu-map-view_cs.png){align="left"}

- **Edit**: Open the map file for editing in the Map Editor.

- **Select all**: Select all files in the map.

- **Clear selection**: Deselect the selected files in the map.

- **Lock**: Get a lock on the selected files in the map.

- **Unlock**: Unlocks the map file and makes it available for editing. It does not revert the changes to earlier version.

- **Save as new version and unlock**: Create a newer version and release the lock on the selected files in the map.

- **Preview**: Open a preview of the map file. In this view, all topic files within the map are shown in a single unified page-by-page view.

- **Copy**: You can choose from the following options:
    - **Copy UUID**: Copy the UUID of the map file to Clipboard.
    - **Copy Path**: Copy complete path of the map file to Clipboard.

- **Locate in repository**: Shows the location of the map file in the repository \(or DAM\).

- **Add to**: You can choose from the following options:
    - **Collections**: Adds the map file to collections. You can choose to add it to an existing or new collection.

    - **Reusable content**: Adds the map file to the Reusable content list in the left panel.

- **Properties**: Use this to open the properties page of the map file. This properties page can also be accessed from the Assets UI by selecting a file and selecting the Properties icon in the toolbar.

- **Open map dashboard**: Opens the map dashboard.

- **View in Assets UI**: Use this to show a preview of the map file in the Assets UI. In this view, all topic files within the map are shown in a single unified page-by-page view.
- **Download map**: Select this option to open the **Download map** dialog box. 

    In the **Download Map** dialog box, you can choose the following options:

    **Use Baseline**: Select this option to get a list of Baselines created for the DITA map. If you want to download the map file and its contents based on a specific Baseline, select the Baseline from the drop-down list. For more details about working with Baselines, view [Work with Baseline](./generate-output-use-baseline-for-publishing.md).

    **Flatten File Hierarchy**: Select this option to save all referenced topics and media files in a single folder.
 
    You can also download the map file without selecting any option. In that case, the last persisted versions of the referenced topics and media files are downloaded.
   
    After you select the **Download** button, the map export package request is queued. The **Success** dialog box is displayed if the package is created successfully.  You can select the **Download** button from the **Success** dialog box. 
    
    You receive the map download-ready notification if the map is ready to download. In case the download fails, you receive the notification that the map download failed.

    You can access the download link from the Adobe Experience Manager notification Inbox. Select the generated map notification in the Inbox to download the map in .zip format.

    >[!NOTE]
    >
    >  By default, the downloaded maps remain for five days in the Adobe Experience Manager notification Inbox.

- **Close map context**: Closes the map file.

The following screenshot shows the Options menu for a file in the map view:

![](images/options-menu-file_cs.PNG){align="left"}

You can perform the following actions using the Options menu:

- **Edit**: Open the file for editing. In case of a .ditamap/.bookmap file, it is opened in the [Map Editor](map-editor-advanced-map-editor.md#) for editing.

- **Lock**: Locks the selected file. For a locked file, this option changes to **Unlock**.
    


    >[!NOTE]
    >
    > - If a file is locked by a user, hovering the mouse pointer over the lock icon shows the user \(name\) who has locked the file.
    > - When you check in a file, it prompts you to save the changes. If you don't save your changes, then it only checks in the file.

- **Preview**: Get a quick preview of the file (.dita, .xml, audio, video, or image) without opening it. You can resize the preview pane. If the content contains any `<xref>` or `<conref>`, you can select it to open it in a new tab.  The title of the file appears in the window. If no title is present, then the filename appears. To close the **Preview** pane, you can either select the close icon or select anywhere outside the pane.  
- **Copy**: You can choose from the following options:
    - **Copy UUID**: Copy the UUID of the selected file to Clipboard.
    - **Copy Path**: Copy complete path of the selected file to Clipboard.

    
- **Locate in repository**: Shows the location of the selected file in the repository \(or DAM\).
- **Expand all**: Expand all topics in the map files.

- **Collapse all**: Collapse all topics that are a part of the current map file.

- **Add to**: You can choose from the following options:
    - **Collections**: Adds the selected file to collections. You can choose to add it to an existing or new collection.

    - **Reusable content**: Adds the selected file to the Reusable content list in the left panel.

- **Properties**: Use this to open the properties page of the selected file. This properties page can also be accessed from the Assets UI by selecting a file and selecting the Properties icon in the toolbar.

- **View in Assets UI**: Use this to show a preview of a .dita/.xml file in the Assets UI. In case of a .ditamap/.bookmap file, all topic files within the map are shown in a single unified page-by-page view.

- **Generate**: Generate the output for the selected file at Sites page, Content fragment, or Experience Fragment.

>[!NOTE]
>
> You can also open and edit the properties of selected topics in a DITA map from the **More Options** menu under References.

### Reusable content

One of the main features of DITA is the ability to reuse content. The **Reusable content** panel can store your DITA files from where you generally insert reusable content. Once added, the DITA files remain in the Reusable content panel across sessions. This means that you don't have to add your DITA files again to access them later.

You can simply drag-and-drop reusable content from the panel onto your current topic and it gets inserted easily and quickly. You can also get a preview of the content before inserting it in your document.

By default, you can view the files by titles. As you hover over a file, you can view the file title and the file path as a tooltip.

>[!NOTE]
>
> As an administrator, you can also choose to view the list of files by filenames in the Editor. Select the **File name** option of the **Editor files display configuration** section in **User preferences**.

To add a DITA file to your Reusable content panel, use any of the following methods:

- Select the **+** icon next to Reusable content to open the browse file dialog box. Select the file that you want to add and then select **Add** to complete the process.

- In the Repository view, select the **Options** icon of the desired file and choose **Add to** > **Reusable content** from the context menu.

- Right-click on a file's tab in the editor to open the context menu and choose **Add to** > **Reusable content**.


Once the file is added, you can view all reusable content elements from the file in the Reusable content panel. Reusable content is shown with their IDs and element names.

When you add a file to the Reusable content list, the file's title is shown instead of the UUID of the file. To check the UUID of the file, mouse hover over the file's title and the UUID of the file is displayed in the tooltip.

![](images/uuid-reusable-content-file-title_cs.png){width="400" align="left"}

>[!NOTE]
>
> You can add multiple files to the reusable content list. Then you can insert the desired content from the Reusable content panel into your document.

**Refresh**: Rechecks for all reusable content and displays a fresh list of reusable content.

To insert content from the Reusable content panel, use any of the following methods:

- Hover the mouse pointer over an element that you want to insert, select the **Options** icon, and choose **Insert reusable content** from the dropdown.

    ![](images/insert-reusable-content_cs.png){width="400" align="left"}

    >[!NOTE]
    >
    > Select a file and then select **Preview** from the **Options** menu to preview the file without opening it. You can also preview the references present in a topic. The reference ID appears in the window. 
    >
    > The **Preview** option is also available in the **Options** menu of an element, which gives you a quick preview of the element before inserting it.  

- Drag-and-drop the reusable content item from the panel at the desired location in your document.

### Outline

When you select the **Outline** icon, you get the hierarchical view of the elements used in the document.

![](images/outline-view_cs.png){width="300" align="left"}

The Outline view offers the following features:

- A tree view of all elements used in the document.

- If an element has an ID, attribute, and text you can view them along with the element.

- Access Outline view in both Author and Source views.

- Use the filter drop-down list to show all elements or only the broken references:

- Choosing an element in the Outline view selects the element's content in the Author or Source view. The Outline view remains in sync with the Author and Source view. If you make any changes in any view, you can view them in the Outline view. For example, if you add a paragraph or update an element in the Author view, it is shown in the Outline view. 

    ![](images/select-element-content-outline-view_cs.png){width="650" align="left"}

- Drag and drop elements. You can easily replace an element by dropping another element on it. If you drag and drop an element over another element and you view a dashed rectangle box around the element, it indicates that the element will get replaced. It replaces the element on which the element is dropped.

    ![](images/replace-element-outline-view_cs.png){align="left"}

    If you drag and drop an element, a dashed rectangle indicates that the element can be placed at the current location. If the drag and drop is invalid, then an error message is shown to indicate that the operation is not allowed.

    ![](images/drop-element-outline-view_cs.png){align="left"}

- The **Options** menu in the *Outline* view allows you to perform generic operations such as Cut, Copy, Delete, Generate ID, Insert element before or after the current element, Rename or replace an element, Wrap an element, Unwrap an element, and create a snippet out of the selected element.

>[!NOTE]
>
>For more details on Generate ID, Insert element before or after the current element, and Unwrap an element, view [Other features in the Editor](web-editor-other-features.md#).

**View Configure**

Using the **View Configure** option, you can choose to view the following:

-  **Show ID**: Shows the id of the element.
-  **Show Attribute**: Shows the attribute along with its value.
-  **Show Text**: Shows the text. If the text is longer than 20 characters, then an ellipsis is displayed.

If a block element has its own text, it is displayed along with that block element. If it does not have it's own text, the text of the first child element is displayed along with that block element. 

![](images/outline-view-block-element.png){width="550" align="left"}

If your administrator has created a profile for attributes, then you'll get those attributes along with their configured values. You can also assign display attributes configured by your administrator under the **Display attributes** tab in the **Settings**. The attributes defined for an element are displayed in the Layout and the Outline view.


For more details, view the *Display attributes* within the *Settings* feature description in the [Left panel](#left-panel) section.

**Search feature**

Using the search feature, you can search for an element by its name, id, text or attribute value. 

The search is case-insensitive and exactly matches the string. The search results are sorted on the basis of the element's position in the document. 
 
You can search for a string in the element if it is shown in the **Outline** view. For example, if the string "Adobe" is present in the text of the element and is shown in the Outline View panel (as you have selected **Show Text** from the View Options dropdown), then the containing element is filtered. But if the text is not shown in the Outline View panel (as you have not selected **Show Text** from the View Options dropdown), then the containing element is not filtered. Similarly, you will find the string in the ID or attributes if you have selected them.

### Glossary

Experience Manager Guides allows you to easily create and use the glossary type documents. You can create glossary topic files and then include them in a common glossary map. Once this map is added as your root map, the glossary entries are then shown in the Glossary panel.

![](images/glossary-panel.png){width="650" align="left"}

To insert a term from the glossary, simply drag-and-drop the entry from the panel to the desired location in your topic. The Options menu of a glossary term allows you to get a quick **Preview** of the entry term, **Copy path** of the entry term file, or locate the entry term file in the repository.

Perform the following steps to search text terms and replace them with glossary abbreviations:

1. Open the DITA topic or map in which you wish to search and convert the text or terms.
1. Select the glossary panel to view the glossary terms present in the root map. You can drag-and-drop these terms to add them to the open topic.
1. Select the **Hotspot** tool \( ![](images/hotspot-icon.svg)\) in the Glossary panel to search and convert specific text terms to linked glossary abbreviations. Also, vice versa you can use it to search glossary abbreviations and convert them to text terms.

    

You can configure the following settings of the Hotspot tool:

![](images/glossary-hotspot-tool.png){width="300" align="left"}


- **Glossary keys**: Select the glossary keys from the DITA map you want to use for the search in the selected topic. The selected keys will be displayed below. You can remove a selected key by selecting the **Remove** icon.

- **Topics**: Choose either the **Current topic** opened in the Editor, all **Opened topics** in the current map, or the **Current map** being edited in the Map Editor to search the terms.
- **Filter Topics by Status**: You can choose to limit the search to topics that have the selected document status. The topics can be in Draft, Edit, In-Review, Approved, Reviewed, Done status, or in any one of the state as configured by the organization.
- **Action**: You can choose to either search the glossary keys **Manually for each topic** or **Automatically for all topics**. If you choose **Manually for each topic**, it prompts you to confirm before converting each term in every topic. If you choose **Automatically for all topics**, it converts all terms in all the topics automatically.
- **Convert**: You can either convert a searched **Text to glossary term** or **Glossary term to text.**
- **Options**: You can select from the following options:
    - **Case-sensitive match**: Searches for a term to find the match which has the same casing. For example, 'USB' will not match with 'usb'.
    - **Convert only the first instance**: If multiple instances of the searched term are present in a topic, only the first instance is converted.
    - **Lock file before conversion**: The searched file is locked before the terms are converted.
    - **Create a new version after conversion**: A new version of the topic is created after the conversion of terms has been completed.
- **Next** button appears if you select **Manually for each topic** option. Select **Next** to convert the terms for each topic on the basis of the selected settings. It prompts for conversion of terms in each topic and moves to the next file. You can choose to convert a term or skip it and move to the next term.

    ![](images/manual-convert-skip.png){width="300" align="left"}

- **Convert** button appears if you select **Automatically for all topics** option. Select **Convert** to convert all the terms found in the document to linked glossary abbreviations.

A list of the **Topics Updated** with the converted terms and **Topics with Error** is displayed. Hover over the info icon near Topics with Error to view the details of the error.

>[!NOTE]
>
> Refresh the topic to view the converted terms.

### Conditions

The Conditions panel displays the conditional attributes defined by your administrator in the global or folder-level profile. You can add conditions to your content by simply dragging and dropping the desired condition onto your content. The conditional content is highlighted using the color defined for the condition for easy identification.

You can also apply multiple conditions on an element by dragging-and-dropping multiple conditions on an element. When you apply multiple conditions on an element, the Properties panel displays the applied conditions separated with a comma.

![](images/multiple-conditions-applied_cs.png){align="left"}

However, in the Code view the conditions are separated using a space delimiter. When you add or edit a condition in Code view, ensure that multiple conditions are separated using a space.

>[!IMPORTANT]
>
> The following screenshot is of a user with administrative privileges. As a user with administrative privileges, you can add, edit, and delete conditions. Else, as a normal author, you will only get the option to apply conditions.

![](images/conditional-content-through-panel_cs.png){align="left"}

To add or define a condition, select the + icon next to Conditions panel to bring up the Define Condition dialog box:

![](images/conditional-panel-create-cond.png){width="400" align="left"}

From the Attribute list, select the conditional attribute that you want to define, enter a value for the condition, then specify the label that is displayed in the Conditions panel. Define a group for the condition. You can add multiple conditions to a group. You can also define a color for the condition. This color is set as the background color of the content on which the condition is applied.

You can group the conditions and structure them in nested folders. Groups help you create conditions at multiple levels and organize them better for use in the content. 

For example, you can create condition groups of products like *Acrobat* and *AEM Guides*. You can select the conditional attributes for both groups. Under each group, you can have specific values like *User*, *Admin*, *Reviewer*, and *Author*.  

>[!NOTE]
>
> Either type in to create a new group or select an existing group for a particular attribute.

You can use `/` and define sub-groups like `AEM Guides/Cloud Service`.



![condtions organised in a nested hierarchy](images/conditions-nested-hierarchy.png){width="300" align="left"}


To edit a condition, choose **Edit** from the Options menu. The Edit Condition dialog box is displayed:

![](images/conditional-panel-edit-cond.png){width="400" align="left"}

Specify the details in the same way as configured while defining a new condition.

### Subject scheme 

Subject scheme maps are a specialized form of DITA maps that are used to define taxonomic subjects and controlled values. Depending upon your requirements, you can create a subject scheme map and reference it within your root map file. Experience Manager Guides allows you to define the nested-level hierarchy of the subject definitions in your subject scheme.

You can easily create and then use the subject scheme in a subject scheme map. Once this map is added as your root map, the subject scheme is then shown in the Subject Scheme panel. The Subject scheme panel displays the available subject scheme in a nested or hierarchical manner.

Experience Manager Guides also supports nested level subject scheme maps, and you can have multiple subject schemes defined under the root subject scheme map.

The following example shows how to use subject scheme in Experience Manager Guides.

1. Create a subject scheme file in a tool of your choice. The following XML code creates subject scheme that binds values for the `platform` attribute.

```XML
<?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE subjectScheme PUBLIC "-//OASIS//DTD DITA Subject Scheme Map//EN" "subjectScheme.dtd">
    <subjectScheme id="GUID-4f942f63-9a20-4355-999f-eab7c6273270">
        <title>rw</title>
        <!-- Define new OS values that are merged with those in the unixOS scheme -->
        <subjectdef keys="os">
            <subjectdef keys="linux">    </subjectdef>
            <subjectdef keys="mswin">    </subjectdef>
            <subjectdef keys="zos">    </subjectdef>
        </subjectdef>
        <!-- Define application values -->
        <subjectdef keys="app" navtitle="Applications">
            <subjectdef keys="apacheserv">    </subjectdef>
            <subjectdef keys="mysql">    </subjectdef>
        </subjectdef>
        <!-- Define an enumeration of the platform attribute, equal to       each value in the OS subject. This makes the following values       valid for the platform attribute: linux, mswin, zos -->
        <enumerationdef>
            <attributedef name="platform">    </attributedef>
            <subjectdef keyref="os">    </subjectdef>
        </enumerationdef>
        <!-- Define an enumeration of the otherprops attribute, equal to       each value in the application subjects.       This makes the following values valid for the otherprops attribute:       apacheserv, mysql -->
        <enumerationdef>
            <attributedef name="otherprops">    </attributedef>
            <subjectdef keyref="app">    </subjectdef>
        </enumerationdef>
    </subjectScheme>
```

![](images/subject-scheme-panel-new.png){width="300" align="left"}

1. Save the file with a.ditamap extension and upload it to any folder in DAM.

    >[!NOTE]
    >
    > You can add a reference to the subject scheme file in the parent DITA map.

    ![](images/subject-scheme-root-map-new.png){width="550" align="left"}

1. Set the parent map as the root map in the **User preferences**. Once this map is added as your root map, the subject scheme is then shown in the Subject scheme panel.

    ![](images/subject-scheme-user-preferences-new.png){width="650" align="left"}
   

1. In the Editor, open the file where you want to use the subject scheme definitions.
1. Apply the subject scheme to your content by simply dragging and dropping the desired subject scheme onto your content. The content is then highlighted in the defined color.

    
    

**Handling hierarchical definitions of subject definitions and enumerations**

Besides handling the enumerations and the subject definitions present in the same map, Experience Manager Guides also provides the feature to define enumerations and subject definitions in two separate maps. You can define one or more subject definitions in a map and the enumeration definitions in another map and then add the map reference. For example, the following XML code creates subject definitions and enumeration definitions in two separate maps. 

The subject definitions are defined in `subject_scheme_map_1.ditamap`   

 
```XML
<?xml version="1.0" encoding="UTF-8"?> 
    <!DOCTYPE subjectScheme PUBLIC "-//OASIS//DTD DITA Subject Scheme Map//EN" "../dtd/libs/fmdita/dita_resources/DITA-1.3/dtd/subjectScheme/dtd/subjectScheme.dtd"> 
    <subjectScheme id="subject-scheme.ditamap_f0bfda58-377b-446f-bf49-e31bc87792b3"> 

    <title>subject_scheme_map_1</title> 
    
    <subjectdef keys="os" navtitle="Operating system">
        <subjectdef keys="linux" navtitle="Linux">
        <subjectdef keys="redhat" navtitle="RedHat Linux">
        </subjectdef>
        <subjectdef keys="suse" navtitle="SuSE Linux">
        </subjectdef>
        </subjectdef>
        <subjectdef keys="windows" navtitle="Windows">
        </subjectdef>
        <subjectdef keys="zos" navtitle="z/OS">
        </subjectdef>
        </subjectdef>
        <subjectdef keys="deliveryTargetValues">
        <subjectdef keys="print">
        </subjectdef>
        <subjectdef keys="online">
        </subjectdef>
    </subjectdef>
    <subjectdef keys="mobile" navtitle="Mobile">
        <subjectdef keys="android" navtitle="Android">
        </subjectdef>
        <subjectdef keys="ios" navtitle="iOS">
    </subjectdef>
    </subjectdef>
    <subjectdef keys="cloud" navtitle="Cloud">
        <subjectdef keys="aws" navtitle="Amazon Web Services">
        </subjectdef>
        <subjectdef keys="azure" navtitle="Microsoft Azure">
        </subjectdef>
        <subjectdef keys="gcp" navtitle="Google Cloud Platform">
        </subjectdef>
    </subjectdef>
    </subjectScheme>
```

The enumeration definition is present in    subject_scheme_map_2.ditamap. 

```XML
<?xml version="1.0" encoding="UTF-8"?> 
        <!DOCTYPE subjectScheme PUBLIC "-//OASIS//DTD DITA Subject Scheme Map//EN" "../dtd/libs/fmdita/dita_resources/DITA-1.3/dtd/subjectScheme/dtd/subjectScheme.dtd"> 
        <subjectScheme id="subject-scheme.ditamap_17c433d9-0558-44d4-826e-3a3373a4c5ae"> 
        <title>subject_scheme_map_2</title> 
        <mapref format="ditamap" href="subject_scheme_map_1.ditamap" type="subjectScheme"> 
        </mapref> 
        <enumerationdef>
        <attributedef name="platform">
        </attributedef>
        <subjectdef keyref="mobile">
        </subjectdef>
        <subjectdef keyref="cloud">
        </subjectdef>
        </enumerationdef>
        </subjectScheme>
```

 Here subject definitions are defined in `subject_scheme_map_1.ditamap`  while the enumeration def is present in `subject_scheme_map_2.ditamap`. The reference to `subject_scheme_map_1.ditamap` is also added in `subject_scheme_map_2.ditamap`. 

>[!NOTE] 
>
> As the `subject_scheme_map_1.ditamap` and `subject_scheme_map_2.ditamap` are referenced with each other hence the subject schemes are getting resolved.  

The subject-enumeration references are resolved in the following order of priority: 

1. Same map 
1. Referenced map  

 
The references are not resolved if the enumeration is not found in the same map and the referenced map. 

**Restrict the values to a specific element**

You can also restrict the conditions to some elements within a topic. Use the `<elementdef>` tag to define the element and the `<attributedef>` tag to define the condition that can be applied to the element.  If you don't add the `<elementdef>` tag, you can apply the conditions to all elements. 
For example, use the following enumeration to restrict the `@platform` attribute to the `<shortdesc>` element.  The other conditions are visible for all elements.

```XML
<enumerationdef>
    <elementdef name="shortdesc">
    </elementdef>
    <attributedef name="platform">
    </attributedef>
    <subjectdef keyref="deliveryTargetValues">
    </subjectdef>
    <subjectdef keyref="os">
    </subjectdef>
  </enumerationdef>
```


**Attributes** drop-down

You can also change the value of the subject scheme using the **Attributes** dropdown from the **Content properties** panel in the **Author** view. 

Perform the following steps to change the value:

 1. Select an attribute from the **Attribute** dropdown. 
 1. Select **Edit**.
 1. Select the required value from the **Value** dropdown.
 1. Select **Update**.   

You can also apply values for an attribute by selecting multiple values from the dropdown.

**Source view**

You can also change the values from the attribute's drop-down in the Source view. The Source view also prevents you from adding any incorrect value.

![](images/subject-scheme-code-error.png){width="550" align="left"}

**View and apply the subject scheme from the Conditions panel**

You can also view and apply the subject scheme from the Conditions panel.

To view the subject scheme from the Conditions panel, your system administrator must select the **Show subject scheme in the Conditions panel** option under the General tab in Settings. For more details, view the **Settings** section in the [Tab bar](#tab-bar).

The Conditions panel displays the flat vertical structure of the subject definitions within the subject scheme.

You can add conditions to your content by dragging and dropping the desired condition onto your content. The conditional content is highlighted using the color defined for the condition.

### Snippets

Snippets are small content fragments that can be reused across various topics in your documentation project. The Snippets panel shows a collection of content snippets that you have created. To insert a snippet, drag-and-drop the snippet from the panel to the desired location in your topic. The Snippets panel allows you to add, edit, delete, preview, and insert a snippet.

>[!IMPORTANT]
>
> The following screenshot is of a user with administrative privileges. As a user with administrative privileges, you can add, edit, and delete snippets. Else, as a normal author, you will only get the options to preview and insert a snippet.

![](images/snippets-panel_cs.png){align="left"}

To add a snippet, use any of the following methods:

- Select the **+** icon next to Snippets to open the **New Snippet** dialog box.

    ![](images/snippet-new-dialog.png){width="300" align="left"}

    In the New Snippet dialog box, provide a title which appears in the Snippets panel, a description, and XML code of the snippet content that you want to create. Select **Create** to save and create the snippet.

- In the content editing area, right-click on the element's breadcrumb that you want to use as a snippet and choose **Create Snippet** from the context menu. The New Snippet dialog appears with the XML code of the selected element populated in the **Content** field. Enter the **Title** and **Description** for the snippet and select **Create** to save the snippet.

- In the content editing area, right-click anywhere on the content that you want to use as a snippet and choose **Create Snippet** from the context menu. The New Snippet dialog box appears with the XML code of the selected element populated in the **Content** field. Enter the **Title** and **Description** for the snippet and select **Create** to save the snippet.

    The following screenshot highlights the breadcrumb and the content area from where you can invoke the context menu.

    ![](images/snippet-create-from-breadcrumb-content.png){width="350" align="left"}


To insert a snippet, use any of the following methods:

- Select a snippet from the Snippets panel and drag-and-drop it at the desired location in your topic.

- Place the insertion point where you want to insert the snippet, from the Options menu of the required snippet, choose Insert Snippet.


>[!NOTE]
>
> From the context menu of a snippet entry, you can also choose to Edit, Delete, get a Preview, or Insert a Snippet.

### Templates 

The Templates panel is available to only administrators. Using this panel, administrator can easily create and manage templates that can then be used by the authors. By default, the templates are categorized under *map* and *topic* type templates.

![](images/templates-panel_cs.png){width="300" align="left"}

By default, you can view the files by titles. As you hover over a template, you can view the file title and the file name as a tooltip.   

>[!NOTE]
>
> As an administrator, you can also choose to view the list of files in the Editor. Select the **File name** option of the **Editor files display configuration** section in **User preferences**.

To learn how to create custom templates, view [Create maps based on customized templates](./create-maps-customized-templates.md). 

### Citations 

In Experience Manager Guides, you can add and import citations and apply them to your content. You can add these citations from any source of books, websites, and journals.

For details, view [Add and manage citations in your content](./web-editor-apply-citations.md).

### Language variables

Experience Manager Guides provides the feature to use language variables in the Native PDF output. You can use language variables to define localized strings in the PDF output or to localize any static text in the output templates. You can use CSS styles to localize the strings coming from a CSS.

For details, view [Support for language variables](../native-pdf/native-pdf-language-variables.md).

### Variables

Experience Manager Guides allows you to create and manage variables for Native PDF publishing. For details, view [Variables in the PDF output](../native-pdf/native-pdf-variables.md).


### Find and replace

The Find and replace icon is located at the bottom of the left panel. The Find and replace panel allows you to search for and replace text across files in a map or a folder within your repository. You can find and replace in all topics of a map as well as topics present in the sub-maps within the map.

![](images/map-find-replace.png){align="left"}

By default, you can view the files by titles. As you hover over a file, you can view the file title and the file path as a tooltip.   

>[!NOTE]
>
> As an administrator, you can also choose to view the list of filenames in the Editor. Select the **File name** option of the **Editor files display configuration** section in **User preferences**.

To perform the global search and replace, perform the following steps:

1. Open the global **Find and replace** panel.
1. Select the **Look into** dropdown and select one of the following options to perform the search.

    - **Current Map**: To search in the currently opened map

        >[!NOTE]
        >
        > This option appears if you have already opened a map for editing.

    - **Path**: To search on the selected path
    - **Select Map**: To search in the selected map

1. You can use the **Options** dropdown and choose from the following options:

    - **Lock file before replace**: Select this option if you want to lock a file automatically before replacing the search term. This setting is more relevant in case your administrator has enabled the configuration to lock a file before editing. With the backend setting enabled, you should select this option. It will prevent the file lock dialog from prompting you to lock every file before making any change. If you do not select this option, then a prompt will appear before a file is opened for editing.
    - **Whole words only**: Select this option if you want to search for the whole search string. For example, if you enter over in the search string, then the search result will return all files containing words like over and overview. If you want to restrict your search to return the exact term that is entered, then select this option.
    - **Create new version after replace**: Select this option if you want to create a new version of the topic in which you choose to replace the text. You can also provide version comments which will be added with each updated file.

        If you don't select this option, then the changes are saved in the current version of the topic and no new version is created.

    - **Include indirect references**: Select this option if you want to search the string in the indirect references also within the DITA map. By default, this is disabled so the search is performed only on the direct references.

1. Enter the search term or text that you want to find.
1. Enter the text with which you want to replace the search term.
1. Press Enter or select **Search** icon \( ![](images/search-icon.svg)\) to perform the search.
1. Select a file from the search result list. The file is opened in the content editing area with the searched term highlighted in the content.

1. Select **Replace single occurrence** \( ![](images/replace-icon.svg)\) to replace the currently highlighted search term in the topic or select Next match ![](images/next-match-in-search.png) or ![](images/previous-match-in-search.png) Previous match to move to the next or previous occurrence of the text.
1. Select **Replace all** \( ![](images/replace-all-in-file-icon.svg)\)to replace all occurrences of the searched term in a single file with the replace term in a single click. You will be shown a notification after replacing all the occurrences in the selected file.

To enable the **Replace all** icon, your system administrator must select the option **Enable Replace All** under the **General** tab in **Settings**.

>[!NOTE]
>
> Hover over a file from the search result list to view Replace all in File icon on the right of it. You also get the Ignore File icon to remove the file from the search result. The files which you ignore are removed from the list and the searched term is not replaced in them.

Only one replace all operation can be performed at a time in the whole system, and till the time operation is being performed you will view "Replace all in progress" status. You can also abort the replace all operation in between or view the log report. If you abort the operation, you will receive a notification about it in your Inbox. You will be shown a success notification after replacing all the occurrences in the selected file.

![](images/replace-all-in-progress.png){width="300" align="left"}

You can also use the **Find in map** option from the **Options** menu of a map to find and replace text in a map. This option appears for a map opened in the repository panel or in the map view.

![](images/map-options-menu.png){width="550" align="left"}

### PDF templates

Enables you to work with various PDF templates. For details, view [PDF templates](../native-pdf/pdf-template.md). 

### Review

Experience Manager Guides provides the feature to display all the review tasks in your projects. You can view all the review projects and the active review tasks within the review projects, that you're part of from the **Review** panel.  You can then open the review tasks to view the comments of the various reviewers. 

The review panel displays the review tasks. By default, you can view the files by titles. As you hover over a file, you can view the file title and the file path as a tooltip.

>[!NOTE]
>
> As an administrator, you can also choose to view the list of files by filenames in the Editor. Select the **File name** option of the **Editor files display configuration** section in **User preferences**.

As an author, you can address the comments in a topic using the Editor. 

To view the review comments in the active review tasks that are present in your projects, perform the following steps:

1. Select Review in the left panel. The **Review** panel opens.  All the review projects and the active review tasks within the review projects, that you're part of are displayed.

    ![](images/web-editor-review-panel.png){width="300" align="left"}
1. Select a review project and then select a review task from the list to open it. 
1. You can also filter your projects in the following ways:

    - Enter the search term or text you want to find in the title of the project. Then press Enter to perform the search. For example, you can search all projects with the term 'space' in the title.

    - Select ![](images/filter-search-icon.svg)  to open the **Filter** dialog box. You can select all or only specific projects. The selected projects are listed in the **Review** panel.

        ![](images/active-review-select-project.png){width="300" align="left"}

       Enable the **Tasks initiated by me** option to view only the tasks that you've initiated. The toggle state of this option is maintained even after refreshing the page. Enable the **Show only active tasks** option to filter the project list to show tasks that are currently active.

1. By default, in your review project you will view a flat list of topics that have comments associated with them. Apply the required filters from the left rail to filter the topics based on the review comments present in them:

    - **View all topics**: Lists all topics present in the projects.
    - **View topics with comments**: List only the topics containing review comments.
1. You can also enter the search term or text you want to find in the topic's title or file path. The topics which contain the term in the title or the file path are listed. 
1. Double-click any topic to open it in the author view. You can view the comments in the **Comments** panel.

    ![](images/active-review-task-comments.png){align="left"} 

   >[!NOTE]
   > 
   > The **Review** panel and the **Comments** panel are in sync at all times. In the Comments panel, the comments are loaded based on the review task loaded in the Review panel.
   >You can view the closed review tasks in the left rail of Review Panel along with the active review tasks.
   >Additionally, for a closed review task you can view the review comments in the Comments panel on the right but the **Import Comments** and **Revert Version** buttons are disabled. 
   >For more information about how to address the comments, view [Address review comments](review-address-review-comments.md#).
 

## Content editing area 

The content editing area is where the content of your topic or map is displayed. You make all content edits in this area. It gives a WYSIWYG view of the content you are editing. 

At the bottom-left of the content editing area, you have the breadcrumb of the element at current cursor location. In the bottom-right corner, the available Editor views are displayed.

![](images/content-editing-area.png){align="left"}

To learn more about the Editor views available for a topic file in the content editing area, view [Editor views](./web-editor-views.md).

>[!NOTE]
>
> If you are working on a map file, then different options or views are displayed in the content editing area , including a **Layout** view for the map file. For more details, view [Map editor features](./map-editor-advanced-map-editor.md).

## Right panel

The right panel contains information about the currently selected document.

>[!NOTE]
>
> The right panel is resizable. To resize the panel, bring the cursor on the panel boundary, the cursor changes to a double-headed arrow, select and drag to resize the panel width.

The right panel gives you access to the following features:

- [Content properties](#content-properties)
- [File properties](#file-properties)
- [Review](#review-1)
- [Track changes](#track-changes)
- [Schematron](#schematron)

### Content properties

You can access the **Content properties** feature by selecting the **Content properties** icon in the right panel. The **Content properties** panel contains information about the type of currently selected element in the document and its attributes. 

**Type**: You can view and select the tags of the complete hierarchy for the current tag from the dropdown.

**Attributes**: The **Attributes** dropdown panel is available in Layout, Author, and Source views. You can easily add, edit, or delete the attributes.

1. Select **Add**. 

    ![attrubutes in content properties](images/properties-tab-attributes_cs.png){width="300" align="left"}

1. In the **Attribute** dropdown panel, select the attribute from the dropdown list and specify an attribute's value.  Then select **Add**. 

    ![attributes panel with multiple attributes ](images/attributes-multiple-properties.png){width="300" align="left"}

1. To edit the attribute, hover over it and select **Edit** ![edit-icon](images/edit_pencil_icon.svg).   

1. To delete the attribute, hover over it and select **Delete** ![delete-icon](images/Delete_icon.svg). 


>[!NOTE]
>
> Even if your topic contains referenced content, you can add attributes on it using the properties panel.

If your administrator has created a profile for attributes, then you will get those attributes along with their configured values. Using the content properties panel, you can choose those attributes and assign them to relevant content in your topic. This way you can also create conditional content, which can then be used to create conditional output. For more information about generating output using conditional presets, view [Use condition presets](generate-output-use-condition-presets.md#).

### File properties

View the properties of the selected file by selecting the File properties icon in the right panel. The File properties feature is available in all four modes or views: Layout, Author, Source, and Preview.

The File properties have the following two sections:

**General**

The General section gives you access to the following features:

![file-properties](images/file-properties-general.png){width="300" align="left"}

- **File name**: Displays the filename of the selected topic. The filename is hyperlinked to the properties page of the selected file.
- **ID**: Displays the ID of the selected topic.
- **Tags**: These are the metadata tags of the topic. They are set from the tags field in the properties page. You can type or select them from the dropdown.  The tags appear under the dropdown. To delete a tag, select the cross icon next to the tag. 
- **Edit more properties**: You can edit more properties from the file properties page.  
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

### Review

Selecting the Review icon opens the review panel wherein you can select a review task for the currently opened document and view comments.

![](images/review-panel-before-opening.png){width="300" align="left"}

If you have created multiple Review projects, you can select one from the drop-down and access the review comments.

Using the review panel, you can view and post replies to the comments given on the topic. You can accept or reject the comments one by one.

>[!NOTE]
>
> The comment box and reply box support multi-line entries and allows users to expand it as needed for providing comprehensive comments as well as detailed reply to the comments. You can use **Shift** + **Enter** to go to the next line while writing the comments or replies.

For more information, view [Address review comments](review-address-review-comments.md#).

### Track changes 

Using the Tracked changes feature of the right panel, you can view the information of all updates made in a document. You can also search for any specific updates made to the document.

>[!NOTE]
>
> Tracked changes feature shows all updates that have been tracked using the Enable/Disable Track Changes feature of the [Tab bar](#tab-bar).

### Schematron

"Schematron" refers to a rule-based validation language used to define tests for an XML file. The Editor supports Schematron files. You can import the Schematron files and also edit them in the Editor. Using a Schematron file you can define certain rules and then validate them for a DITA topic or a map.

Learn how to work with Schematron files in Experience Manager Guides, refer to [Support for Schematron files](./support-schematron-file.md).



**Parent topic**: [Introduction to the Editor](web-editor.md)
