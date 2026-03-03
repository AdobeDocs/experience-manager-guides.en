---
title: Release Notes | What's New in Adobe Experience Manager Guides 2026.03.0 release
description: Learn about the new and enhanced features in the 2026.03.0 release of Adobe Experience Manager Guides
role: Leader

---
# What's new in the 2026.03.0 release (March 2026)

This article covers the new and enhanced features introduced with the 2026.03.0 release of Adobe Experience Manager Guides as a Cloud Service.

For the list of issues fixed in this release, view [Fixed issues in the 2026.03.0 release](fixed-issues-2026-01-0.md).

Learn about [upgrade instructions for the 2026.03.0 release](../release-info/upgrade-instructions-2026-01-0.md).



## Editor enhancements

The following Editor enhancements have been made as part of this release:

- Now, you can search citations across all Journal fields, such as *Title*, *Journal title*, *Author*, *Year*, *Volume*, *Number*, and *Pages*, using the **Any field** option in the **Add citation** dialog. The search returns the closest matching citation based on the entered text.

    For more details, view [Add and manage citations in your content](../user-guide/web-editor-apply-citations.md). 

## Improved review tasks creation experience with project-based reviewer assignments  

The review task creation experience is enhanced to strengthen validation and improve reviewer assignment. The **Assign To** field is now mandatory and must be specified to create a review task. Reviewer assignment is dependent on project selection - the **Assign To** field remains disabled until an active project is selected. After a project is selected, the **Assign To** field is enabled and lists only the users and user groups associated with that project. This ensures that review tasks are assigned only to valid project members and prevents unintended reviewer selection.

![](assets/create-review-task-023.png)

To further improve usability, the **Assign To** field now supports typeahead search, allowing you to quickly locate users or user groups by typing text. Together, these enhancements make reviewer selection more accurate, efficient, and aligned with project-specific review workflows.

For more details, view [Send topics for review](../user-guide/review-send-topics-for-review.md). 

## Download maps with original file names and associated metadata

You can now download a map while preserving its original file names for both file hierarchy options: Flatten file hierarchy and Retain file hierarchy. This enhancement gives you greater flexibility and control over how file names are handled in downloaded content, regardless of the hierarchy option you choose.

Additionally, the downloaded package includes a `metadata.json` file, making the associated metadata easily accessible and reusable outside Experience Manager Guides.

For more details, view [Download files](../user-guide/authoring-download-assets.md).

## Use regular expressions (regex) to enable or disable post processing

Experience Manager Guides now supports using regular expressions (regex) to enable or disable post-processing for folders. This enhancement allows administrators to define post-processing rules that apply to multiple folders or entire folder hierarchies using a single configuration, instead of specifying individual folder paths.

For more details, view [Use regex to enable or disable post processing](../cs-install-guide/conf-folder-post-processing.md#use-regex-to-enable-or-disable-post-processing). 

## Access language copies directly from the Editor interface

With this release, a new **Translations** section is introduced in the Right panel under *File properties** in the Editor. This section provides direct access to all available language copies for the currently opened asset (map, topic, image, etc.). You no longer need to navigate to the Assets UI to view or access these language copies. 

For each language copy, you can hover-over the file to locate its path in the repository or simply select it to open in the Editor. In addition to opening files, you can also perform many actions using the **Options** menu. Some of the actions that you can perform include Edit, Preview, Copy UUID, Copy Path, Add to collections, and Properties.

For more details view, [Right panel in the Editor](../user-guide/web-editor-right-panel.md#file-properties). 

## Enhancements to the Schematron validation panel

The following enhancements have been made to the Schematron user interface for better clarity, usability, and validation outcomes: 

- A clear empty‑state message: *No Schematron file is added. Add Schematron file to validate your dita topics and maps* is now displayed when no Schematron file is added.

    ![](assets/schematron-panel.png){width="350" align="left"}
- When multiple Schematron files are added, they are organized under a consolidated accordion, providing better visibility into the configured Schematron files.

    ![](assets/schematron-panel-error.png){width="350" align="left"}
- Based on the role attribute defined in the Schematron file, validation results are categorized as: `fatal`, `error`, `warning`, and `info`. Each category includes a visible count along with a contextual tooltip for clearer interpretation. 

    ![](assets/schematron-validation-errors.png){width="350" align="left"}

For more details, view [Support for Schematron files](../user-guide/support-schematron-file.md).
