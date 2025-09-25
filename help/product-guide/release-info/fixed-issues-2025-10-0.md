---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2025.10.0 release
description: Learn about the bug fixes in the 2025.10.0 release of Adobe Experience Manager Guides as a Cloud Service.

---
# Fixed issues in the 2025.10.0 release 

This article covers the bugs fixed in various areas of the 2025.10.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2025.10.0 release](whats-new-2025-10-0.md).

Learn about [upgrade instructions for the 2025.10.0 release](upgrade-instructions-2025-10-0.md).

## Authoring

- When multiple DITA maps or topics are open and one of the topics is closed, the **>>** button which showcases all the open tabs gets overlapped with the remaining open tabs on the Tab bar. (GUIDES-31421)
- With the **Approval workflow** enabled, the **Start a New Release** button is not visible on the Editor toolbar if both the Left panel and the Content properties panel are open. (GUIDES-29093)
- When snippet names exceed the width of the snippet panel, they wrap incorrectly onto the next line, resulting in overlap with adjacent snippets and impacting readability. (GUIDES-22685)
- When you add the same reference multiple times to a DITA map, the **Map** view displays the title only for the last occurrence, while the previous ones show the UUID of the reference. (GUIDES-9699)
- The DITAVAL files remain editable,  even when they are locked by another user or when the server has **Disable edit without locking the file** enabled and the file is opened in read-only mode. (GUIDES-27754)
- Logs for missing nodes are being generated from internal cleanup jobs that are not required and are incorrectly marked as errors, resulting in cluttered log files. (GUIDES-31765)


## Publishing

- When generating PDFs, the filtering rules in a DITAVAL file are ignored if any property name contains a period. (GUIDES-33229)
- Salesforce publishing fails with an application error, when a topic with the same name and URL already exists. (GUIDES- 32390)
- Salesforce publishing displays a successful status on the UI even when a DITA map containing a `topichead` element fails to publish the topics within it. (GUIDES-32143)
- For HTML5 output preset, the search filter functionality is not working in AEM Assets for DITAVAL filtering, as the corresponding files are not being displayed when the DITAVAL filter is selected. (GUIDES-28231)
- When generating a Native PDF for a DITA map with multiple topics, if any topic contains a `fig` element within a `figgroup` along with a `title`, the `figgroup` title is incorrectly rendered as a chapter title in the Table of Contents. (GUIDES-23223)
- When duplicating PDF templates from the UI, the UUID is also duplicated, causing template files to be deleted and resulting in incorrect PDF outputs. (GUIDES-30456)
- When generating Native PDF for a DITA map, the title of `example` element is rendering as `h1` heading level, thereby leading to visual inconsistency and improper TOC structure. (GUIDES-19958)

## Translation

- When zooming in the screen of Translation UI, the **Send for Translation** button moves under the ellipsis and becomes enabled even without any asset being selected. (GUIDES-33720)
- When selecting files with **Out of Sync** status on the Translation UI, and the screen width is constrained due to open Left and Right panels, the **Send for translation** label gets truncated. (GUIDES-33692)

## Review

- When a reviewer completes a review task or initiator updates review task without entering comments, the notification email sent displays the most recent previous comment. (GUIDES-33590)

## Known issues

Adobe has identified the following known issues for the 2025.10.0 release:

- When opening a URL with a previously opened DITA topic or refreshing an opened DITA topic, it fails to locate the topic in the repository despite the 'Always locate files in repository' setting being enabled in user preferences. (GUIDES-35565)
**Workaround**: Selecting the topic tab locates the file in the repository.

- When creating a new file in Author view with multiple files already open, the Right Panel fails to refresh and displays incorrect data if the cursor is placed on an element tag in a different file. (GUIDES-35450)
**Workaround**: Switching tabs or refresh the page to resolve the issue.

- When unlocking a file that was previously set to Read-only and then attempting to unlock it again, the system incorrectly displays the error message "Selected files are not locked". (GUIDES-35421)
**Workaround**: Refresh the page or locking/unlocking the topic resolve the issue.

- The 'Refresh Navigation' button is appearing for DITA topic files, though it should only be available only for DITA maps, book maps, and subject schemes. (GUIDES-35452)

- When switching to Author view from Source view for a newly opened topic (by default opened in Source mode), the topic content becomes blank. (GUIDES-35000)




