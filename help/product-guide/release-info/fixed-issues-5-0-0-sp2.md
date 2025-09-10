---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 5.0.0 Service Pack 2 release
description: Learn about the bug fixes in the 5.0.0 Service Pack 2 release of Adobe Experience Manager Guides
role: Leader

---
# Fixed issues in the 5.0.0 Service Pack 2 release (September 2025)


This article covers the bugs fixed in various areas of 5.0.0 Service Pack 2 release of Adobe Experience Manager Guides.

Learn about [upgrade instructions for the 5.0.0 Service Pack 2 release](upgrade-instructions-5-0-0-sp2.md).

## Platform

- When upgrading from version 4.3.1 (non-UUID) to the latest version through UUID migration, and moving dependent images between folders and subsequently reverting the parent DITA files to earlier versions it results in broken image references. (GUIDES-34315)

## Known issues

Adobe has identified the following known issues for 5.0.0 Service Pack 2 release:

- The most recent task-level comment is displayed in the email notification to the task initiator if the Reviewer completes the task without adding a comment. (GUIDES-33590)
- In the Merge dialog, the dropdown list incorrectly displays Main content instead of showing the available versions of the selected topic. (GUIDES-30820)
- Switching between presets that use the same Baseline deactivates the Save button for the current preset. (GUIDES-28025)
- An empty line is automatically inserted when pasting new content into a new line within a codeblock element.(GUIDES-27842)
- A topic within a DITA map fails to publish in the AEM Sites output when it is being used as both keydef and topicref within its submaps. (GUIDES-22269)
- In the Content properties panel, the Attributes field closes automatically when you try to update a reference from the Update link dialog, preventing the link from being updated. (GUIDES-17767)