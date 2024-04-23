---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2024.4.0 release
description: Learn about the bug fixes in the 2024.04.0 release of Adobe Experience Manager Guides as a Cloud Service.
---

# Fixed issues in the 2024.04.0 release 

This article covers the bugs fixed in various areas of the 2024.04.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2024.04.0 release](whats-new-2024-04-0.md).

Learn about [upgrade instructions for the 2024.04.0 release](upgrade-instructions-2024-04-0.md).

## Authoring

- The **Copy** function fails to duplicate the empty folders in Adobe Experience Manager as a Cloud Service. (15353)
- The Web Editor is unable to upload .pptx files. (14837)
-  While finding a text in the Web Editor, the cursor returns to the first occurrence of the searched text, on pressing the Enter key. (14820)
- Autosave causes multiple issues, it repositions the cursor, and requires manual clicks in the document. (14253)
- The search results are disabled after opening a file found through global **Find and Replace**. (12142)
- In the source view, `</conbody>` is occasionally inserted in incorrect locations. (11305)
- In the XML Editor, the tooltip feature fails to update the Source field. (15847)
- The **Share UUID Link** feature is not working for the images in Adobe Experience Manager. (15598)
- Overlapping text issues occur in `<reltable>` and `<fig>` tags. (15238) 
- Flickering issues occur in the **Attributes** panel. (15237)
- On deleting a character or word within the content, the cursor jumps between the block elements. (15224)
- The **Attributes** panel is not displayed in the Source view of the Web Editor. (14387)
- Unwanted, non-breaking spaces get added while editing at the end of a tag in the Web Editor. (11786)
- Content gets deleted while correcting the spelling errors in DITA files. (11610)


## Publishing

- AEM Site output generation fails when the **Delete Orphan Site** option is enabled. (15896)
- The edit functionality is not working when adding files to the Map Collection. (15813)
- In the JSON output, metadata from DITA map or topics fails to propagate to the JSON output files. (15713)
- Native PDF publishing fails while renaming the preset. (15662)
- The **sourcePath** property is incorrect on the published AEM site output. (15502)
- The language variables selection and customization are not working properly in the Native PDF Output Preset. (15399)
- Native PDF generation fails when using a template with a large stylesheet or layout. (15344)
- Content isn't rendered properly in the published output if `<conref>` is used with an absolute path.
- AEM Sites URL shortening is not working due to conflicts between the `fmdita rewriter` and `ResourceResolver`. (14793)
- The **processing-role="resource-only"**, **search="no"**, and **chunk="to-content"** attributes appear irrespectively in AEM Sites output. (14442)
- If a folder that contains 2k maps is selected as the root map, the changes applied to the output preset fail. (14852) 

## Management

- Unclosed **Resource Resolvers** cause increasing session count and PathNotFoundException errors post the October 2023 release of Experience Manager Guides as a Cloud Service. (15604)
- The feature flag **fmdita.useapproval** is not working as expected. (15310)
- Creating a baseline using the Java API does not work with the June 2023 release of Experience Manager Guides as a Cloud Service. (14787)
- The `/bin/fmdita/import` API remains stuck in pending request indefinitely when the uploading assets exceed 500 MB. (14743)

## Review

- Deleting review nodes disrupts the ability to open and view comments in Adobe Experience Manager Guides. (15366)
- In the Web Editor, the Review panel loads slowly. (14680)

## Translation

- **Accept Translation** fails to complete the translation of temporary files. (14665)

