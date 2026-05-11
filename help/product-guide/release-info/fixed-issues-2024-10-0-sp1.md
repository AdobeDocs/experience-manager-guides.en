---
title: Release Notes | Fixed issues in the 2024.10.0 Service Pack 1 release of Adobe Experience Manager Guides
description: Learn about the bug fixes in the 2024.10.0 Service Pack 1 release of Adobe Experience Manager Guides as a Cloud Service.
exl-id: d5fa200b-1f15-4ec2-adf9-a29382afc3de
TQID: https://experienceleague.adobe.com/ziRAAFKf5Dl-6Hd7ziXwSJepbiVzkXLGz5jDWIILPkU
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
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Fixed issues in the 2024.10.0 Service Pack 1 release

This article covers the bugs fixed in various areas of the 2024.10.0 Service Pack 1 release of Adobe Experience Manager Guides as a Cloud Service.

## Authoring

- DITA map creation on a UUID instance fails when `xmleditor.uniquefilenames` is enabled in `XMLEditorConfig`. (21201)
- When closing a file, comments and labels added in the **Save Changes and Unlock File** dialog box are not getting saved in the Version History with the new version. This is specific to a use case where **Ask for Check-in on Close** or **Ask for New Version on Close** is enabled in `XMLEditorConfig`. (20065)
- Document state marked as **Done** reverts back to **Draft** before saving a new version, resulting in the **Done** state not persisting in any document versions. (20006)
- Unable to add a PDF file as an image reference in a topic in the Web Editor. (21206)
- Selecting a DITA file in the Assets UI shows the **Open in FrameMaker** option, even when disabled in the configuration. (20082)

## Publishing

- In the Native PDF output, chapter titles are missing from the TOC, leading to an incorrect hierarchy. (21840)

 
## Management

- Resource leaks occur due to **Unclosed ResourceResolver** errors in logs. (18488)
- When creating a new or duplicate baseline, labels are displayed in a random order. (19307)


## Baseline

- Editing and then Saving a Baseline on a Cloud setup timesout after 1 minute if the Baseline has large number of topics or maps. (19558)

## Translation

- Map translation using Baseline becomes slow and eventually fails to load the list of all the associated topics and maps files. (19733)
