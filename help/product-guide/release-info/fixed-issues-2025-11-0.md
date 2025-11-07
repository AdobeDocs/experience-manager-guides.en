---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2025.11.0 release
description: Learn about the bug fixes in the 2025.11.0 release of Adobe Experience Manager Guides as a Cloud Service.

---
# Fixed issues in the 2025.11.0 release 

This article covers the bugs fixed in various areas of the 2025.11.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2025.11.0 release](whats-new-2025-11-0.md).

Learn about [upgrade instructions for the 2025.11.0 release](upgrade-instructions-2025-11-0.md).

## Authoring

- If an empty `prop` element with no attributes or values is added to a DITAVAL file, then additional `prop` elements cannot be added. (GUIDES-33597)
- After upgrading Experience Manager Guides to 2025.08.0 version, the option to enable or disable the custom **Acrolinx** tab no longer appears in **Workspace settings**. (GUIDES-35261)
- Custom CSS applied at a folder-level profile for topics or maps is reverted to the default style in Preview mode upon browser refresh. (GUIDES-31098)
- **Undo** and **Redo** operations do not work as expected in the Source view of the Editor for DITA files. (GUIDES-24914, GUIDES-25034) 
- When referencing a DITA map in a topic using the `Xref` element, the file name of the referenced map is displayed instead of the title of the map. (GUIDES-21759)
- When adding multiple Schematron files for validation through the right panel of the Editor interface, an error **Schematron file(s) don't exist or have errors** is displayed even if the files added are valid and have no errors. (GUIDES-33731)
- Large or complex MathML equations fail to display in the Editor. (GUIDES-29095)

## Asset management

- When you re-upload an edited image through the Experience Manager Guides UI, the image's original rendition gets updated but the associated DITA content continues to display the previous version of the image. (GUIDES-33693)
- When attempting to move two or more folders from their source location to a different location (using the Bulk Move tool), the operation fails if the folder names start with the same string (e.g., Product and ProductImages). (GUIDES-29096)
- Deleting a searched asset from the Omnisearch Assets UI bypasses the **Force delete** warning dialog and deletes the asset directly, even when it's referenced in existing DITA content. (GUIDES-17232)

## Publishing

- When publishing a DITA map using baseline on AEM Sites (with legacy component mapping), the map elements with the attribute `processing-role = resource-only` are also getting published. (GUIDES-37649)
- In some cases, the `jcr:content/fmUuidOfSource` property is found missing in the AEM Sites output pages (with legacy component mapping), leading to newly created content pages not discoverable.
- Content filtering via DITAVal filters and conditional presets do not work for Salesforce publishing. (GUIDES-33515)
- Unable to create a Native PDF preset for a map if a folder with the same name exists in its content hierarchy. (GUIDES-33012)
- When Native PDF output is generated using a dynamic baseline, the term **PDFProject** is displayed as the PDF title instead of the actual map title. (GUIDES-31102)
- Generating Native PDF output with certain `print` attribute values in topic references do not work as expected. (GUIDES-31101)
- When a folder containing DITA maps is moved using the Assets UI or **Bulk move** option, existing map collections and bulk activation collections that reference those maps fail to load. (GUIDES-28355)
- When you move a folder containing a map with condition presets, the conditions are not applied in the generated output after the move. (GUIDES-28352)
- When you generate AEM Sites output using legacy component mapping, topics that use the `copy-to` attribute get published with the `copy-from` topic's name instead of the name set in the `copy-to` attribute. (GUIDES-22155)
- Activating one or more DITA maps from **Bulk publish dashboard** generates excessively large logs. (GUIDES-20746)

## Platform

- Error logs that are generated while uploading an asset via the Assets UI or creating a new file from the Editor interface, incorrectly use the term `predecessor` instead of `successor` in the log message. (GUIDES-35607)

## Known issues

Adobe has identified the following known issues for the 2025.11.0 release:

- Creating a duplicate topic using `copy-to` attribute and referencing it with `scope=peer` attribute causes redirection issues in AEM Sites output, where links are redirected from AEM Sites (with composite component mapping) to AEM Sites (with legacy component mapping), and vice-versa.
- Reindexing of folders for using Smart suggestions in AI Assistant do not happen if the added folders are moved from the Assets UI to a different location using the **Bulk Move** tool.











