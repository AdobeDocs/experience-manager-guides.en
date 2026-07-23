---
title: Guides AI for smart tagging capability
description: Learn how to use Guides AI for smart tagging capability for topics and maps in a single operation.
---

# Get started wuth Guides AI

>[!NOTE]
>
> Guides AI is available in Experience Manager Guides as a Cloud Service starting with 2026.08.0 release. Contact your Customer Success team to enable this feature.

Adobe Experience Manager Guides continues to make content authoring more intelligent with the introduction of **Guides AI** a new conversational assistant integrated directly into the Editor. Currently it introduces the **Smart Tagging** skill, powered by **Adobe CX Enterprise Coworker**, making it easier to organize and manage content through AI-assisted tag recommendations.

## Guides AI panel

The Guides AI interface provides all the tools you need to generate, review, and apply AI-recommended tags. 

![Guides AI panel](images/guides-ai-panel.png){width="650"}

The following components help you add files, configure tag recommendations, and manage your Smart Tagging workflow: 

- **(A)** Conversation history: View and reopen previous conversations to review earlier tag recommendations and actions.
- **(B)** New chat: Start a new tagging session for a different topic, map, or set of files.
- **(C)** Tag namespace: Select the taxonomy namespaces from which Guides AI should generate tag recommendations. Only tags from the selected namespaces are considered.
- **(D)** Response space: Review AI-generated tag recommendations and choose to accept, reject, or modify them before applying the tags.
- **(E)** Prompt space: Enter a natural language request to generate tag recommendations for the selected content.
- **(F)** Attach files or add context: Add topics, DITA maps, or external files from your local system to provide the content that Guides AI should analyze for tag recommendations.
- **(G)** Model: Displays the AI model that will be used to analyze the content and generate tag recommendations.
- **(H)** Send: Submit your prompt and attached content to generate AI-powered tag recommendations.

## How smart tagging works

Smart tagging analyzes the content of your topics or maps and recommends relevant metadata tags based on your organization's existing taxonomy. Instead of manually identifying and applying tags, you can ask Guides AI to generate recommendations, review them, and apply only the
ones you want.

The recommendations are generated using your configured AEM taxonomy, ensuring that suggested tags remain consistent with your organization's metadata strategy.

## 	Generate AI tags for a topic

Perform the following steps to use Guides AI for tagging files: 

1. Log in to Experience Manager Guides.
1. On the Home page, select **Guides AI** from the Tab bar. Ensure that the Guides AI feature is enabled by your administrator. 
1. Add the file for which you want to generate tag recommendations using one of the following methods:

    - **Using Suggested prompts**: In the Response area, select the **Suggest tags for the file** prompt. The prompt is automatically added to the Prompt space. Select `[file]`, then choose the file from the Repository or a Collection in the **Select file** dialog.

        ![Access Guides AI panel using suggested prompts](images/suggested-prompts.png){width="650"}

    - **Drag and drop**: Drag and drop a topic or map into the Prompt space, then enter a natural language request, such as *Suggest tags for this file*.

        ![access Guides AI panel by dragging and dropping a topic or map](images/dragging-prompts.png){width="650"}

1. Guides AI analyzes the content and generates tag recommendations.

    ![Interface of Guides AI panel while analysis and thinking](images/guides-ai-analysis.png){width="650"}

1. Review the suggested tags. **Accept** the recommendations to apply them, or **Reject** them if they are not required.

    ![Guides AI panel response after analysis of the content](images/guides-ai-tags-review.png){width="650"}

Guides AI understands natural language, so you can use conversational prompts instead of predefined commands to generate tag recommendations.

## Generate AI tags for multiple topics in a map

Use Smart Tagging to generate tag recommendations for multiple topics in a map in a single operation. After you add a map, Guides AI prompts you to select the topics to analyze, allowing you to generate recommendations only for the required topics. You can select up to **25 topics** in a single request.

To generate tag recommendations for multiple topics in a map:

1. In the **Prompt** space, enter **`/`**.

    ![Guides AI bulk tagging](images/guides-ai-map.png){width="650"} 

2. Select one of the following options:
   - **Add file from device** to add a DITA map from your local system.
   - **Add repository reference** to browse and select a DITA map from the repository.

        ![Guides AI bulk tagging while selecting maps](images/ai-map-selection.png){width="650"}

3. Enter a natural language prompt, such as **"Suggest tags for this map "**, and then select **Send**.
    A message indicates that the selected map contains multiple topics. Select **Select topics** to choose the topics for which you want tag recommendations.

    ![Guides AI bulk tagging while selecting topics](images/ai-select-topics.png){width="650"}

4. In the **Select topics** dialog, select the topics for which you want tag recommendations.   
   The dialog provides:
   - A list of topics in the selected map.
   - A preview pane showing the selected topic and its existing tags.
   - Filter options to display topics **with tags** or **without tags**.

        ![Selecting topics dialog while applying tags](images/ai-select%20dialog.png){width="650"}  
        

5. Select **Confirm**. Guides AI analyzes the selected topics and displays the number of tag recommendations generated for each topic.

6. Select **Preview** to review the AI-generated tag recommendations.

    ![Guides AI bulk tagging process for preview of tags](images/preview-tags.png){width="650"}

7. Review the suggested tags for each topic, and then choose one of the following actions:
   - **Accept all** to apply all suggested tags for all the topics.
   - **Reject all** to discard all suggested tags for all the topics.
   - **Clear all suggestions** to remove all the suggested tags for a specific topic.
   - Select the **X** icon next to a tag to remove an individual tag suggestion.

    ![Guides AI bulk tagging preview dialog](images/preview-dialog.png){width="650"}

8. After you complete the review, Guides AI displays a summary of the tags applied to each topic and any rejected tag recommendations.

    ![Guides AI bulk tagging summary](images/summary.png){width="650"}
