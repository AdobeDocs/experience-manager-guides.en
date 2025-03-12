---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2025.04.0 release
description: Learn about the bug fixes in the 2025.04.0 release of Adobe Experience Manager Guides as a Cloud Service.

---
# Fixed issues in the 2025.04.0 release 

This article covers the bugs fixed in various areas of the 2025.04.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2025.04.0 release](whats-new-2025-04-0.md).

Learn about [upgrade instructions for the 2025.04.0 release](upgrade-instructions-2025-04-0.md).


## Publishing

- In the legacy AEM Sites output, section links within nested topics of a map do not resolve correctly when manually set in Source mode. Instead of navigating to the intended section, they redirect to the main topic that contains the nested topic. (26103)
- Inconsistent error logging for HTML5 output generation failures in different environments, despite using the same Experience Manager Guides version. (25969) 

## Editor 

- Unable to access file properties from the repository panel if the parent folder name includes "&" character. (25762)
- Options to save changes and save as a new version work for even locked files in the Editor. (23875)

## Authoring


- Special character insertion box in the Editor fails to load for German locale. (24537) 
- Comments and labels added while saving a new version of a DITAVAL file are not getting saved in the Version History with the new version. (24076)
- When working with a map that contains a large number of references, the right panel in the Editor does not refresh while switching between the referenced files. (23344)
- The order of customized filters set in the repository filters is not retained as defined. Additionally, performing an advanced filtering operation on the custom fields results in an application error. (21193)
- In the Baseline and Translation UI, the document state of the working copy of a topic is displayed for all versions of a topic instead of the selected version. (20674) 
- Unable to remove the empty lines in a code block element from Author view. (20672)
- New ids fail to generate for elements defined in snippets or templates, even when the **auto generate ID** option is enabled in `XMLEditorConfig`. (21734)
- Creating a new dita asset from dita templates copies the replication properties from corresponding dita templates. (21193) 


## Publishing

 - Unable to embed video links in Native pdf even when the **Embed Multimedia Files** option is enabled in the PDF preset. (9989)

## Review

- Updating the details of a review task in the Review dashboard does not confirm whether the update was successful or unsuccessful. (8051) 




 


 

 

