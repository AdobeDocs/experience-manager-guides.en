---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 4.6.0 Service Pack 1 release
description: Learn about the bug fixes in the  4.6.0 Service Pack 1 release of Adobe Experience Manager Guides
role: Leader
exl-id: ab45ac10-8a97-4ade-accc-2b884da0e973
TQID: https://experienceleague.adobe.com/-PGxudGeachzaYoru1fHTObZcwRuXzle5s7KRRJlfBA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
    internal-label: Document state
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
    internal-label: Web Editor
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
---
# Fixed issues in the 4.6.0 Service Pack 1 release (October 2024)


This article covers the bugs fixed in various areas of 4.6.0 Service Pack 1 release of Adobe Experience Manager Guides.

Learn about [upgrade instructions for the 4.6.0 Service Pack 1 release](upgrade-instructions-4-6-0-sp1.md).

## Authoring

- DITA map creation on a UUID instance fails when `xmleditor.uniquefilenames`is enabled in `XMLEditorConfig`. (21201)
- When closing a file, comments and labels added in the **Save Changes and Unlock File** dialog box are not getting saved in the Version History with the new version. This is specific to a use case where **Ask for Check-in on Close** or **Ask for New Version on Close** is enabled in `XMLEditorConfig`. (20065) 
- The Document State marked as **Done** reverts to **Draft** before saving a new version, resulting in the **Done** state not persisting in any document versions. (20006)
- Unable to add a PDF file as an image reference in a topic in the Web Editor. (21206)
- Selecting a DITA file in the Assets UI shows the **Open in FrameMaker** option, even when disabled in the configuration. (20082)


## Publishing

- Uploading attachments to Salesforce fails if the attachment path exceeds the allowed length. (19420)
- When publishing a topic to Salesforce, the PDF file links fails to resolve. (19304)
- The `DUPLICATE_VALUE` error occurs intermittently when attempting to republish an existing article in Salesforce. (17932)
- In the Native PDF output, chapter titles are missing from the TOC, leading to an incorrect hierarchy. (21840)
- When publishing AEM Sites, only a limited number of attributes are available for inclusion in the TOC. (7483)

## Management

- Resource leaks occur due to Unclosed **ResourceResolver** errors in logs. (18488)
- When creating a new or duplicate baseline, labels are displayed in a random order. (19307)
