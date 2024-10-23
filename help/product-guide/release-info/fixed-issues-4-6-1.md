---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 4.6.1 release
description: Learn about the bug fixes in the  4.6.1 release of Adobe Experience Manager Guides
role: Leader

---

# Fixed issues in the 4.6.1 release (October 2024)


This article covers the bugs fixed in various areas of 4.6.1 release of Adobe Experience Manager Guides.


Learn about [upgrade instructions for the 4.6.0 release](../release-info/upgrade-instructions-4-6-0.md).

## Authoring

- DITA map creation on a UUID instance fails when `xmleditor.uniquefilenames`is enabled in `XMLEditorConfig`. (21201)
- When closing a file, comments and labels saved in the **Save Changes and Unlock File** dialog box are not getting added in the Version History with the new version. This is specific to a use case where **Ask for Check-in on Close** or **Ask for New Version on Close** is enabled in `XMLEditorConfig`. (20065) . 
- The Document State marked as **Done** reverts to **Draft** before saving a new version, resulting in the **Done** state not persisting in any document versions.(20006)
- Unable to add a PDF file as an image reference in a topic via drag-and-drop in the Web Editor. (21206)
- Selecting a DITA file in the Assets UI shows the **Open in FrameMaker** option, even when disabled in the configuration.


## Publishing

- Uploading topics with attachments to Salesforce fails and throws an error `STRING_TOO_LONG` if the attachment path exceeds the allowed length. (19420)
- When publishing a topic to Salesforce, the link to the PDF file fails to resolve. (19304)
- The `DUPLICATE_VALUE` error occurs intermittently when attempting to republish an existing article in Salesforce. (17932)
- The Table of Contents (TOC) displays the topic title at level 1 instead of the chapter title in the Native PDF output.(21840)
- When publishing an AEM Site, only a limited number of attributes are available for inclusion in the Table of Contents (TOC). Now, the support has been extended to include all custom attributes. (7483)

## Management

- Fixed resource leak due to Unclosed **ResourceResolver** errors in logs. (18488)
- When creating a new or duplicate baseline, labels display in a random order. (19307)









