---
title: Configure Other Settings
description: Learn about how to configure folders, assets folders, variables, snippets, conditions, and more for different departments in Experience Manager Guides.  
feature: Authoring 
role: Admin
level: Experienced
---
# Configure other settings 

As an Administrator, you can also configure the following settings for the Learning course Authors and Publishers: 

- **Folder settings**
    - **Create different folders**: You can create folders for Authors and Publishers working in different departments or products in your enterprise. These folders can be mapped to specific folder profiles, each configured with different authoring and output templates to support department-specific learning course creation and decentralized administration. 

        You can create a new folder from the Repository panel. 

        ![](assets/create-new-folder.png){width="350" align="left"}
    - **Create language folders**: If you translate content into different languages, you must create folders corresponding to each language. Each of these language folders will contain the content corresponding to that language. 

        For details, view [Best practices for content translation](../user-guide/translation-first-time.md). 
    - **Assets management**: Similar to folders, you can also create different Assets folders to cater to the needs of different departments. This way, you also ensure that Authors and Publishers have access to the correct CSS configured in their templates, images, and other assets.  

        ![](assets/configure-assets-folder.png){width="350" align="left"}
- **Snippets**: You can configure snippets at a folder level to ensure Authors have access to the correct Snippets. Only Administrators can create Snippets in Experience Manager Guides, which can then be used by Authors in the Editor.  

    You can access Snippets from the left panel in the Editor.  

    ![](assets/create-snippets.png){width="350" align="left"}
- **Conditions**: As an Administrator, you can configure standard DITA-supported conditional attributes at the global or folder levels. Authors then use configured conditions by simply dragging and dropping the desired condition onto their content.  

    You can access Conditions from the left panel in the Editor.  

    ![](assets/create-conditions.png){width="350" align="left"}
- **Variables**: You can define variables to make your content more portable, consistent, and easier to update. During output generation, variables are replaced with the values from the selected variable set, allowing you to produce customized outputs efficiently. 

    For details, view [Create a new variable](../native-pdf/native-pdf-variables.md#create-a-new-variable)  

- **Editor toolbar**: You can customize the Editor toolbar as per your organizational needs. For example, you may prefer to change the name of a toolbar button, change its location, and so on.  

    For details, view [Configure and customize the XML Editor](../cs-install-guide/conf-folder-level.md#configure-and-customize-the-xml-editor-id2065g300o5z). 
