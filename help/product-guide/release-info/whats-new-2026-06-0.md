---
title: Release Notes | What's New in Adobe Experience Manager Guides 2026.06.0 release
description: Learn about the new and enhanced features in the 2026.06.0 release of Adobe Experience Manager Guides
role: Leader
---
# What's new in the 2026.06.0 release (June 2026)

This article covers the new and enhanced features introduced with the 2026.06.0 release of Adobe Experience Manager Guides as a Cloud Service.

For the list of issues fixed in this release, view [Fixed issues in the 2026.06.0 release](fixed-issues-2026-06-0.md).

Learn about [upgrade instructions for the 2026.06.0 release](../release-info/upgrade-instructions-2026-06-0.md).

## Fetch content from Git repositories using Git connector (Beta)

Experience Manager Guides now introduces Git Connector (Beta), which allows you to import content from Git repositories into Experience Manager Guides.

After the content is imported, teams can continue using Experience Manager Guides for their authoring, review, translation, and publishing workflows.

To help keep imported content up to date, Git Connector also supports re-fetching content from the source repository to bring in updates. It includes intelligent change detection to identify content updates, preserves topic and map GUIDs during import and re-fetch operations, and provides conflict resolution capabilities to help manage differences between repository content and content already available in Experience Manager Guides. For more details, view [Import DITA content from Git repositories using Git Connector](../user-guide/web-editor-git-connector.md). 

## Introducing a new publishing engine for native PDF in Experience Manager Guides

A new publishing engine is now available for Native PDF in Experience Manager Guides. The new engine provides support for `OpenType` fonts and updated `CSS` processing capabilities, helping you take advantage of newer PDF rendering features.

Because the new publishing engine uses updated rendering behavior, generated PDF output may differ from output produced by the existing publishing engine. If you use custom PDF templates or CSS customizations, review your generated output and update stylesheets as needed to maintain the desired appearance.

For more details, view [Working with the new publishing engine for Native PDF](../web-editor/new-pdf-engine.md). 

## Editor enhancements 

### Support for AMA citation style

Experience Manager Guides now supports the American Medical Association (AMA) citation style, extending the existing citation framework to meet the documentation standards required by customers in healthcare, regulatory, and life sciences sectors.

When AMA is selected as the citation style in **Workspace settings**, citations are automatically formatted according to AMA guidelines, including numeric superscript rendering, sequential numbering, and accurate reference list ordering. The **Parse citation** option in the Editor is available exclusively when AMA is selected, allowing authors to add and parse citations without switching contexts.

AMA citation style is supported across the Native PDF and AEM Sites output formats. To configure the citation style, go to **Workspace settings** and select AMA from the citation style options. For details, view [Work with citations](../user-guide/web-editor-apply-citations.md).


### Support for external data sources and citations now available in the New Editor

The New Editor now supports two existing Experience Manager Guides capabilities: Ability to connect with external data sources and and use citations in the documents.

Authors can continue using configured external data sources while creating or updating content in the New Editor. Citations are also supported, so authors can add and manage references in their content without switching editors.

## Product Training and Learning content enhancements

The following enhancements are available for the Product Training and Learning content feature in this release:

- Authors can now make a marked knowledge check mandatory before learners advance in a course. A new **Require knowledge check to proceed** option is introduced for knowledge checks in courses. When enabled, this option requires learners to complete the marked knowledge check before they can move ahead in the course. The **Next** button remains disabled until all mandatory questions are completed.
- You can now use multiline text input fields when creating learning content. This enhancement makes it easier to capture longer learner responses by supporting line breaks and text wrapping within a single field, without relying on custom scripting. 
- 
-
- 

## Review enhancements

### User identification in the tagging list during review

When tagging users in review comments or replies, the tagging dropdown now displays each user's email address alongside their user ID. This makes it easier to identify and select the correct reviewer, especially in large organizations where display names alone may be ambiguous.

If an email address isn't available, the user ID is shown instead. For more details on working with Review UI, view [Review topics](../user-guide/review-topics.md).

### Sync review task completion between the Review UI and AEM Inbox (Beta)

>[!NOTE]
>
> This feature is currently available as a Beta feature and is disabled by default. To enable it in your environment, contact the Customer Success team.

You can now keep review task completion in sync between the Review UI and the AEM Inbox. When this feature is enabled, completing a task in the Review UI removes it from the AEM Inbox, and completing it from the AEM Inbox marks it as completed in the Review UI. This helps avoid completing the same task twice and makes the review workflow smoother. Authors and task initiators can continue to review feedback and reassign tasks when additional review is required. When a task is reassigned, a new AEM Inbox notification is generated for the reviewer, allowing the review cycle to continue seamlessly.

For more details on the working with the Review UI, view [Review topics](../user-guide/review-topics.md). 

## Publishing enhancements

## Customize PDF output with topichead styles

You can now use the `outputclass` attribute on `<topichead>` elements to apply custom styles in PDF output. Similar to `<topicref>`, you can style the topichead entry in the table of contents, the generated heading based on the topichead's navtitle, and the content associated with the topichead. This enhancement provides greater flexibility for customizing the appearance of PDF output. 

For more details, view [Apply custom style on TOC entries and topic content](../native-pdf/custom-style-toc.md).

