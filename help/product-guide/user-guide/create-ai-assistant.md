---
title: Create topics and maps with AI Assistant
description: Learn how to draft new DITA topics and maps from your notes, specifications, or pasted content with AI Assistant, then review them before saving.
---

# Create content with AI Assistant

The **Create** skill in AI Assistant's Agentic mode helps you generate structured content from notes, specifications, or other source content. It uses templates available in your repository to create drafts, reducing the effort required to structure and author content manually.

You can attach files, specify the topic types, select an existing topic as a reference for tone and style, and choose the destination folder for the generated content. To create topics from files, follow these steps:

1. Log in to Experience Manager Guides.
1. On the Home page, select **AI Assistant** from the Navigation bar. Ensure that your Administrator has enabled the AI Assistant in Agentic mode. 

1. Select **Create** from the AI Assistant panel.

   The starter prompt appears in the prompt box: `Create draft content referring to attached file(s) and having tone of content similar to [file]`

1. Attach your notes, specification, or other files to the prompt using any of the following methods: 

   - **Using shortcut**: Type `/` in the Prompt field, then choose **Add repository reference** to choose the file from the Repository (or **Add files from device** to upload the file from your computer).

   - **Using `Attach files or add context (+)*` icon**: Adds files from your local system. 
   

1. In the prompt, select `[file]`. Select the existing topic whose tone you want the draft to match. You can choose the topic from the repository or from a collection. The topic name replaces `[file]` in the prompt.

   ![Select the file placeholder to choose the topic](images/sample-create.png){width="350"}

1. You can also edit the prompt to name the topic types and the save folder. For example, enter `Create a task topic from these notes in /content/dam/guides/new.` AI Assistant uses a full folder path as entered.

1. Select **Send**.

   AI Assistant analyzes the content and lists each step it completes.

1. Answer any questions that AI Assistant asks.

   Questions can cover the save folder or how to use the attached material. If you don't enter a path, or you describe the folder in words, AI Assistant asks you to confirm where to save.

      ![Select the file placeholder to choose the topic](images/folder-create.png){width="350"}

1. Select **Preview** to review the generated topic.

   Check each draft against your source material and the topic types you asked for.

      ![](images/preview-craete.png)

1. Select one of the following:

   - **Accept** to save the topic to the folder you confirmed
   - **Reject** to discard the changes without saving anything   

      The topic is now available in your repository.

      ![](images/accept-reject-create.png)


<!--## Create a topic from an earlier answer

AI Assistant can save an earlier answer in the chat as a new topic. This saves you from copying a summary or explanation into a new file.

To create a topic from an earlier answer:

1. Enter a prompt that produces the content you want.

   For example, enter `Summarize this topic.`

2. Select **Send**.

   AI Assistant displays the summary in the chat.

3. Enter `Save this summary as a new topic.`

4. Select **Send**.

   AI Assistant drafts a new topic from the summary and opens a preview.

## Create a map from existing topics

You can ask AI Assistant to group topics that already exist in your repository into a new map. AI Assistant proposes the grouping and order before it creates the map.

To create a map from existing topics:

1. Type `@` in the prompt box, followed by the paths of the topics, separated by commas.

2. Enter a prompt that names the map you want.

   For example, enter `Make a map from these four existing topics: overview, install, config-reference, troubleshooting.`

3. Select **Send**.

   AI Assistant proposes how to group and order the topics.

4. Review the proposed grouping and order.

   After your review, AI Assistant opens a preview of the new map.

## Create topics from pasted content

Pasting a how-to or an overview lets you draft a topic without saving a file first. Plain text and formatted content both work for creating new topics.

To create topics from pasted content:

1. Copy the content from a web page, Word, Google Docs, or a wiki.

2. Paste the content into the prompt box.

   Pasted content over 2,000 characters becomes an attachment.

3. Enter a prompt that names the topic type.

   For example, enter `Create a task topic from these pasted steps.` or `Create a concept topic from this pasted overview.`

4. Select **Send**.

   AI Assistant drafts the topic and opens a preview.-->



