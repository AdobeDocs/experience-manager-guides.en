---
title: Release Notes | What's New in Adobe Experience Manager Guides 2026.05.0 release
description: Learn about the new and enhanced features in the 2026.05.0 release of Adobe Experience Manager Guides
role: Leader
---
# What's new in the 2026.05.0 release (May 2026)

This article covers the new and enhanced features introduced with the 2026.05.0 release of Adobe Experience Manager Guides as a Cloud Service.

For the list of issues fixed in this release, view [Fixed issues in the 2026.05.0 release](fixed-issues-2026-05-0.md).

Learn about [upgrade instructions for the 2026.05.0 release](../release-info/upgrade-instructions-2026-05-0.md).

## Introducing Editor 2.0

Editor 2.0 marks a significant evolution in authoring, emphasizing performance, usability, and UI/UX to simplify working with large files, complex tables, and structured content without compromising control over how content is viewed and edited.

### Performance enhancements 

Editor 2.0 significantly improves responsiveness when working with large DITA files. This ensures that Authors can confidently edit large topics and maps without performance degradation or loss of edit history.

- Undo/Redo support enabled for large files containing more than 3,500 elements 
- Dirty marker support added for large documents, ensuring accurate change tracking and save-state awareness

### Improved table editing 

Table authoring is enhanced to deliver a smoother and more intuitive experience.  This ensures faster table creation and modification with fewer manual steps and improved accuracy.

- Fluid and responsive table interactions
- Easy row and column insertion
- Drag-and-drop support for column/row reordering 
- Contextual table toolbar for cell alignment, merging and splitting cells, applying common attributes
- Ability to add multiple rows or columns in a single action 

### Enhanced Author view 

The Author view now provides greater visibility into structured content for improved transparency and control over content structure without switching to Source view. 

- XML comments are visible in Author view for both DITA Maps and Topics
- Can be shown or hidden through the Editor settings
- Attributes are now visible alongside elements
- Visibility is user-configurable via Editor settings 

### New Editing modes & Toolbars 

Editor 2.0 introduces powerful new ways to edit content efficiently. This ensures faster authoring with reduced context switching and easier access to structured elements. 

- Side-by-side Author and Source view available for DITA Topics 
- In-line element insertion toolbar
- Allows quick insertion of valid elements directly at the cursor position 

### UI & UX improvements 

Several visual and usability enhancements providing improved readability, accessibility, and a more modern editing interface. 

- Dark theme available for the Content editing area in the Editor 
- Richer out-of-the-box CSS for Author mode and Preview mode 

### New Editor Settings 

A new centralized settings panel gives Authors better control over editor behavior . Configuration options include, ability to enable/disable: 

- Non-breaking spaces in Author mode 
- Tag visibility settings with attributes or without attributes 
- XML comments in author mode 
- Quick insert menu 
- Ability to configure favorite elements 

## Review enhancements

The following Review enhancements have been made as part of this release:

- You can now enable **Automated reminders** to schedule AEM notifications and email reminders for reviewers, both before a review task's due date and after it becomes overdue. You can configure multiple reminders in each case, with pre-due reminders sent in a defined sequence and overdue reminders triggered after the task is marked overdue, based on the configured reminder schedule. For details on how to configure the reminders for review tasks, view [Send one or more topics for review](../user-guide/review-manage-tasks-review-dashboard.md).

- Reviewers can now access Version history for topics under review, allowing them to view and compare previously reviewed and updated versions of the same topic. This helps reviewers validate changes made since earlier review cycles and maintain continuity by reviewing comments, labels, and other related details within the current review context. For details, view [Version history for the Reviewer](../user-guide/review-topics.md#version-history-for-the-reviewer).

## New baseline introduced in Experience Manager Guides

Managing large, complex baselines is now faster, more stable, and easier to scale with the **new baseline experience**, built on a redesigned baseline architecture. This update addresses long‑standing performance and reliability challenges while preserving existing workflows.

Available as a beta enhancement, this update provides solution to common pain points such as slow loading, inconsistent baseline states, and limited manageability by delivering a faster, more stable, and more predictable baseline experience, with added support for automation and large‑scale baseline operations. Improvements are delivered through a more efficient data model, incremental loading, and stronger coordination between the UI and backend validation. The key improvements are:

- Improved performance and scalability
- Stronger UI and backend consistency
- Expanded filtering, navigation, and dependency visibility

For details, view [New baseline in Experience Manager Guides](../user-guide/web-editor-baseline-v2.md).










