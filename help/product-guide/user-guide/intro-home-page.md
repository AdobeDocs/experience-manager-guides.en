---
title: Adobe Experience Manager Guides Home page experience
description: Get to know the Home page of the Adobe Experience Manager Guides.
feature: Authoring
role: User
---
# Adobe Experience Manager Guides Home page experience

The Home page is the first thing that you see when logging into Experience Manager Guides. It provides you with a unified and intuitive welcome screen experience, which includes a quick view of recent files, collections, and more.

![](images/aem-home-page.png){width="800" align="left"}

The Experience Manager Guides Home page is divided into the following sections: 

 - Header bar 
 - Navigation bar 
 - Left panel 
 - Widget section  

## Header bar 

The header bar is the top-bar of the Home page that displays the Adobe Experience Manager logo (or a Unified Shell if you are using the Unified Shell as your Experience Manager Guides UI).  

![](images/aem-home-header.png){width="800" align="left"}

## Navigation bar 

The navigation bar surfaces tools to switch navigation, customize the overview layout, and expand or minimize the workspace view. It also displays the Experience Manager Guides profile (Global Profile or Folder Profile) that is currently being used.

![](images/aem-home-nav-bar.png){width="800" align="left"}

Features available in the navigation bar are explained as follows: 

 - **Navigation switcher**: Allows seamless navigation to other pages: 
   - **Home**: The default view that you see when logging into Experience Manager Guides.
   - **Editor**: An easy-to-use web-based Editor that allows you to create and manage structured documents in AEM Guides. [Get to know the Editor interface.](./web-editor.md) 
   - **Map console**: Provides you a dedicated workspace to handle all aspects of map management and publishing.   
 - **AI Assistant**: An [AI Assistant tool](./ai-assistant-right-panel.md) that helps you make your authoring smarter and faster. 
 - **Customize overview section**: Allows you to hide or show the widgets in the Overview layer. 
 - **Profile in use**: Displays Global profile or Folder profile (name) that is currently being used.  
 - **Adjust view**: Allows you to expand or minimize the current workspace. Expanding the view hides the header bar, while minimizing it restores the header bar to its original position 

## Left panel 

The left panel is a persistent panel. You can expand or collapse it by selecting the Expand Sidebar icon placed at the bottom-left corner of the interface. 

![](images/aem-home-left-panel.png){width="800" align="left"}

The left panel provides a quick access to the following: 

- [Overview](#overview)
- [Map Collections](#map-collections) 
- [Bulk Publish](#bulk-publish)
- [Publish Queue](#publish-queue)
- [User Preferences](#user-preferences)  

>[!NOTE]
>
> In addition, if your administrator has configured Workfront integration in the system, then a **Workfront** option is also shown in the Left panel. Learn about [working with Workfront Integration](./workfront-integration.md)
 

### Overview 

The Overview layer acts like a personalized dashboard and provides you quick access to essential items for enhanced productivity. It features a Widget section where the following widgets are displayed: 

 - **Recent Files**: The widget provides you a snapshot of recently-used files (a list of files that you accessed in the Editor) along with the key file details including Title, File name, File type, File path, and Accessed on dates. 

    The following options are available when you hover over a file:  

   - **Open in editor**: Allows you to open the selected file in the Editor. You can also open it by selecting the file title. 
   - **Pin**: Allows you to pin the selected file in the widget 
   - **Remove**: Allows you to remove the selected file from the Recent files widget. 

    **Create new file from the New File drop-down menu**  

    The **New file** drop-down menu allows you to create a topic or DITA Map right from the **Recent files** widget section. On successful file creation, you will be redirected to the Editor interface where you can work upon the file. 

 - **Collections**: If you work on a set of files or folders, you can add them to this widget to access them quickly. Once added, you can view the files by Titles along with their respective Owner names and Created on dates.  As you click on the column dropdown, you can view the options to sort and resize the column.  

    The following options are available when you hover over a collection:
     - **Rename**: Allows you to rename the selected collection.  
     - **Delete**: Allows you to delete the selected collection. 
     - **View in Assets UI**: Allows you to open the selected collection in the Assets UI. 

     You can open a collection by selecting the Collection title. The following options are available when you hover a Collection file:
      - **Open in editor**: Allows you to open the selected file in the Editor. You can also open it by selecting the file title. 
      - **Open in map console**: Allows you to open the selected map file in the map console. (Available only for a DITA map file).
      - **Add to collections**: Allows you to add the selected file to a new or existing collection.
      - **Remove from collections**: Allows you to remove the selected file from the collections list.
      - **View in Assets UI**: Allows you to locate the selected file in Assets UI. 

     **Create new collection from the New collection drop-down menu**  

    The **New collection** drop-down menu allows you to create a new collection and add it to the **Collections** widget.

> [!NOTE]
>
> The widgets also provide you with options to sort and resize columns for a customized view. To view these options, click on the column header and the options would display in a list.  

### Map collections 

Experience Manager Guides provides you the ability to organize your content for publishing by using a dashboard called **Map collections**. To use this feature, select **Map collections** from the Left panel. It takes you to the Map collections folder in the **Assets UI** where you can [use map collection for output generation.](./generate-output-use-map-collection-output-generation.md)  

### Bulk publish 

The Bulk Activation feature allows you to quickly and easily activate your content from authoring to publishing instance. To use this feature, select **Bulk publish** from the Left panel. It takes you to the Bulk Activation Collections folder in the Assets UI where you can manage as well as [create a bulk activation map collection.](./conf-bulk-activation-publish-map-collection.md) 

### Publish queue 

When you have a large set of publishing tasks running on your system, it becomes practically impossible to check each DITA map individually to monitor its publishing task. Experience Manager Guides gives the administrators and publishers a unified view of all publishing tasks running in the system.  

To use this feature, select **Publish queue** from the Left panel. It takes you to the Publish dashboard folder in the Assets UI where you can [manage publish tasks using the publish dashboard](./generate-output-publish-dashboard.md). 

### User preferences 

The User preferences are available to all authors. Using the preferences, you can configure the following settings:

 - **General**: The General tab allows you to configure the following settings:

    ![](images/user_preference_editor.png){width="800" align="left"}

     - **Folder profile**: The Folder profile controls various configurations related to conditional attributes, authoring templates, output presets and the Editor configurations. The Global profile is shown by default. In addition, if your administrator has configured folder profiles in the system, then those folder profiles are also shown in the Folder profiles list.     
     - **Base path**: By default, when you access the Experience Manager Guides repository from the Editor, you are shown assets from the /content/dam location. Your working folder would most likely be a few folders inside the /content/dam/ folder. It would take you a few clicks to reach the working folder every time. You can set the Base path to your working folder and the Repository view then shows you the content from that location upfront. This reduces the time to access your working folder. Also, when you insert any reference or media file in your topic, the file browse location starts with the folder set in the Base path.
     - **Select Root Map**: Select a DITA map file to resolve key references or glossary entries. The selected root map takes the highest precedence to resolve key references. For more details, view [Resolve key references](./map-editor-other-features.md). 
     - **Maximum number of recent files**: Use this field, to set a maximum limit on the files that are displayed in the Recent files widget.
     - **Set default map opening behavior**: Here, you can select a default behavior the system will follow while opening a DITA map file. 

 - **Appearance**: The Apperance tab provides you with the options to select the themes for the application and the source view of the content editing area. Use this tab to configure the following settings:

    ![](images/user_preference_editor_appearance.png){width="800" align="left"}
 
     - **View files by**: Select the default way to view the files in the Editor. You can view the list of files by the titles or the filenames from the various panels in the Author view. By default, the files are displayed by title in the Editor.
     - **Application theme**: You can choose from the Light or Dark themes for the application. In the case of the Light theme, the toolbars and panels use a light grey color background. In the case of the Dark theme, the toolbars and panels use a black color background. Select **Use device** theme to allow Experience Manager Guides to select the light and dark themes based on the theme of your device. In all themes, the content editing area is shown in white color background in the Author view.
     - **Source view theme**: You can choose from the Light or Dark themes for the content editing area in source view. In the case of the Light theme, the content editing area uses a light grey color background for the source view while in the case of Dark theme, it uses a black color background. Select **Use device** theme to allow Experience Manager Guides to select the light and dark themes based on the theme of your device.
    - **Always locate files in the repository**: Select this option to show the location of a file in the repository while editing it in the Editor.
     - **Show non-breaking space indicator in the author mode**: Select this option to show an indicator for the non-breaking spaces while editing it in the Editor. It’s enabled by default.





