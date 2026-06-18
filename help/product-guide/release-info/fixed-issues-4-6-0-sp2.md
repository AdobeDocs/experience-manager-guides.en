---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 4.6.0 Service Pack 3 release
description: Learn about the bug fixes in the  4.6.0 Service Pack 3 release of Adobe Experience Manager Guides
role: Leader
exl-id: 8ff26c28-4a88-4eb2-b359-5b1b0138dd4b
TQID: https://experienceleague.adobe.com/bsiTHK--FPkvfF4bdYUnL-HbAMuhtBKj7wT2eCmd7hM
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
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
    internal-label: Web Editor
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
---
# Fixed issues in the 4.6.0 Service Pack 3 release (January 2025)


This article covers the bugs fixed in various areas of 4.6.0 Service Pack 3 release of Adobe Experience Manager Guides.

Learn about [upgrade instructions for the 4.6.0 Service Pack 3 release](upgrade-instructions-4-6-0-sp2.md).

## Authoring

- All condition groups are lost and the conditions become flattened on updating the conditions from the folder profile. (23526)
- Changing the header rows value for a table in the **Content properties** panel does not apply the updated value. (23213)
- When adding new topic references in DITA map using **Topic reference** element dialog in the layout view, the added references are shown as broken link. (22859)
- When adding topics in DITA map using **Topic reference** element dialog in the author view, the selected topics are inserted in reverse order of being selected. (22858)
- When copying an image from any external product (for example, MS PowerPoint) and pasting it into Guides, the functionality to upload the asset on the fly for use in the file breaks. (24983)
- When searching files in the repository using **Search & filter** functionality, multiple files cannot be selected. (25104)

## Publishing

- Publishing to Salesforce fails when content contains non breaking spaces. (23664)
- For topics having errors like broken links, the Salesforce publishing fails and progress bar is shown indefinitely. (22985)
- For maps having broken links, the Salesforce publishing fails and progress bar is shown indefinitely. (24963)
- If an external link contains a UUID, it goes in post processing and converts the external link to UUID link thereby breaking the link on editor and also on the publishing sites. (22574)
- The `xref` converts to relative link even when the **scope** of link is set to **external**. (23059)
- Native PDF generation fails for content with **chunk** attribute set to **to-content**. (21772)
- The **Edit properties** dialog for a baseline does not show the previously saved criteria for dynamic baseline. (23964)


## Translation

- For non-legacy translation (for non-UUID), moving a topic in the source path to a different folder results in broken references in the target locale. (24152)
