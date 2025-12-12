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
- When saving a topic or map as a new version, you can't add multiple labels either directly or selected from the dropdown, and instead retains only a single combined label. (GUIDES-32716)
- When uploading an image with a filename containing invalid characters, the asset fails to upload and displays a misleading message **file are locked by other user** despite the asset being unlocked. (GUIDES-32680)
- For an output preset, the search filter functionality is not working in AEM Assets for DITAVAL filtering, as the corresponding files are not being displayed when the DITAVAL filter is selected.(GUIDES-35418)

## Publishing

- When generating AEM Sites output, map titles containing keywords and topic titles with <ph> element are not included in the output. (GUIDES-36641)   
- When publishing using a custom preset with content that contains links to PDFs without the scope set as external, the process fails to complete. (GUIDES-21708)
- When performing bulk activation, the package creation adds filters for all paths listed under the fileReference property of a page, including external and peer paths. (GUIDES-24887)
- In native PDF output, the `abbreviated-form` element displays the `glossterm` instead of the designated `glossSurfaceForm` or `glossAcronym` when linked to a glossary key or content key. (GUIDES-26393)
- For Native PDF output, the `<alt>` element for images is ignored, preventing alternate text from being applied for accessibility. (GUIDES-29087)
- When downloading temporary files for a map with a baseline during publishing for a preset, the `metadata.xml` file incorrectly references the `versionPath` instead of the `dampath`.(GUIDES-29815)
- When creating or editing a topic that includes a citation, if the Author field is empty in the citation dialog, the PDF is not generated. (GUIDES-37934)
- GUIDES-31752 - shubham

## Platform

- When trying to save the content or save a new version of the topic, you encounter error **Failed to save file**. (GUIDES-37837) 

## UUID migration

- Using scope="external" for a reference to DAM content within a topic or map causes the asset's relative path to be substituted with a GUID. (GUIDES-38783)

## Reports

- The Broken List report is capturing valid `keyrefs` and `conkeyrefs` that are properly resolved within the scope of the current map. (GUIDES-27774)

## Known issues

Adobe has identified the following known issues for the 2026.01.0 release:











