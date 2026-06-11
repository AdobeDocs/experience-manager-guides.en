---
title: Configure Folder Profiles
description: Learn about how to configure folder profiles when working with the Learning and Training content in Experience Manager Guides.
feature: Authoring
role: Admin
level: Experienced
exl-id: dc26ae48-c953-492c-823a-5f65157b6902
TQID: https://experienceleague.adobe.com/jp7oUSIZlnTfGnx58E9rPn6Tk4zE2lp-oZSTdjblbZ0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
    internal-label: Reports
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
    internal-label: Profiles
  - id: b89a36a9-95de-429b-adde-f901256d8f24
    internal-label: Variables
  - id: f7774ebe-aec9-42b6-97e4-5002acdc712e
    internal-label: Review
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
    internal-label: Map console
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Configure Folder profiles

A folder profile is required to segregate the configurations for different departments or products in your enterprise. For Learning and Training content, you can create and configure a folder-level profile to manage authoring templates, output templates, output presets, and other folder-level settings.

Learn about [Best practices for setting up the folder structure](best-practices-folder-structure.md). 

To get started with the folder profile configuration for Learning and Training content, you need to: 

1. **Create different folders to manage authoring and output templates**: You can create folders for Authors and Publishers working in different departments or products in your enterprise. These folders can be mapped to specific folder profiles, each configured with different authoring and output templates to support department-specific learning course creation and decentralized administration. 

    You can create a new folder from the Repository panel. 

    ![](assets/create-new-folder.png){width="350"}
2. **Create language folders to manage translation**: If you translate content into different languages, you must create folders corresponding to each language. Each of these language folders will contain the content corresponding to that language. 
   
3. **Create a folder to manage Assets**: Similar to folders, you can also create different Assets folders to cater to the needs of different departments. This way, you also ensure that Authors and Publishers have access to the correct CSS configured in their templates, images, and other assets.  

    ![](assets/configure-assets-folder.png){width="350"}
4. [Create a folder profile](../cs-install-guide/conf-folder-level.md#create-and-configure-a-folder-level-profile) to map different folders. 
5. **Select the Folder profile to be configured**: Once the folder profile is created, you need to select the Folder profile on the [User Preferences](../user-guide/intro-home-page.md#user-preferences) page to ensure that Authors and Publishers have access to the correct templates.

    ![](assets/folder-profile.png){width="650"}

6. **Configure Folder profile settings**: For Learning and Training content, the following settings can be configured at a folder level: 
    - [General](#general)
    - [Panels](#configure-panels) 
    - [Content templates](#configure-content-templates)
    - [Output presets](#configure-output-presets)
    - [HTML editor](#html-editor-settings) 
    - [Publish profiles](#manage-publish-profiles) 

 To access these settings, switch to the Editor view and select **Workspace settings** from the **Options** menu as shown below: 

 ![](assets/access-editor-settings.png)

## General

In the General tab, you can configure the following settings that are specific to the Product Training and Learning content feature:

![](assets/lc-config-settings-general.png){width="350"}

- **Learning content**: Use the **Enable Learning content** toggle to enable or disable the feature at a folder-profile level. 
- **HTML editor**: This setting allows you to configure the Editor for HTML-based authoring. Key configuration options present in this setting are as follows: 

    - **Hide inline styling**: Enable this option to prevent Authors from applying inline formatting to the course content. When enabled, all the inline styling options like Fonts, Border, Layout, Background, and Columns present in the right panel of the Editor remain hidden for Authors. However, Authors can still use the global class-based styling options available in the **Styles** panel. This helps maintain consistency with your organization's style guidelines. 
    - **Hide Source view for Authors**: Enable this option to restrict access to the HTML source code. This is useful when you want to simplify the editing experience or avoid accidental changes to the underlying code. 

## Configure panels 

This setting controls the panels that are shown in the left and right panels of the **Editor** and **Map console** in Experience Manager Guides. You can toggle the button to show or hide the desired panel.  

For Learning and Training content, ensure that only the following features are enabled for the Editor and Map console.  

![](assets/panels-settings.png){width="350"}


### Editor 

**Left panel** 

- **Collections**: Enables you to organize and save frequently used files, or quickly access shared files. 
- **Explorer**: Allows you to view and access all your maps, topics, images, and other assets stored in the content repository. 
- **Course manager**: Provides a dedicated workspace for creating and managing courses.  
- **Map**: Provides a map view of the currently opened map file.
- **Outline**: Displays the structural hierarchy of the currently opened topic or map, allowing quick navigation and element‑level access.
- **Workfront**: Provides access to robust project management features on top of Experience Manager Guides core CCMS capabilities.
- **Reusable content**: Allows you to manage and insert reusable elements or topics to ensure consistency and reduce duplication across content.
- **Glossary**: Enables you to create and manage glossary terms and include them across topics to maintain consistent terminology.
- **Snippets**: Allow you to create and reuse small content fragments across various topics in your Learning courses. 
- **Conditions**: Allows you to configure conditional attributes at a global and folder level. 
- **Templates**: Allows you to create and manage the course templates. 
- **Citations**: Enables you to add and manage citations into content using supported citation styles.
- **Language variables**: Enables you to define language variables for published output. 
- **Variables**: Allows you to create and manage variables to use in your learning content. 
- **Output templates**: Enables you to create and manage output templates to generate output in various formats.  
- **Find and replace**: Provides options to search for and replace text across files in a map or a folder within your repository.  
- **Data sources**: Allows you to connect external data sources and reuse data within your content.
- **Review**: Allows you to create and manage review workflows in Experience Manager Guides.
- **System reports**: Allows you to create and manage reports. 

**Right panel**

- **Content properties**: Contains information about the type and attributes of the currently selected element in the Editor. 
- **File properties**: Allows you to view and manage the properties of the selected file.  
- **Styles**: Display the global class-based styling options for use in your learning content. 
- **Filters**: Enables you to filter content based on applied conditions in the Preview mode of a topic. 

### Map console 

**Left panel** 

- **Presets**: Enables you to configure output presets for publishing the Learning course. 
- **Translation**: Provides options to translate your content into multiple languages. 
- **Reports**: Allows you to generate and manage reports to get a useful insight into the overall health of the content in your course. 
- **Condition presets**: Provides options to configure condition-based output presets for different audiences, departments, and more. 

**Right panel**

- **Filters**: Allows you to use filters when working with reports and translation.  

## Configure content templates 

>[!NOTE]
>
> This setting is available only when the learning content feature is enabled in the **Workspace settings** > **General**. 

This setting allows you to manage the authoring and publishing templates present in the [Left panel in the Editor](../user-guide/web-editor-left-panel.md). You can add, remove, or reorder authoring and output templates, which will then be accessible to Authors and Publishers. 

![](assets/templates-settings.png){width="350"}

The Authoring templates are available in four categories – Learning course, Learning content, Quiz, and Question bank. If there are any predefined templates configured in your instance, they will be displayed by default. 

![](assets/templates-list.png){width="350"}

### Add templates

Perform the following steps to add a new template: 

1. Navigate to the template category where you want to add a template and select **Add**.  
2. In the Select path dialog, select the desired template. 
3. Choose **Select**.  

    ![](assets/add-templates.png){width="350"}

The template is added in the respective category in the Settings panel. 

Similarly, you can add the other Authoring and Output templates. Once added, these templates are made available to Authors and Publishers in their respective course dialogs. For example, the Learning course template added by the Administrator will be available to Authors when they create a new course.  

![](assets/templates-added-course.png){width="350"}

### Work with new authoring and output templates 

To use a different template than those shown in the **Select Path** dialog, create a custom authoring or output template. 

**Create new authoring templates**

To use a different map or topic template, create a new authoring template from the Templates panel in the Editor. Use map templates to create Learning courses and topic templates for Learning content, Quiz, or Learning summary. 

For details, view [Create customized templates from the Editor](../user-guide/create-maps-customized-templates.md). 

![](assets/authoring-templates-editor.png){width="350"}

**Create new output templates**

Perform the following steps to create a new output template for the Learning and Training content: 

1. From the left panel in the Editor, select **More** > **Output templates**.
    
    The Output templates panel is displayed. 

    ![](assets/output-templates-editor.png){width="350" height=""}
2. In the Output templates panel, select (+) to create a new output template. 

    ![](assets/create-new-output-template.png){width="350"}
3. Select an Output template from the dropdown menu. 


    ![](assets/output-template-types.png){width="650"}
4. Based on the selected Output template type, a dialog is displayed where you can create a new template based on the available templates.  

     ![](assets/new-scorm-template-dialog.png){width="350"}

5. Select **Create**. 

    A new Output template is created. 

6. To access and add the Output template for Publishers, navigate to **Settings** > **Templates** > **Output templates** and select **Add**.

    ![](assets/add-output-template-settings-panel.png){width="350"}

    The output template is displayed in the Select path dialog.  
7. Select the template and choose **Confirm**. 

    ![](assets/select-scorm-template-dialog.png){width="350"}

    The selected output template is now added to the Settings panel.  

    ![](assets/scorm-template-added.png){width="350"}

### Configure page layouts for SCORM output templates

SCORM output templates allow you to assign different page layouts to different topic types within a course. This enables you to customize the presentation of lessons, quizzes, overview pages, and other content types in the generated SCORM package.

For example, a lesson page can use a layout that includes a header, content area, and footer, while a quiz page can use a simplified layout without a footer. You can also create dedicated layouts for overview pages or any other topic type and map them accordingly.

Layout assignments are configured at the **Output Template** level. Any SCORM preset that uses the configured output template will apply the selected layout mappings when generating courses.
Follow the steps below to configure the page layout for the templates:

1. Navigate to **Output templates** and open the required **SCORM output template**.

2. Select the **Settings** tab.

3. In the **Page layouts** window, locate the available topic types.

    ![](assets/page-layout-scorm.png){width="650"}

4. For each topic type, select the page layout to be used during course generation.

   **Example:**
   - **Default Page Layout**: Lesson
   - **Quiz**: Quiz
   - **Overview**: Lesson

5. To use a new layout, create the required page layout within the output template using the **New Page Layout** option from the context menu from the **Output templates** panel.

    ![](assets/new-page-layout-scorm.png){width="650"}

6. Return to the **Settings** tab and assign the newly created layout to the appropriate topic type.

7. Save the Page Layout for output template using the Save icon on the right corner of Tab bar .


When a course is generated using a SCORM preset that uses the configured output template, each topic is rendered using the layout assigned to its topic type. This allows different content types within the same course to have customized page structures and visual presentation.    

### Remove or reorder templates 

Once added, you can remove or reorder the templates from the Settings panel.  

To remove a template, select the **Remove** icon next to it.    

![](assets/remove-teamplates.png){width="350"}

You can also define the order in which the templates present within a category are displayed. To change the display order of the templates, select the dotted bars and drag a template to the desired position.  

![](assets/reorder-templates.png){width="350"}


## Configure Output presets 

>[!NOTE]
>
> This setting is available only when the learning content feature is enabled in the **Workspace settings** > **General**. 

The Output presets tab allows you to define which output formats are available for publishing a course. It contains two sections: **Allowed output preset types** and **Common output presets**.  

![](assets/configure-course-output-presets.png){width="350"}

- **Allowed output preset types**: This section lists all output presets supported in the Experience Manager Guides instance. For course publishing, only **SCORM** and **PDF** formats are applicable. You can select one or both options. The selected presets will be available to Publishers when generating course output. 

    ![](assets/allowed-output-presets.png){width="350"}

- **Common output presets**: This section displays the output presets commonly created and added by Publishers to a specific folder profile. You can also remove any preset that is no longer needed. 

    ![](assets/common-output-presets.png){width="350"}

## Manage Publish profiles 

This section allows you to view, create, and manage publish profiles used for publishing courses to SCORM Cloud or Adobe Learning Manager (ALM). Each profile defines the connection settings and configuration details required to publish a learning course to a selected publishing server.

You can create multiple profiles to publish content to different SCORM Cloud accounts or ALM instances, providing flexibility and control over your publishing workflow.

To configure a publish profile, select the desired publish server (SCORM Cloud or Adobe Learning Manager) and provide the required connection details. For SCORM Cloud, enter the server information along with the Client ID and Client Secret of the associated SCORM Cloud application. For Adobe Learning Manager, provide the corresponding server and authentication details required for your ALM environment. 

![](assets/configure-publish-profiles.png){width="350"}
