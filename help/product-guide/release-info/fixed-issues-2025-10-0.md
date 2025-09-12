---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2025.10.0 release
description: Learn about the bug fixes in the 2025.10.0 release of Adobe Experience Manager Guides as a Cloud Service.

---
# Fixed issues in the 2025.10.0 release 

This article covers the bugs fixed in various areas of the 2025.10.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2025.10.0 release](whats-new-2025-10-0.md).

Learn about [upgrade instructions for the 2025.10.0 release](upgrade-instructions-2025-10-0.md).

## Authoring

- When multiple DITA maps or topics are open and one of the topics is closed, the **Action** button gets overlapped with the remaining open tabs on the Tab bar. (GUIDES-31421)
- With the **Approval workflow** enabled, the **Start a New Release** button is not visible on the Editor toolbar if both the Left panel and the Content properties panel are open. (GUIDES-29093)
- When using a limited window width, long snippet names wrap incorrectly, causing the text to overlap and become difficult to comprehend. (GUIDES-22685)
- When you add the same reference multiple times to a DITA map, the **Map** view displays the title only for the last occurrence, while the previous ones show the GUID of the reference. (GUIDES-9699)
- The DITAVAL files remain editable,  even when they are locked by another user or when the server has **disable edit without checkout** enabled and the file is opened in read-only mode. (GUIDES-27754)
- When zooming in the screen of Translation UI, the **Send for Translation** button moves under the ellipsis and becomes enabled even without any asset being selected. (GUIDES-33720)
- Some logs were being generated from the scheduled jobs, that were not required and were incorrectly marked as errors, resulting in cluttered log files. (GUIDES-31765)


## Publishing

- When generating PDFs, the filtering rules in a DITAVAL file are ignored if any property name contains a period (.), thereby resulting in the inclusion of the filtered content in the PDF. (GUIDES- 33229)
- Publishing fails with an application error, when a topic with the same name and URL already exists in Salesforce. (GUIDES- 32390)
- When a DITA map includes a `topichead` element, the topics within the DITA map fail to publish, despite the UI indicating a successful publishing status. (GUIDES-32143)
- For HTML5 output preset, the search filter functionality is not working in AEM Assets for DITAVAL filtering, as the corresponding files are not being displayed when the DITAVAL filter is selected. (GUIDES-28231)
- When generating a Native PDF for a DITA map with multiple topics, if any topic contains a `fig` element within a `figgroup` along with a `title`, the `figgroup` title is incorrectly rendered as a chapter title in the Table of Contents. (GUIDES-23223)
- When duplicating PDF templates from the UI, the UUID is also duplicated, causing template files to be deleted and resulting in incorrect PDF outputs. (GUIDES-30456)
- When generating Native PDF for a DITA map, the title of `example` element is rendering as `h1` heading level, thereby leading to visual inconsistency and improper TOC structure. (GUIDES-19958)

## Review

- When a reviewer or initiator completes or updates a task without entering final comments in the **Complete Task** dialog, the notification email sent to them displays the most recent comment from the previous given comments. (GUIDES-33590)



