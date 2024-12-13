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
- When adding new topic files in DITA map using **Topic reference** option on the layout view, it shows a broken link. (22859)
- When adding topics using **Topic reference** option, the selected topics are inserted in reverse order. (22858)
- If an external link contains a UUID pattern, it breaks the link. (22574)

## Publishing

- An endless in-progress screen with no error message is shown when some articles are published on Salesforce. (23664)
- The `xref` does not retain the relative link even when the **scope** of link is set to **external**. (23059)
- For topics having errors like broken links, the Salesforce publishing fails and  progress bar is shown indefinitely. (22985)
- Native PDF generation fails for content with **chunk** attribute set to **to-content**. (21772)

## Translation

- During translation, moving a topic in the source path (en_us) to a different folder results in broken references in the target locale. (24152)
