---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2026.01.0 release
description: Learn about the bug fixes in the 2026.01.0 release of Adobe Experience Manager Guides as a Cloud Service.

---
# Fixed issues in the 2026.01.0 release 

This article covers the bugs fixed in various areas of the 2026.01.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2026.01.0 release](whats-new-2026-01-0.md).

Learn about [upgrade instructions for the 2026.01.0 release](upgrade-instructions-2026-01-0.md).

## Authoring

- When updating an inline MathML equation using the **Edit MathML** option from the context menu, the updated value is not reflected until the page is refreshed. (GUIDES-38198)
- When a topic contains many reusable elements (those with IDs) added in the **Reusable panel**, some elements may not be accessible because of fixed container height. (GUIDES-37220)
- When inserting a cross-reference to a file, the icons for maps and topics are identical.(GUIDES-36662)
- When editing a map, special symbols in the `navtitle` are not displayed in the **Author** view. (GUIDES-35435)


## Asset management

- Unable to remove Version labels from **Version history** panel in Assets UI. (GUIDES-38276)
- Unable to add multiple **Version labels** to a topic from the Save as new version dialog. (GUIDES-32716)
- When uploading assets with filename containing invalid characters, the asset fails to upload and displays an incorrect message **file is locked by other user** despite the asset being unlocked. (GUIDES-32680)
- For an output preset, the search filter functionality is not working in AEM Assets for DITAVAL filtering, as the corresponding files are not being displayed when the DITAVAL filter is selected.(GUIDES-35418)

## Publishing

- When generating AEM Sites output, the map titles containing keywords and topic titles with `<ph>` element are not getting included in the published output. (GUIDES-36641)   
- When publishing using a custom preset with content that contains links to PDFs without the scope set as external, the process fails to complete. (GUIDES-21708)
- When performing bulk activation, the package creation adds filters for all paths listed under the `fileReference` property of a page, including external and peer paths. (GUIDES-24887)
- In Native PDF output, the `abbreviated-form` element displays the `glossterm` instead of the designated `glossSurfaceForm` or `glossAcronym`. (GUIDES-26393)
- For Native PDF output, the `<alt>` element for images is ignored, preventing alternate text from being applied for accessibility. (GUIDES-29087)
- When downloading temporary files for a map with a baseline during publishing for a preset, the `metadata.xml` file incorrectly references the `versionPath` instead of the `dampath`.(GUIDES-29815)
- When creating or editing a topic that includes a citation, if the Author field is not added in the citation dialog, the PDF is not generated. (GUIDES-37934)
- A CSS file (`rhdefault.css`) is getting incorrectly added to the PDF template, even when the template does not include any CSS file, resulting in **missing CSS file** error logs. (GUIDES-31752)
- For an output preset, the search filter functionality is not working in AEM Assets for DITAVAL filtering, as the corresponding files are not being displayed when the DITAVAL filter is selected. (GUIDES-35418)

## Platform

- When trying to save the content or save a new version of the topic, you encounter an error **Failed to save file**. (GUIDES-37837) 
- Using `scope="external"` for a reference to DAM content within a topic or map causes the asset's relative path to be substituted with a GUID. (GUIDES-38783)

## Reports

- The **Broken list** report is incorrectly including valid `keyrefs` and `conkeyrefs` that are properly resolved within the scope of the current map. (GUIDES-27774)












