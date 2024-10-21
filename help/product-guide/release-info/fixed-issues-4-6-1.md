---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 4.6.1 release
description: Learn about the bug fixes in the  4.6.1 release of Adobe Experience Manager Guides
role: Leader

---

# Fixed issues in the 4.6.1 release (October 2024)


This article covers the bugs fixed in various areas of 4.6.1 release of Adobe Experience Manager Guides.


For more information about the new features and enhancements, view [What's new in  the 4.6.1 release](whats-new-4-6-1.md).

Learn about [upgrade instructions for the 4.6.1 release](../release-info/upgrade-instructions-4-6-1.md).

## Authoring

- DITA map creation on a UUID instance fails when `xmleditor.uniquefilenames`is enabled in `XMLEditorConfig`. (21201)
- Comments or Labels entered while saving a file in the Web Editor do not save in the version history when **Ask for Check-in on Close** or **Ask for New Version on Close** is enabled in `XMLEditorConfig`. 
- Document state marked as **Done** reverts back to **Draft** on saving as a new version. (20006)
- Unable to add a PDF file as image in the Web Editor. (21206)

## Publishing

- Uploading topics with attachments to Salesforce fails and throws an error `STRING_TOO_LONG` if the attachment points to a long string path. (19420)
- Bulk Publish Dashboard shows blank for maps that are still in the translation process.(19352)
- When publishing a topic to Salesforce, the link to a PDF file is not resolving as expected. (19304)
- On a Windows setup, publishing fails at the DITA-OT execution step when topics or maps contain multi-valued metadata properties. (19001)
- The `DUPLICATE_VALUE` error occurs intermittently when attempting to republish an existing article in Salesforce. (17932)


## Management

- In some cases, migratring content using scripts results in numerous **Unclosed ResourceResolver** errors. (18488)

## Baseline

- Editing and then Saving a Baseline on a Cloud setup timesout after 1 minute if the Baseline has large number of topics or maps. (19558)
- Publication labels are displayed in a random order when creating New or Duplicate Baselines for topics and maps. (19307)


## Translation

- Map translation using Baseline becomes slow and eventually fails to load the list of all the associated topics and maps files.

## General

- When selecting a DITA file in the Asset UI, the option **Open in FrameMaker** appears, even though it is disabled in the configuration settings. (20082)






