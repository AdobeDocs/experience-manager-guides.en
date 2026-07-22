---
title: Use the AI Assistant to author documents smartly `
description: Learn how to Use the AI Assistant to search and author documents smartly in Adobe Experience Manager Guides.
---

# Guides AI: Smart tagging capability

>[!NOTE]
>
> Guides AI is available in Experience Manager Guides as a Cloud Service starting with 2026.08.0 release. Contact your Customer Success team to enable this feature.

Adobe Experience Manager Guides continues to make content authoring more intelligent with the introduction of **Guides AI** a new conversational assistant integrated directly into the Editor. Currently it introduces the **Smart Tagging** skill, powered by **Adobe CX Enterprise Coworker**, making it easier to organize and manage content through AI-assisted tag recommendations.

## Smart Tagging: AI-powered metadata recommendations

Smart Tagging analyzes the content of your topics or DITA maps and recommends relevant metadata tags based on your organization's existing taxonomy. Instead of manually identifying and applying tags, you can ask Guides AI to generate recommendations, review them, and apply only the
ones you want.

The recommendations are generated using your configured AEM taxonomy, ensuring that suggested tags remain consistent with your organization's metadata strategy.

## Guides AI Panel

The Guides AI panel provides all the tools you need to generate, review, and apply AI-recommended tags. 

![Guides AI panel](images/guides-ai-panel.png)

The following components help you add files, configure tag recommendations, and manage your Smart Tagging workflow: 

- **(A)** Converstion history: View and reopen previous conversations to review earlier tag recommendations and actions.
- **(B)** New chat: Start a new tagging session for a different topic, map, or set of files.
- **(C)** Tag namespace: Select the taxonomy namespaces from which Guides AI should generate tag recommendations. Only tags from the selected namespaces are considered.
- **(D)** Response area: Review AI-generated tag recommendations and choose to accept, reject, or modify them before applying the tags.
- **(E)** Prompt space: Enter a natural language request to generate tag recommendations for the selected content.
- **(F)** Atatch files or add context: Add topics, DITA maps, or external files from your local system to provide the content that Guides AI should analyze for tag recommendations.
- **(G)** Model selected: Displays the AI model that will be used to analyze the content and generate tag recommendations.
- **(H)** Send: Submit your prompt and attached content to generate AI-powered tag recommendations.

## How smart tagging works with Guides AI

Perform the following steps to launch Guides AI: 

1. Login to Experience Manager Guides.
1. On the Home page, select **Guides AI** from the top. Ensure that the Guides AI feature is enabled by your administrator. 
1.  Add the content you want to analyze by:
    -   Mentioning the file using \*\*@*\*.
    -   Dragging and dropping a topic or map into the prompt.
    -   Typing **/** to browse and select content from your local device
        or the AEM repository.
1.  Enter a natural language request such as *"Suggest tags for this
    file."*
1.  Guides AI analyzes the content and generates tag recommendations.
1.  Review the suggested tags.
1.  Accept the recommendations to apply them, or dismiss them if they
    are not required.

Because Guides AI understands natural language, your prompt does not
need to match a predefined command exactly. As long as the request
clearly indicates that you want tag suggestions, the Smart Tagging skill
is triggered.

## Review before applying

Guides AI always keeps you in control.

The assistant presents its recommendations for review before making any
changes. After reviewing the proposed tags, you can:

-   Accept all suggested tags and apply them.
-   Remove individual tag suggestions before applying.
-   Clear all suggested tags.
-   Reject the recommendations and continue working without making
    changes.

This review-first workflow ensures that AI recommendations complement
your existing authoring process rather than replacing editorial
judgment.

## Tagging multiple topics in a map

Smart Tagging is not limited to individual topics.

When you select a **DITA map**, Guides AI first prompts you to choose
which topics should be analyzed. This allows you to generate
recommendations only for the topics you want instead of processing the
entire map.

The workflow supports tagging multiple topics in a single operation,
making it significantly easier to apply consistent metadata across
larger documentation sets. Currently, you can select **up to 25 topics**
in a single Smart Tagging request.

## Intelligent recommendations based on existing metadata

Smart Tagging works with your existing taxonomy rather than creating
arbitrary labels.

If a topic already contains the most relevant metadata, Guides AI may
recommend few---or no---additional tags. This helps avoid duplicate or
unnecessary metadata while maintaining consistency across your content
repository.

## Built for future AI skills

Smart Tagging is just the beginning.

Guides AI has been designed as an extensible AI framework for Adobe
Experience Manager Guides. As additional skills become available,
authors will be able to accomplish more content authoring tasks through
simple conversational interactions, further streamlining documentation
workflows and improving productivity.

With Guides AI, Adobe Experience Manager Guides takes another step
toward making technical content creation more intelligent, efficient,
and user-friendly.
