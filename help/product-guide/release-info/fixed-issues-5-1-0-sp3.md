---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 5.1.0 Service Pack 3 release
description: Learn about the bug fixes in the 5.1.0 Service Pack 3 release of Adobe Experience Manager Guides
role: Leader
exl-id: faa9a5d7-616f-4692-98d1-23abc78556b6
TQID: https://experienceleague.adobe.com/qiVY-B-D3FcHq2PH7Go2AAFpnstCrPJ2MVLEalQCVn0
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
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
---
# Fixed issues in the 5.1.0 Service Pack 3 release (December 2025)


This article covers the bugs fixed in various areas of 5.1.0 Service Pack 3 release of Adobe Experience Manager Guides.

Learn about [upgrade instructions for the 5.1.0 Service Pack 3 release](upgrade-instructions-5-1-0-sp3.md).


## Authoring

- Custom CSS applied at a folder-level profile for topics or maps is reverted to the default style in Preview mode upon browser refresh. (GUIDES-31098)
- Unable to add multiple **Version labels** to a topic from the **Save as new version** dialog. (GUIDES-32716)


## Asset management

- Unable to remove Version labels from **Version history** panel in Assets UI. (GUIDES-38276)


## Review

- When a Reviewer completes a review task or initiator updates review task without entering comments, the notification email sent displays the most recent previous comment. (GUIDES-33590)

## Publishing 

- When you generate AEM Sites output using legacy component mapping, topics that use the `copy-to` attribute get published with the `copy-from` topic's name instead of the name set in the `copy-to` attribute. (GUIDES-22155)
- When Native PDF output is generated using a dynamic baseline, the term **PDFProject** is displayed as the PDF title instead of the actual map title. (GUIDES-31102)

## Platform

- Using `scope="external"` for a reference to DAM content within a topic or map causes the asset's relative path to be substituted with a GUID. (GUIDES-35605)

## Known issue

Adobe has identified the following known issue for the 5.1.0 Service Pack 3 release:

- When you mark a review task as complete from the task details page, the task is completed and closed; however, its status continues to display as **In Progress** on the Review dashboard. (GUIDES-39375)
