---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 4.6.0 Service Pack 2 release
description: Learn about the bug fixes in the  4.6.0 Service Pack 2 release of Adobe Experience Manager Guides
role: Leader

---
# Fixed issues in the 4.6.0 Service Pack 2 release (January 2025)


This article covers the bugs fixed in various areas of 4.6.0 Service Pack 2 release of Adobe Experience Manager Guides.

Learn about [upgrade instructions for the 4.6.0 Service Pack 2 release](upgrade-instructions-4-6-0-sp2.md).

## Authoring

- All condition groups are lost and the conditions become flattened on updating the conditions from the folder profile. (23526)
- Changing the header rows value for a table in the **Content properties** panel does not apply the updated value. (23213)
- When adding new topic references in DITA map using **Topic reference** element dialog in the layout view, the added references are shown as broken link. (22859)
- When adding topics in DITA map using **Topic reference** element dialog in the author view, the selected topics are inserted in reverse order of being selected. (22858)

## Publishing

- Publishing to Salesforce fails when content contains non breaking spaces. (23664)
- The `xref` converts to relative link even when the **scope** of link is set to **external**. (23059)
- For topics having errors like broken links, the Salesforce publishing fails and progress bar is shown indefinitely. (22985)
- Native PDF generation fails for content with **chunk** attribute set to **to-content**. (21772)
- If an external link contains a UUID, it goes in post processing and converts the external link to UUID link thereby breaking the link on web editor and also on the publishing sites. (22574)
- When choosing **Edit properties**, the baseline dialog does not show the previously saved criteria for dynamic baseline. (23964)

## Translation

- During latest translation (for non-UUID), moving a topic in the source path to a different folder results in broken references in the target locale. (24152)
