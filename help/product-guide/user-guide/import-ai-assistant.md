---
title: Import documents as topics with AI Assistant
description: Learn how to convert PDF, Word, and Markdown files into DITA topics and a map with AI Assistant, and review the result before you save it.
---

# Import documents with AI Assistant

Moving existing content into Adobe Experience Manager Guides often means rebuilding every heading, list, and table as topic files by hand. In AI Assistant in Agentic mode, the **Import** feature converts a PDF, Word, or Markdown file into DITA topics and a corresponding map for you. You choose how the file is split into topics and where the topics are saved. 

This article covers the import workflow. To learn about the panel, attachments, and conversation history, view [Get started with AI Assistant in Agentic mode](#).


## Import a file as topics and a map

Importing converts a PDF, Word, or Markdown file into topics and a map. You decide which heading level starts a new topic, so the topics match how you want to structure the content.

To import a file:

1. On the Home page, select **AI Assistant** from the Navigation bar.

1. Select **Import** from the AI Assistant panel. You can also use other prompts like `Convert this docx to DITA topics.` for a Word file or `Convert this markdown into DITA topics.` for a Markdown file.

   The starter prompt `Help me import content from the attached PDF file` appears in the prompt box.

1. Attach the file to your prompt using any of the following methods: 

   - **Using shortcut**: Type `/` in the Prompt field, then choose **Add repository reference** to choose the file from the Repository (or **Add files from device** to upload the file from your computer).

   - **Using `Attach files or add context (+)*` icon**: Adds files from your local system to provide the content for importing. 

   - **Drag and drop**: Drag and drop the file you wnat to import from the system directly into the prompt space.

      ![](images/attach-import.png)

1. Select **Send**.

   AI Assistant analyzes the file and lists each step it completes.

1. Select and confirm the folder where you want to save the imported topics.   

   ![](images/folder-import.png)

1. Choose the heading level that becomes a topic. For example H2 as shown in the screenshot.

   ![](images/heading-import.png)

1. Select **Confirm**.

   AI Assistant starts converting the file.

1. Select **Preview** to review the generated topics and the map.

   Check that each topic starts at the heading you expected and that the map order matches the original file. You can also check the Source code of the data imported using the Source tab. 

   ![](images/preview-import.png)

1. Select one of the following:

   - **Accept** to save all topics and the map to the folder you confirmed
   - **Reject** to discard the import without saving anything   

      The topics and the map are now available in your repository.

      ![](images/accept-reject-import.png)

After the conversion finishes, AI Assistant opens a preview of the generated topics and map. You can navigate to the corresponding map and topics directly from the AI Assistant dialog.

## Import pasted content as topics

Pasting content from a web page, Word, Google Docs, or a wiki lets you import without saving a file first. Formatted content keeps its headings, lists, and tables.

To import pasted content:

1. On the Home page, select **AI Assistant** from the Navigation bar.

2. Copy the content from the web page, Word, Google Docs, or wiki.

3. Paste the content into the prompt box.

   Formatted content over 2,000 characters is attached as Markdown, so its structure carries over.

4. Enter a prompt that names what you want.

   For example, enter `Import the pasted page into DITA.` or `Turn the pasted content into DITA topics and a map.`

5. Select **Send**.

   AI Assistant asks for the heading level and the save folder, as it does for an attached file.

>[!NOTE]
>
>Only formatted pastes keep their structure and can be imported. To turn plain text into new topics, view [Create topics and maps with AI Assistant](#).


## Example import prompts

These prompts show how you can phrase an import request in the prompt box.

| Prompt | What it does |
|---|---|
| `Import this PDF to DITA.` | Converts the attached PDF file |
| `Convert this docx to DITA topics.` | Converts the attached Word file |
| `Convert this markdown into DITA topics.` | Converts the attached Markdown file |
| `Turn the pasted content into DITA topics and a map.` | Converts the content you pasted |

*Caption: The same import flow applies to every file type, so you only change the file named in the prompt.*


