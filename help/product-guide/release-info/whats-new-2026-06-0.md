---
title: Release Notes | What's New in Adobe Experience Manager Guides 2026.06.0 release
description: Learn about the new and enhanced features in the 2026.06.0 release of Adobe Experience Manager Guides
role: Leader
---
# What's new in the 2026.06.0 release (June 2026)

This article covers the new and enhanced features introduced with the 2026.06.0 release of Adobe Experience Manager Guides as a Cloud Service.

For the list of issues fixed in this release, view [Fixed issues in the 2026.06.0 release](fixed-issues-2026-06-0.md).

Learn about [upgrade instructions for the 2026.06.0 release](../release-info/upgrade-instructions-2026-06-0.md).


## New map collection (Beta) for managing maps and publishing outputs

>[!NOTE]
>
> This feature is currently available as a Beta feature and is disabled by default. To enable it in your environment, contact the Customer Success team.

New map collection (Beta) brings map collection management and output generation activities together in a single interface. From one location, you can manage maps and presets, generate and publish outputs, view generation and publishing history, and more. By bringing related publishing tasks together, it makes it easier to work with map collections and track output activity across multiple maps and their associated languages.

![](assets/new-maps-collection.png)

For more details, view [Use New map collection for output generation (Beta)](../user-guide/generate-output-use-new-map-collection-output-generation.md). 

## Introducing a new publishing engine for Native PDF

A new publishing engine, *Native PDF engine v2*, is now available for Native PDF in Experience Manager Guides. It includes rendering enhancements and fixes for Native PDF engine v1 issues. Because rendering behavior has been updated, PDF output generated with *Native PDF engine v2* may differ from output generated with the existing Native PDF publishing engine, *Native PDF engine v1*.

For example, text in generated PDFs may appear slightly different due to updates in the core fonts used by *Native PDF engine v2*. Similarly, images may appear more sharper because of improvements in image interpolation and rendering behavior.

Learn how to [enable Native PDF engine v2](../install-conf-guide/conf-new-pdf-engine.md) in your environment. 

For information about enabling **Native PDF engine v2** and reviewing migration considerations, view [Work with the Native PDF engine v2](../web-editor/new-pdf-engine.md).


## Editor enhancements 

### Support for AMA citation style

Experience Manager Guides now supports the American Medical Association (AMA) citation style, extending the existing citation framework to meet the documentation standards required by customers in healthcare, regulatory, and life sciences sectors.

When AMA is selected as the citation style in **Workspace settings**, citations are automatically formatted according to AMA guidelines, including numeric superscript rendering, sequential numbering, and accurate reference list ordering. The **Parse citation** option in the Editor is available exclusively when AMA is selected, allowing authors to add and parse citations without switching contexts.

AMA citation style is supported across the Native PDF and AEM Sites output formats. To configure the citation style, go to **Workspace settings** and select AMA from the citation style options. For details, view [Work with citations](../user-guide/web-editor-apply-citations.md).


### Support for external data sources and citations now available in the New Editor

The New Editor now supports two existing Experience Manager Guides capabilities: Ability to connect with external data sources and use citations in the documents.

Authors can continue using configured external data sources while creating or updating content in the New Editor. Citations are also supported, so authors can add and manage references in their content without switching editors. 

## Review enhancements

### Sync review task completion between the Review UI and AEM Inbox (Beta)

>[!NOTE]
>
> This feature is currently available as a Beta feature and is disabled by default. To enable it in your environment, contact the Customer Success team.

You can now keep review task completion in sync between the Review UI and the AEM Inbox. When this feature is enabled, completing a task in the Review UI removes it from the AEM Inbox, and completing it from the AEM Inbox marks it as completed in the Review UI. This helps avoid completing the same task twice and makes the review workflow smoother. Authors and task initiators can continue to review feedback and reassign tasks when additional review is required. When a task is reassigned, a new AEM Inbox notification is generated for the reviewer, allowing the review cycle to continue seamlessly.

For more details, view [Review topics](../user-guide/review-topics.md). 

## Learning content enhancements

The following enhancements are available for the Product Training and Learning content feature in this release:

- Authors can now make a knowledge check mandatory for learners before they advance in a course. A new **Require knowledge check to proceed** option is introduced for knowledge checks in courses. When enabled, learners are required to attempt a knowledge check before proceeding to subsequent course content. This helps ensure that required knowledge checks are completed at designated points in the course. For more details, view [Other options in the Insert menu](../learning-content/lc-other-insert-options.md).
- You can now use multiline text input fields when creating learning content. This enhancement makes it easier to capture longer learner responses by supporting line breaks and text wrapping within a single field, without relying on custom scripting. Learn more about [Other options in the Insert menu](../learning-content/lc-other-insert-options.md).
- SCORM output templates now support assigning different page layouts to different topic types within a course. This allows you to configure dedicated layouts for lessons, quizzes, overview pages, and other topic types directly from the output template settings.

    This allows each topic type to use a layout that is appropriate for its content and structure, rather than applying the same layout across all course pages. For more details on configuring page layouts for SCORM output templates, view [Configure Folder profiles](../lc-config-guide/lc-folder-profile.md). 
- Experience Manager Guides now supports direct publishing of SCORM content to Adobe Learning Manager (ALM). After configuring an ALM publish profile, authors can generate SCORM output and upload it directly to Adobe Learning Manager without downloading and manually importing the package.

    For more details, view [Configure SCORM preset](../learning-content/config-scorm-preset.md).


