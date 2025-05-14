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


## Review

- The document view in the Review UI does not wrap the content for some screen sizes, requiring users to scroll horizontally to view the full content. (GUIDES-25292)

## Known Issues

Adobe has identified the following known issues for the 2025.06.0 release:

- With the **Tags View** off, any text typed after a `codeblock` after pressing the downward arrow key is moving the text into a new `p` element, instead of continuing inline after the code block. (GUIDES-29083)
- When using the **Find and Replace** option, after applying the **Replace Single Occurrence** operation on a file for the first instance, no further actions can be performed on the remaining files. (GUIDES-28930)

