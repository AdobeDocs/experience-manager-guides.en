---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 5.1.0 Service Pack 3 release
description: Learn about the bug fixes in the 5.1.0 Service Pack 3 release of Adobe Experience Manager Guides
role: Leader

---
# Fixed issues in the 5.1.0 Service Pack 3 release (December 2025)


This article covers the bugs fixed in various areas of 5.1.0 Service Pack 3 release of Adobe Experience Manager Guides.

Learn about [upgrade instructions for the 5.1.0 Service Pack 3 release](upgrade-instructions-5-1-0-sp3.md).


## Authoring

- Using `scope="external"` for a reference to DAM content within a topic or map causes the asset's relative path to be substituted with a GUID. (GUIDES-35605)
- Custom CSS applied at a folder-level profile for topics or maps is reverted to the default style in Preview mode upon browser refresh. (GUIDES-31098)
- Unable to add multiple **Version labels** to a topic from the **Save as new version** dialog. (GUIDES-32716)

## Baseline

- Error occurs while loading **Version labels** for a Baseline when the associated DITA map contains missing `topicref` elements. (GUIDES-37743)

## Review

- When a Reviewer completes a review task or initiator updates review task without entering comments, the notification email sent displays the most recent previous comment. (GUIDES-33590)

## Publishing 

- When you generate AEM Sites output using legacy component mapping, topics that use the `copy-to` attribute get published with the `copy-from` topic's name instead of the name set in the `copy-to` attribute. (GUIDES-22155)
- When Native PDF output is generated using a dynamic baseline, the term **PDFProject** is displayed as the PDF title instead of the actual map title. (GUIDES-31102)
- Unable to set custom rendition for a specific output preset. (GUIDES-38477)




