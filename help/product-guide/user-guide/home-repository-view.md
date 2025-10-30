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

**Tab bar**

The Tab Bar, located at the top of the Repository view, provides quick access to essential actions as listed.

![](images/tab-bar-repository-view.png){align="left"}


- **Folder navigation panel**: Displays a hierarchical, tree-like structure of folders within the Repository, enabling seamless navigation. This panel shows folder-level information only. When a folder is selected from here, its contents, files and, sub-folders are displayed in the main view.
It also offers navigation through breadcrumbs as shown below. You can use the breadcrumbs to traverse to the required location directly.

    ![](images/folder-navigation-panel.png){align="left"}

- **Refresh**: Updates the Repository view to reflect the latest changes.
- **Upload Assets**: Allows you to upload assets directly to the selected folder.
- **New**: Enables the creation of new topics, maps, and folders within the Repository.
- **AI Assistant**: A powerful, AI-driven tool designed to enhance your productivity through smart help features.
- **More actions**: Provides access to Workspace settings and Assets
- **Expand view**: Allows you to expand the page view using the **Expand** icon.

**Repository view**

The Repository View serves as the central window where all folders and files within the repository are displayed. This interface offers customization options to enhance usability and visibility:

- **Field customization**: You can modify the fields displayed by using the **Customize** option located at the top-right corner of the central window that provides a toggle control for the available fields. The Name and Title fields are mandatory and both cannot be disabled together. Other fields, such as File Type, UUID, Document State, Locked By, Created On, and Modified On, can be enabled or disabled as needed.

    ![](images/customize-repo-view.png){align="left"}

- **Column resizing**: Columns can be resized by selecting the dropdown menu on the respective field label.

- **Sorting options**: The Name and Title fields support sorting in ascending or descending order, accessible via the dropdown on the field label.

- **Editing option**: 

    - You can select one or multiple files from the Repository View for editing.
    - After selecting the desired files using the checkbox, the Edit option becomes available in the top-right corner of the Repository View.
    - Clicking Edit opens the selected file(s) in the Editor Interface, where you can begin editing immediately.

        ![](images/edit-repo-view.png){align="left"}

- **Options menu for files and folders**: 
    - For folder: You can also perform many actions using the Options menu available for Folders in the Repository view. You can use New option to add new topics, maps to the folder, Upload assets in the folder, add to collections to the folder, or Reprocess assets.

        ![](images/options-folder-repo.png){align="left"}

    - For files: Get access to different options in the Options menu on the file. Some common options available for both media and DITA files are: Lock, Preview, Duplicate, Move to, Rename, Delete, Add to collections, Copy as properties.   
        ![](images/options-file-repo.png){align="left"}


**Search experience**

The Search panel in the Repository view helps in searching the required files or folders from the Repository primarily on the basis of **File title**, **File name** and **Content**.
 
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

Your search results from the Repository View are mirrored in the Search Panel within the Editor Interface for seamless access. For more details view, [Search panel] 

![](images/search-panel-repo.png){align="left"}

