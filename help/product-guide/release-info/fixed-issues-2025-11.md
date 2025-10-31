---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2025.11.0 release
description: Learn about the bug fixes in the 2025.11.0 release of Adobe Experience Manager Guides as a Cloud Service.

---
# Fixed issues in the 2025.11.0 release 

This article covers the bugs fixed in various areas of the 2025.11.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2025.11.0 release](whats-new-2025-11-0.md).

Learn about [upgrade instructions for the 2025.11.0 release](upgrade-instructions-2025-11-0.md).

## Authoring



## Publishing

- When publishing a DITA map using baseline on AEM Sites (with legacy component mapping), the map elements with the attribute `processing-role = resource-only` are also getting published. (GUIDES-37649)
- After upgrading Experience Manager Guides to 2025.08.0 version, the option to enable or disable the custom **Acrolinx** tab no longer appears in **Workspace settings**. (GUIDES-35261)
- When you re-upload an edited image through the Experience Manager Guides UI, the image's original rendition gets updated but the associated DITA content continues to display the previous version of the image. (GUIDES-33693)
- If an empty `prop` element with no attributes or values is added to a DITAVAL file, then additional `prop` elements cannot be added. (GUIDES-33597)
- When attempting to move two or more folders from their source location to a different location (using the Bulk Move tool), the operation fails if the folder names start with the same string (e.g., Product and ProductImages). (GUIDES-29096)
- When performing actions on Assets via the Assets UI, the generated error logs contain an incorrectly term `predecessor` instead of `successor`in the log message. (GUIDES-35607)
- Running bulk activation from the Editor interface generates excessively large logs. (GUIDES-20746)
- When a custom CSS is applied to a topic or map, refreshing the browser while in the Editor causes the applied CSS to revert to the default style in the Preview mode. (GUIDES-31098)
- Large or complex MathML equations fail to display in the Editor. (GUIDES-29095)
- In the Assets UI, deleting a file directly from Search results removes it without any warning, even if it is referenced in one or more DITA topics. 
- When you search for a file in the Assets UI and delete it directly from the Search results, the asset is removed without any warning - even if it is referenced in existing DITA content. (GUIDES-17232)
- When an Xref element points to a map file, the map files are displayed with thier file names instead of map title. 
- After making a change to a DITA file in the Editor, if you switch to Source view and use **Undo** followed by **Redo**, the changes are not reapplied. (GUIDES-24914, GUIDES-25034) 

- An AEM Sites output (with legacy component mapping) is generated without any Search page when `searchPageTemplate` and  `searchPathProp` properties are removed from the associated output template. (GUIDES-34242)
- Ditaval filtering or conditional processing that include operations such as `Exclude` and `Include` do not work for Salesforce publishing. 
- Unable to create a Native PDF preset for a map if a folder with the same name exists in its content hierarchy. (GUIDES-33012)
- When Native PDF output is generated using a dynamic baseline, the term **PDFProject** is displayed as the PDF title instead of the actual map title. (GUIDES-31102)
- Generating output based on different print attribute values (such as Yes, No, and printonly) do not work for Native PDF publishing. (GUIDES-31101)
- When a folder containing DITA maps is moved using the Assets UI or **Bulk move** option, existing map collections and bulk activation collections that reference those maps become inaccessible and show blank pages. (GUIDES-28355)
- When you move a folder containing a map with condition presets applied to its Output preset, the conditions are not applied in the generated output after the move. (GUIDES-28352)
- In a DITA map, when a copy-to attribute is added to a topic reference, the page name is not getting picked up in the generated ouput of AEM Sites (with legacy component mapping).   
- When you generate AEM Sites output using legacy component mapping, topics that use the `copy-to` attribute get published with the incorrect page name. The page uses the original topic's name instead of the name set in the `copy-to` attribute. (GUIDES-22155)

## Translation



## Review



## Known issues

Adobe has identified the following known issues for the 2025.11.0 release:



