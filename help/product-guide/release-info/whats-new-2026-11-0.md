---
title: Release Notes | What's New in Adobe Experience Manager Guides 2026.11.0 release
description: Learn about the new and enhanced features in the 2026.11.0 release of Adobe Experience Manager Guides
role: Leader
---

# What's new in the 2026.11.0 release (November 2026)

## Introducing AI-powered content creation and import in AI Assistant

Now, you can use **AI Assistant** to create and import DITA content using natural-language prompts. Powered by **Adobe CX Enterprise Coworker**, the new **Create** and **Import** skills simplify structured content creation and help authors work with DITA content without requiring extensive DITA expertise.

- **Create:** Generate DITA topics and maps from natural-language prompts, reference documents, or existing content using repository templates. You can review the generated content before saving it.
- **Import:** Convert existing PDF, DOCX, or Markdown files into structured DITA topics and maps. You can preview and review the converted content before saving it to the repository.

The **AI Assistant** panel also introduces a fullscreen mode and an **Active conversations** section for an enhanced conversational experience.

For more details, view [Use AI Assistant in Agentic mode](../user-guide/ai-assistant-agentic.md).


## Introducing the Assistant panel in the Editor

The generative AI-powered **Smart Help** capability is now available through the dedicated **Help Assistant** panel, accessible from the Editor's tab bar. The panel provides a conversational search experience, allowing you to ask questions in natural language and quickly find relevant information from the AEM Guides documentation. This helps you access contextual guidance and resolve queries without leaving the Editor, streamlining your authoring workflow.

Administrators can manage the availability of the Help Assistant panel through Workspace settings. The **AI Help Assistant** section includes a toggle to enable or disable the panel for users.

For more information, see the [AI Help Assistant](../user-guide/ai-assistant.md) documentation.

## Track changes panel in the New editor

The Track Changes panel is now available in the New Editor, providing a centralized view of all tracked edits and comments within a topic. You can review, accept, or reject changes directly from the panel, streamlining collaboration and content review.

You can also control how deleted content appears in the Editor using the **Show tracked deletions inline** setting that lets you display deleted content as strikethrough text or replace it with a pencil icon linked to the corresponding change. Learn more about [Track changes](../user-guide/config-editor-settings.md#track-changes).

## Sort files and folders in the Explorer panel

The **Explorer** panel in the Editor now lets you sort files and folders in ascending or descending order using the **Sort** button. By default, items are displayed in ascending order based on the **Editor files display** setting in **User preferences**. Depending on your configuration, files and folders are sorted by either title or file name. This enhancement makes it easier to navigate and locate topics and maps within the Editor.

For more information, view [Explorer](../user-guide/paginated-loading-assets.md#explorer) section in Paginated loading of files and folders.

## Manage versions and labels for non-DITA files from the Editor

Experience Manager Guides now lets you view version history and manage version labels for non-DITA files, such as images, multimedia files, ZIP files, PDFs, and DOCX files, directly from the Editor. You can preview these files, review their version history, compare versions, and revert to an earlier version without navigating to the Assets UI.

You can also assign or update version labels to identify specific file versions for content releases and baseline management, ensuring consistency between your content and associated assets.

For more information, view [Work with media and other non-DITA files](../user-guide/authoring-file-management.md#work-with-media-and-other-non-dita-files).

## Review initiators can add comments for reviewers

Review initiators can now add inline comments and annotations to topics within a review task using the Review UI. This allows them to provide additional context, highlight specific content, and draw reviewers' attention to areas that require feedback.

These comments appear in the **Comments** panel alongside feedback from other reviewers, providing a consolidated view of the review discussions. Reviewers also receive an AEM notification when the initiator adds a comment, helping streamline collaboration and communication throughout the review process. For more information, view [Add comments for reviewers](../user-guide/review-send-topics-for-review.md#add-comments-for-reviewers).

## View and manage output history from the Map Console

The Map console in Experience Manager Guides now includes an **Output history** tab, allowing you to view and manage output generation tasks directly from the Editor without navigating to the Map Dashboard.

The tab provides a consolidated view of output generation tasks, including their status, preset details, generation date, and duration. You can search and filter tasks, cancel ongoing generations, access generated outputs and logs, and remove completed entries from the history. You can also export the output history as a CSV file for further analysis.

Output generation statuses use color indicators consistent with the Map dashboard. A yellow status indicates that generation completed with errors or warnings, helping you identify outputs that require attention without opening individual logs.

Fore details, view [Manage output generation process](../user-guide/generate-output-manage-process.md#view-and-manage-output-generation-tasks-from-the-editor).


## Enhanced output history purging options

*Source: GUIDES-4365*

Adobe Experience Manager Guides now offers two options for purging output history: **By age**, which removes entries older than a specified number of days, and **By count**, which keeps only the specified number of recent entries for each map and preset.

You can also choose to purge only the output logs while preserving the history entries for audit purposes, or remove both the logs and their associated entries. These options help optimize repository storage while providing greater control over output history purging.

For more information, view [Configure auto-purging period for output history](../install-conf-guide/conf-output-generation.md#configure-auto-purging-period-for-output-history-id19aai070v8q).

## GitLab support for Edge Delivery Services publishing profiles

You can now publish DITA content to Edge Delivery Services sites whose code repository is hosted in GitLab, in addition to GitHub. When you create an Edge Delivery Services publishing profile, select GitLab as the server type and enter a project access token generated for the repository in the Access Token field.

Publish presets also include a field for a subfolder, so you can publish content to a subfolder within the root folder specified in the profile.

For more details, view [Configure an Edge Delivery Services].

## Enhancements to Salesforce publishing

Adobe Experience Manager Guides introduces the following enhancements to improve security and publishing efficiency:

- **Support for Proof Key for Code Exchange (PKCE)**: Salesforce publish profiles now support PKCE during validation, enabling secure connections with Salesforce organizations that require PKCE. You can enable this setting in the Salesforce connected app to strengthen authorization security. For details, view [Create a Salesforce profile](../install-conf-guide/workspace-settings.md#publish-profiles).

- **Optimized asset publishing**:  With the enhanced Salesforce publishing experience, Experience Manager Guides checks whether referenced assets, such as multimedia and other non-DITA files, have changed since their last publication. Only modified assets are republished, while unchanged assets are skipped, reducing redundant uploads and improving publishing efficiency. For more information, view [Enhanced Salesforce publishing using backend processing](../user-guide/web-editor-article-publishing.md#enhanced-salesforce-publishing-using-backend-processing).


## Support for images from map metadata in Native PDF

Native PDF publishing now supports dynamically displaying images defined in the metadata of DITA maps, bookmaps, and custom maps. You can use a single PDF template across multiple maps while displaying map-specific images, such as product cover images, in the generated output.

By adding an image placeholder to the page layout, you can automatically populate it with the image referenced in the map metadata during publishing. This eliminates the need to maintain separate templates for different images and simplifies template management.

For more information, view [Add an image from map metadata](../native-pdf/design-page-layout.md#add-an-image-from-map-metadata-add-image-map-metadata).




Check from here 

## Content Health checks for maps and baselines

Source: GUIDES-13317, 24312

Adobe Experience Manager Guides adds a Content Health check at the map level, so you can find content problems before they affect generated output. The check covers:

- Baselines of the map
- Broken links
- Duplicate IDs
- DITA topic validation through Schematron rules

Content Health is on by default in this release. Learn more in the Content Health documentation.

## Upsert API enhancements

*Source: GUIDES-24015*

The Upsert API in Adobe Experience Manager Guides now creates or uploads an asset in a single call, so you no longer call create and update separately. Each request can include:

- A predefined GUID for the asset, instead of one generated from the file name
- Metadata applied when the asset is created
- A version label and comment, created with the asset

This helps when you import content from external systems. Learn more in the Upsert API documentation.

## Generated and Published History in Map Collections

*Source: GUIDES-49986*

Map Collections in Adobe Experience Manager Guides now show the generation and publishing status of each map. When you generate many maps at once, you can check progress from the Map Collections view instead of opening the Outputs tab of every map. This helps you spot failed maps sooner. The new Map Collections experience is on by default in this release. Learn more in the Map Collections documentation.

## Categorized Salesforce publishing results

*Source: GUIDES-33718*

Salesforce publishing in Adobe Experience Manager Guides now returns a categorized result summary after each publish. Topics are grouped as follows:

- Published
- Excluded by conditions
- Failed, with the Salesforce error and the affected field

The summary also shows topic-level stages and a link to view the article in Salesforce. This helps authors find what failed without reading raw logs. Some errors, such as an archived article conflict, still show a generic message. Learn more in the Salesforce publishing documentation.

## Processing instructions and tracked text in outline view

*Source: GUIDES-48316*

The outline view in the new editor now shows entries for processing instructions and tracked text, so you can see and navigate to them from the outline.

For more details, view Use outline view in the new editor.

## GUIDES-37103 [Management] Download a learning map

## GUIDES-15239	[Experience Enhancement] Outputs in XML editor
