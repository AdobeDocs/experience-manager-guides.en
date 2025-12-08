---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2026.01.0 release
description: Learn about the bug fixes in the 2026.01.0 release of Adobe Experience Manager Guides as a Cloud Service.

---
# Fixed issues in the 2026.01.0 release 

This article covers the bugs fixed in various areas of the 2026.01.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2026.01.0 release](whats-new-2026-01-0.md).

Learn about [upgrade instructions for the 2026.01.0 release](upgrade-instructions-2026-01-0.md).

## Authoring

- When updating an inline MathML equation using the **Edit MathML** option from the context menu, the updated value is not reflected. (GUIDES-38198)
- When many topics or referenceable elements are listed in the Reusable panel, some items remain hidden or get truncated and do not appear even after searching. (GUIDES-37220)
- When inserting a cross-reference to a topic, the icons for DITA maps and topics appear identical and share the same CSS class, making them difficult to distinguish.(GUIDES-36662)
- When editing a DITA map, special symbols in the `navtitle` are not displayed in Author mode. (GUIDES-35435)


## Asset management

- When trying to delete a label from a version for a topic or map in the Version History panel of the Assets UI, the label remains and is not removed. (GUIDES-38276)

## Publishing

- When generating AEM Sites output, map titles containing keywords and topic titles with <ph> element are not included in the output. (GUIDES-36641)   

## Platform

- Error logs that are generated while uploading an asset via the Assets UI or creating a new file from the Editor interface, incorrectly use the term `predecessor` instead of `successor` in the log message. (GUIDES-35607)

## UUID migration

- GUIDES-35605

## Known issues

Adobe has identified the following known issues for the 2026.01.0 release:

- Creating a duplicate topic using `copy-to` attribute and referencing it with `scope=peer` attribute causes redirection issues in AEM Sites output, where links are redirected from AEM Sites (with composite component mapping) to AEM Sites (with legacy component mapping), and vice-versa. (GUIDES-37656)











