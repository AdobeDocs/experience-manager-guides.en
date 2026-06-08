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

Experience Manager Guides now introduces Git Connector (Beta), which allows you to import DITA content from Git repositories into Experience Manager Guides.

After the content is imported, teams can continue using Experience Manager Guides for their authoring, review, translation, and publishing workflows.

To help keep imported content up to date, Git Connector also supports re-fetching content from the source repository to bring in updates. It includes intelligent change detection to identify content updates, preserves topic and map GUIDs during import and re-fetch operations, and provides conflict resolution capabilities to help manage differences between repository content and content already available in Experience Manager Guides. For more details, view [Import DITA content from Git repositories using Git Connector](../user-guide/web-editor-git-connector.md). 

## Support for external data sources and citations now available in the New Editor

The New Editor now supports two existing Experience Manager Guides capabilities: Ability to connect with external data sources and and use citations in the documents.

Authors can continue using configured external data sources while creating or updating content in the New Editor. Citations are also supported, so authors can add and manage references in their content without switching editors.

## Learning 

- **Mandatory knowledge checks before progressing in a course**: Authors can now make a marked knowledge check mandatory before learners advance in a course. A new **Require knowledge check to proceed** option is introduced for knowledge checks in courses.

When enabled, this option requires learners to complete the marked knowledge check before they can move ahead in the course. The **Next** button remains disabled until all mandatory questions are completed.

## Support custom styling for topichead and topicgroup in Native PDF output

In Native PDF publishing, you can now apply the outputclass attribute to `topichead` and `topicgroup` elements in a DITA map, allowing you to style section headings, grouped content, and related TOC entries.

This enhancement reduces the need to manually apply the same `outputclass` to individual child `topicref` elements and gives you more flexibility when defining styles through `layout.css` and `content.css`.

For more details, view [Apply custom style on TOC entries and topic content](../native-pdf/custom-style-toc.md).


#### Apply custom style to a `<topichead>`

You can also apply an `outputclass` attribute to the `<topichead>` element in your DITA map and define a custom style for it in the CSS.

For example, if you want to visually identify a section heading that is new or recently updated, add an `outputclass` attribute to the `<topichead>` element in your DITA map:

```xml
<topichead navtitle="History of flights" outputclass="new-topic"/>


