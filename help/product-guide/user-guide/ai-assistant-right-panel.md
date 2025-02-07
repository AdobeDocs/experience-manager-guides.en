---
title: Use the AI Assistant to author documents smartly `
description: Learn how to Use the AI Assistant to author documents with smart efficiency.
exl-id: 47d37323-20bf-4444-a2c9-41c44b2c8daf
---
# Authoring assistant to author documents smartly

Adobe Experience Manager Guides provides an AI Assistant tool that helps you make your authoring smarter and faster. Using this tool, view the smart suggestions to reuse the content from the existing content repository. Use the text prompt feature to provide a prompt and change the content as per your requirements. Use the AI Assistant to smartly convert a paragraph to a list. You can create a short description for the current topic based on the selected content. This feature also helps you to easily improve and translate the selected content.

>[!NOTE]
>
> This Authoring feature is available for DITA topics only, and can be accessed from the Editor interface only. On the Home page and Map console, only the **Help** panel is displayed. 

After selecting the text in a topic, you can choose to perform any of the AI Assistant actions:

![ai assistant](./images/ai-assistant-panel.png)

## Suggest reusable content 


Use the **Suggest reusable content** ![ai suggest reusable content icon ](./images/ai-suggest-reusable-content-icon.svg) feature to author content consistently and accurately. You can select the content, and Experience Manager Guides provides suggestions about how to reuse the existing content in your repository. 
Learn more about using [AI-powered smart suggestions to author content](authoring-ai-based-smart-suggestions.md).


## Use text prompt 

A text prompt is an instruction, question, or statement that guides the AI Assistant in generating a specific response.

You can use a text prompt to change the content. For example, you can select the content of your current topic and use the prompt *Make the text more concise*. Similarly, you can use a text prompt to add an attribute to the tag used in the selected content. 

1. Select the text for which you want to use the text prompt.
1. Select **Use text prompt** ![ai use text prompt icon](./images/ai-use-text-prompt.svg)from the **Authoring**  panel.
1. Give a prompt in one of the following ways:

    - Choose a prompt from the suggested prompts. 
    - Revise or edit a suggested prompt to create a custom prompt as per your requirements.

        >[!NOTE]
        >
        > The suggested prompts are configured in the `ui_config.json` by your administrator. 

    - Enter your prompt in the text box. 
  

1. Select **Regenerate** ![Regenerate icon](./images/refresh-icon.svg) for another response or output based on your prompt, like the AI tools.

1. (Optional) Select **Expand** ![expandicon](./images/expand-icon.svg) to open the **Use text prompt** editor. It displays the current and the generated content. You can edit the source layout content and check the preview.
    
    ![ai assistant text prompt editor](./images/text-prompt.png)


    >[!NOTE]
    >
    > The responses are generated based on the selected content.



1. You can also edit the prompt in the editor and regenerate the response. For example, you can change the prompt to make the text more concise to approximately 40 words.
 
1. You can verify the source of the generated content and edit it if required.

1. Select **Accept** to replace the selected content in the topic with the generated content.  
1. **Cancel**: Cancels the text prompt action. Returns to the Authoring panel. 

    >[!NOTE]
    >
    > Selecting the **Dismiss** icon in the Authoring panel returns you to to the initial state of the AI Assistant.

## Improve content 

Use the **Improve content** feature to improve the quality of the selected content of the current topic. You can select the content to check spelling, language, and grammatical structure, and suggest a better version of the content. It also enhances the quality of sentences.

1. Select the content. 
1. Select **Improve content** ![ai improve content icon](./images/ai-improve-icon.svg) to find the suggestions for the improved content. 
1. Select **Regenerate** for another suggestion of improved content. 

1. (Optional) Select **Expand** to open the improved content editor. It displays the current and generated content. You can edit the content in the source layout and also check the preview.



    ![ai assistant improve content editor](./images/ai-assisstant-improve-content.png)

Accept the suggestion, edit the response in the source view before accepting, regenerate for a different response, or cancel the action to go back to the previous state.





## Create shortdesc 

Create a short description for the topic based on the selected content in around 30-50 words. The short description helps users search for and find relevant content. 
For example, you can list the system requirements and generate a short description accordingly. 
 


1. Select the content. 
1. Select **Create shortdesc** ![ai create short description icon](./images/ai-create-shortdesc-icon.svg) to create a short description for the current topic. 
1. Select **Accept** to create a new short description if the short description isn't already present. If a short description exists, you need to confirm it before replacing it with the new short description.

You can also perform the following actions: 

- Select **Regenerate** to generate another short description for your topic, like the AI tools.
- Select **Expand** to open the **Create shortdesc** editor. 

    ![ai assistant create short description editor](./images/ai-assistant-create-short-desc.png)




## Itemize content 

This feature intelligently converts a selected paragraph into a list.  It analyzes the content and creates a logical list of items. You don't have to manually create the items. For example, if you have a paragraph detailing the steps to create a user account, the tool can transform this into a step-by-step list, eliminating the need to manually create items one by one.

![ai assistant itemize content icon](./images/ai-assisstant-itemise-content.png)



1. Select the content. 
1. Select **Itemize content** ![ai itemize content icon](./images/ai-itemize-icon.svg) to convert the selected content into a list. 
The Authoring tool in the AI Assistant panel converts the content smartly into a list of items. 
1. (Optional) Select **Expand** to open the **Itemize content** editor. 
1. Once your list is ready, accept the changes in the generated content. The generated content then replaces the selected content.  



## Translate content 

Use this intelligent feature to translate the selected content to the target language, making it highly useful when adding notes in different languages. For example, you can add content in English and quickly translate it into Arabic.

Perform the following steps to translate the content:

1. Select the content that you want to translate.
1. Select **Translate content** ![ai translate content icon](./images/ai-translate-content-icon.svg) from the **Authoring** panel.
1. Select the target language from the dropdown. The translated content appears in the AI Assistant panel.

1. (Optional) Select **Expand** to open the **Translate content** editor. 
1. You can also select another language from the dropdown menu and regenerate the content in the chosen language. For example, if you select French and then select **Regenerate**, the content is translated into French.

![ai assistant translate content](./images/ai-assisstant-translate-content.png)
