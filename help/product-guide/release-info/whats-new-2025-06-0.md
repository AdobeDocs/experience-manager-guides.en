---
title: Release Notes | What's New in Adobe Experience Manager Guides 2025.06.0 release
description: Learn about the new and enhanced features in the 2025.06.0 release of Adobe Experience Manager Guides
role: Leader

---
# What's new in the 2025.06.0 release (June 2025)

This article covers the new and enhanced features introduced with the 2025.06.0 release of Adobe Experience Manager Guides as a Cloud Service.

For the list of issues fixed in this release, view [Fixed issues in the 2025.06.0 release](fixed-issues-2025-06-0.md).

Learn about [upgrade instructions for the 2025.06.0  release](../release-info/upgrade-instructions-2025-06-0.md).

## System configuration file now included in the published output under temporary files 

The latest publishing enhancements to Experience Manager Guides now adds a new `system_config.json` file to the temporary files generated while publishing HTML, PDF, and JSON outputs using DITA-OT, as well as Native PDF output. This file is automatically included when you enable the **Retain temporary files** option for the presets and generate the output.

The `system_config.json` file contains key instance details, including the Author URL, Local URL, and Publish URL, which provide clearer context and improve the traceability of the downloaded URLs.

For more details, view [Understand the output presets](../user-guide/generate-output-understand-presets.md).

## Auto sign-out prompt to prevent accidental content loss

A pop-up alert is now displayed when your Adobe Experience Manager session expires due to inactivity or auto logout. Upon resuming editing after an idle period, a pop-up alert is triggered to notify that the session has expired. This allows you to log back in or refresh before continuing, ensuring all edits are properly saved. This feature helps prevent accidental content loss and ensures a smoother, more reliable experience, even after extended periods of inactivity.

![](assets/sign-out-prompt.png)

Learn more about [auto sign-out prompt](../user-guide/auto-sign-out-prompt.md) in Experience Manager Guides. 

## Enhanced map download options in the Editor

Experience Manager Guides features a redesigned **Download map** dialog in the Editor. This enhancement introduces a new **Use actual file names** option to the dialog and reorganizes the existing options under **Flatten file hierarchy** and **Retain file hierarchy**. These improvements give you better control over how your map files are named and structured during map.

For more details, view [Download files](../user-guide/authoring-download-assets.md#download-a-dita-map-file-from-the-editor).

![](assets/download-map-dialog-new.png){width="300" align="left"}


## Enhanced `navref` handling in the Editor

The latest enhancements to the Editor improve the handling of `navref` elements in a DITA map. Now, when you add a `navref` element to a map, the **Select path** dialog opens, allowing you to easily choose the map references to include as navigation links in your map. Additionally, the title of the added map is displayed in both Author view and Layout view, providing better visibility of the included navigation during authoring.

For more details, view [Add navigation references](../user-guide/map-editor-other-features.md#add-navigation-references).
