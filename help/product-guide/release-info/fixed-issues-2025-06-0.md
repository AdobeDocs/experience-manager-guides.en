---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2025.06.0 release
description: Learn about the bug fixes in the 2025.06.0 release of Adobe Experience Manager Guides as a Cloud Service.

---
# Fixed issues in the 2025.06.0 release 

This article covers the bugs fixed in various areas of the 2025.06.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2025.06.0 release](whats-new-2025-06-0.md).

Learn about [upgrade instructions for the 2025.06.0 release](upgrade-instructions-2025-06-0.md).

## Authoring

- When opening a DITA map with the unified shell enabled, the editor refreshes intermittently. (GUIDES-26919)
- Failing to close JCR session connections while updating or creating topics result in memory leaks and service downtime. (GUIDES-26282)
- Dragging the columns changes their width from percentage to pixel values, which results in distorted or misaligned tables.(GUIDES-23128)
- When content is pasted into a `code block` or when spaces are added in the `code block` and the view is switched, the spacing is lost. (GUIDES-27478)
- When adding a map to the `bookmap`, it gets stored in `fmditatopicrefs` instead of `fmditamaprefs`. (GUIDES-25480)
- The **Insert image** dialog fails to render correctly on a high-resolution or zoomed-out screens causing the figure title and alternate text fields to disappear. (GUIDES-26459)


## Publishing

- Native PDF publishing continues indefinitely, if the DITA content has a weblink without having scope as `external`. (GUIDES-26434) 
- Publishing of Native PDFs and AEM sites stalls and gets queued, when there are errors in the content. (GUIDES-26516)
- When creating a new baseline with a large number of labels, it prevents all the labels from being fetched. (GUIDES-16232)
- When generating AEM Site pages with titles that include multiple words separated by spaces, the map title displays hyphens instead of spaces. (GUIDES-27903)
- For Native PDF, an invalid metadata property name is not getting resolved and is displayed as `unresolved property name` in **document properties**. (GUIDES-25680)
- Multi-line text within `codeblock` causes text overflow issues during PDF generation. (GUIDES-15541)
- When adding maps to the map collection, assets other than maps (likes topics etc.) are displayed, and the translated map languages are also not properly sorted.(GUIDES-25085)


## Review

- The document view in the Review UI does not wrap the content for some screen sizes, requiring users to scroll horizontally to view the full content. (GUIDES-25292)


## Known Issues

Adobe has identified the following known issue for the 2025.06.0 release:

- When using the Find and Replace option, after applying the Replace Single Occurrence operation on a file, no further actions can be performed in the Find and Replace panel. (GUIDES-28930)

- In a folder profile, when an already indexed asset is deleted from the UI, the corresponding indexed path is not removed, and an attempt to re-index fails with an error message. As a workaround, you must remove the obsolete path that no longer exists before initiating the re-indexing.(GUIDES-29147)

- If a map contains cyclic dependencies and you open the Map Preview, the Source, Author, and Layout views become inaccessible until the page is refreshed. As a workaround, you must refresh the page to restore access to these views. (GUIDES-28334)
