---
title: AI-powered Smart Suggestions to author content
description: Learn how to view and utilize AI-powered Smart Suggestions in the Web Editor.
exl-id: 30c85d46-61ba-486c-979c-1a2ed95f5a32
---
# AI-powered Smart Suggestions to author content

Experience Manager Guides provides the **Smart Suggestions** feature that helps you create consistent and accurate content.  

While you author content, the **Smart Suggestions** feature can search using AI and show the existing content that is semantically similar to your content. You can then choose the best matching content you want to include in your current topic as a reference.

This helps you reuse existing content from your documentation repository and create consistent content. For example, you are making a document containing information about **Adobe Firefly**, including a paragraph about **Adobe**. In that case, you can quickly view and add the content reference from another topic, like **Adobe Photoshop**, which includes the same paragraph.





When you open a topic in the Web Editor, the **Smart Suggestions** panel appears on the right. 

>[!NOTE]
>
> Your administrator must configure the **Smart Suggestions** feature. For more details, view the [Configure the AI-powered smart suggestions for authoring](/help/product-guide/cs-install-guide/conf-smart-suggestions.md) section in the Installation and Configuration Guide for Cloud Services. 

![Smart suggestions panel](images/smart-suggestions-panel.png){width="300" align="left"}

*View the **Smart Suggestions** panel.*

Perform the following steps to view the smart suggestions for adding appropriate content references to your topic:

1. Select **Smart Suggestions** ![smart suggestions icon](images/smart-suggestions-icon.svg) to open the panel.



    >[!NOTE]
    >
    > In the [global or folder-level profiles](/help/product-guide/cs-install-guide/conf-folder-level.md#conf-ai-smart-suggestions), your administrator needs to define the files or folders to index for smart suggestions, the minimum number of characters you need to enter to view the suggestions, and the maximum number of suggestions you can view in the list.

  1. Type in the content in your topic to view the related suggestions. Ensure that the content's character length exceeds what your administrator has set in the folder profile for the content suggestions to appear.

  1. Select **Suggestions for the current tag** ![smart suggestions current tag icon](images/smart-suggestions-current-tag-icon.svg) to view the authoring suggestions for the current tag where you place your mouse pointer.  The suggestions to view and add content references from the indexed files are displayed based on the content in the current tag.
  
      Keyboard shortcut: **Windows** (*Ctrl* + *K*),  **macOS** (*Command* + *K*)
  1. Select **Suggestions for the complete document**  ![smart suggestions complete document icon](images/smart-suggestions-complete-document-icon.svg) to view the suggestions based on the content present in the complete document.  The smart suggestions![smart suggestions icon](images/smart-suggestions-complete-document-icon.svg) icon is displayed next to the content where a suitable match is found. 

      Keyboard shortcut: **Windows** ( *Ctrl* + *Shift* +  *K* ),  **macOS** (*Command* + *Shift* + *K* )

        >[!NOTE]
        >
        > You can only view the suggestions for the current viewport (the content visible on the screen). To view suggestions for any other content in the document, scroll up or down to display it in the viewport and then select the ![smart suggestions icon](images/smart-suggestions-complete-document-icon.svg) icon .
   
   1. Select the **Smart Suggestions** ![smart suggestions icon](images/smart-suggestions-complete-document-icon.svg) icon near the tags you have added to your document to view the smart suggestions. 
  1. You can view the smart suggestions  in the **Content Reuse** suggestions box.  Experience Manager Guides provides suggestions for exactly matching content and content with the same meaning. For example, you can search for the topic that contains the exact version number, like "release version 2023.03.12". You can also search for "Adobe is headquartered in San Jose, California," and find similar content like "San Jose has the quarters of many software companies like Adobe."
  1. Select **Content Information** ![Content Information](images/smart-suggestions-content-info-icon.svg) to view the details.
        ![Content information panel](images/smart-suggestions-content-information.png){width="300" align="left"}

        *View the detailed information about the content reference.*

        1. The title of the topic that contains the content reference is displayed as a hyperlink. 
        1. The path of the file that contains the content reference.
        1. The type of reference where the content is referred.
        1. The names of DITA files where the topic is referred to are displayed as hyperlinks.
1. Select **Suggested content preview** ![smart suggestions preview icon](images/smart-suggestions-preview-icon.svg) to compare the current content with the suggested content. This helps you compare the differences and determine if you want to add the content reference for the suggested content and make it consistent or retain your current content.

     ![Suggested content preview](images/smart-suggestions-suggested-content-preview.png){width="800" align="left"}

    *Preview the comparison between the current content and the suggested content.*
 
1. Click **Accept** to add the suggested content reference in the **Suggested content preview** dialog box.
1. You can also select **Accept** or **Decline** in the **Content Reuse** suggestions box for the appropriate recommendations.

   
This intelligent feature is handy and minimizes the effort of manual content searching, allowing you to concentrate more on generating new content. It also facilitates better team collaboration and helps maintain consistency in the content created by various authors.

>[!NOTE]
>
>Smart suggestions don’t retain your data beyond the current session. For responses, smart suggestions rely solely upon the index created on the content residing within your internal database. External AI tools are not used, ensuring your data remains within the system.
