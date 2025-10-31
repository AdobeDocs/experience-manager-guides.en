---
title: Repository in Home page 
description: Get to know the Repository in the Home page. Learn about Repository interface and features in Adobe Experience Manager Guides on Home page.
feature: Authoring,
role: User

---
# Repository 

The Repository feature serves as a centralized place designed to enhance the discoverability and management of folders and files. It offers a comprehensive view of all repository contents while enabling advanced customization for improved information access. 

This unified interface streamlines multiple functions, including creating new maps or folders, uploading assets, editing files, and executing precise searches with robust filtering options, thereby ensuring efficiency and ease of use.


## Know the Repository interface

It consists of the options as listed below.

![](images/repository-view-home.png){align="left"}

### Tab bar

The Tab Bar, located at the top of the Repository interface, provides quick access to essential actions as listed.

![](images/tab-bar-repository-view.png){align="left"}


- **Folder navigation panel**: Displays a hierarchical, tree-like structure of folders within the Repository, enabling seamless navigation. This panel shows folder-level information only. You can select the icon highlighted in the image below to show and hide this panel. When a folder is selected from here, its contents, files and, sub-folders are displayed in the central space.

    ![](images/folder-navigation-panel.png){align="left"}

- **Breadcrumbs**: These offers navigation through the folders. You can use the breadcrumbs to traverse to the required location by directly selecting the required location. 

    ![](images/breadcrumbs.png){align="left"}

- **Refresh**: Updates the Repository view to reflect the latest changes.
- **Upload Assets**: Allows you to upload assets directly to the selected folder.
- **New**: Enables the creation of new topics, maps, and folders within the Repository.
- **AI Assistant**: A powerful, AI-driven tool designed to enhance your productivity through smart help features.
- **More actions**: Provides access to Workspace settings and Assets
- **Expand view**: Allows you to expand the page view using the **Expand** icon.

### Repository view

The Repository view serves as the central space where all folders and files within the repository are displayed. It offers customization options and additional features to enhance usability and visibility as listed below:

- **Customise**: You can modify the columns displayed by using the **Customise** option located at the top-right corner of the Repository view that provides a toggle control for the available fields. The Name or Title columns are mandatory and both cannot be disabled together. Other fields, such as File Type, UUID, Document State, Locked By, Created On, and Modified On, can be enabled or disabled as needed. You can also rearrange them by dragging and dropping.

    ![](images/customize-repo-view.png){align="left"}

- **Column resizing**: Columns can be resized by selecting the dropdown menu on the respective field label.

- **Sorting**: The Name, Title, Created on and Last modified columns support sorting in ascending or descending order, accessible via the dropdown on the field label.

- **Editing the file**: 

    - You can select one or multiple files from the Repository view for editing.
    - After selecting the desired files using the checkbox, the **Edit** option becomes available in the top-right corner of the Repository View.
    - Clicking Edit opens the selected file(s) in the Editor Interface, where you can begin editing immediately.

        ![](images/edit-repo-view.png){align="left"}

- **Options menu for folders**: You can perform the following actions using the Options menu available for a *folder* in the Repository view:

    ![](images/options-folder-repo.png){align="left"}

    - **New**: Create a new DITA topic, DITA map, or a folder. 
    - **Upload Assets**: Upload a file from your local system to the selected folder in repository.
    - **Add to collections**: Adds the selected folder to favorites. You can choose to add it to an existing or new collection.
    - **Reprocess assets**: Triggers the processing of all the newly created and unprocessed assets.

- **Options menu for files**: Get access to different options in the Options menu on the file. Some common options available for files are:   

        ![](images/options-file-repo.png){align="left"}

    - **Edit**: Open the file for editing.
    - **Duplicate**: Use this option to create a duplicate or a copy of the selected file.
    - **Lock**: Get a lock on the selected file for editing. 
    - **Preview**: Get a quick preview of the file (.dita, .xml, audio, video, or image) without opening it.
    - **Rename**: Use this option to rename the selected file.
    - **Move to**: Use this option to move the selected file to another folder. 
    - **Delete**: Use this option to delete the selected file.
    - **Copy**: Copies the UUID or complete path of the file
    - **Add to**: Choose to add to collections or Reusable content.
    - **Properties**: Use this to open the properties page of the selected file.
    - **Edit in Oxygen**: Select this option to edit the selected file in the Oxygen connector plugin.
    
    >[!NOTE] 
    >
    >Contact your customer success team to get this feature enabled in the environment. This isn't enabled as a part of the out-of-the-box support. For more details, view the [Configure the option to edit in Oxygen ](../cs-install-guide/conf-edit-in-oxygen.md) section in the Installation and Configuration Guide.

    - **Download as PDF**: Use the option to generate the PDF output and download it.
    - **Open in map dashboard**: In case the selected file is a DITA map, then this option opens the map dashboard.
    - **Open in map console**: In case the selected file is a DITA map, then this option opens the map console.  

### Search and filtering experience

The Search panel in the Repository view helps in searching the required files from the Repository primarily on the basis of **File title**, **File name** and **Content**.
 
Select the **Filter Search** \(![Search filter icon](images/filter-search-icon.svg)\) icon to open the Filter panel on the right.

![](images/Search-filters-repo.png){align="left"}

You have the following options to filter the files and to narrow down your search Repository:

- **Search in**: Select the path where you want to search the files present in the Repository. 

- **File type**: You can look for all **DITA Topics**,  **DITA Maps**, **Ditaval Files**,  **Image Files**, **Multimedia**, **Documents**, and **JSON**.

- **Locked by**: Displays a list of users. The list is paginated and loads asynchronously, showing a limited set of users at a time and fetching more as you scroll or navigate. This improves loading speed and overall performance, especially when working with a large number of users.

- **Last modified**: Filter content based on modification date. Select a date range from the calendar or choose one of the following time frame options: 
    - In last week
    - In last month
    - In last year

You can also reset the data using the Reset button

- **Tags**: Filter content based on tags. 

- **DITA element**: Filter content based on various DITA elements.

After adding all the required filters, select **Apply** located at the bottom-left corner of the Filters panel.
Your search results will then be customized according to the selected filter criteria.

**Show in search panel**

The **Show in search panel** option becomes available after performing a search in the Repository view.This feature allows you to display all search results directly in the Editor Interface without switching manually from the left navigation panel.

Your search results from the Repository View are mirrored in the Search Panel within the Editor Interface for seamless access. For more details view, [Search panel](./explorer-editor.md).

![](images/search-panel-repo.png){align="left"}

