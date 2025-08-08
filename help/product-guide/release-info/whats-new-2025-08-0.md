---
title: Release Notes | What's New in Adobe Experience Manager Guides 2025.08.0 release
description: Learn about the new and enhanced features in the 2025.08.0 release of Adobe Experience Manager Guides
role: Leader
---
# What's new in the 2025.08.0 release (August 2025)

This article covers the new and enhanced features introduced with the 2025.08.0 release of Adobe Experience Manager Guides as a Cloud Service.

For the list of issues fixed in this release, view [Fixed issues in the 2025.08.0 release](fixed-issues-2025-08-0.md).

Learn about [upgrade instructions for the 2025.08.0  release](../release-info/upgrade-instructions-2025-08-0.md).


## Enhanced review workflow

With this release, the review workflow mechanism has been significantly enhanced to introduce various new features like improved task management workflows with actionable notifications, ability to tag users to seek immediate attention, and access to project and task details from the review panel for ease of use.

These workflow improvements enhance collaboration and efficiency by streamlining task management and enabling prompt user engagement. Users can quickly act on notifications, access relevant details, and stay aligned within the review environment.

For more details, view [Introduction to review](../user-guide/review.md)

## Configurable AI Assistant actions in the Editor settings

The latest update introduces enhanced configuration for **Authoring quick actions** in AI Assistant, empowering Administrators to customize the authoring environment according to specific workflows and preferences.

Once the **AI Assistant** toggle is enabled, Administrators can selectively choose which quick actions are visible under the **Authoring** tab, helping streamline author interactions. These visibility settings are specific to each folder profile.

Learn more about [AI assistant in Editor settings](../user-guide/web-editor-settings.md#general) in Experience Manager Guides.

![](assets/authoring-quick-actions.png){width="350" align="left"}


## Improved experience for creating and using DITAVAL files

This update brings new capabilities for customizing the content publishing through enhanced flagging support in DITAVAL files. You can now apply start and end flags around specific content, including images, and enrich flagged sections with formatting options like bold, italics, and more. To handle condition overlaps, the **Style conflict** can be configured, which includes setting a default background and text color, ensuring clarity and consistency in the output. These flags are fully supported in Native PDF generation, and the resulting output accurately and comprehensively reflects all applied styling elements.

Additionally, this update enhances output preset creation by enabling editable DITAVAL fields across formats, allowing users to manually specify DITAVAL paths. For Native PDF, multiple DITAVAL files can be added, each displayed as a tagged entry for easy identification and removal, providing greater flexibility and control over conditional content in PDF outputs.

For more details, view [Use the DITAVAL Editor](../user-guide/ditaval-editor.md) and [Output presets](../user-guide/generate-output-understand-presets.md) in Experience Manager Guides.

![](assets/ditaval-flag-style.png){width="650" align="left"}


## Improved output generation log filtering

This release introduces upgraded log filtering capabilities that offer enhanced clarity. You can now filter output generation logs by four distinct levels; **Info**, **Warn**, **Error** (including both errors and exceptions), and **Fatal**; with intuitive color-coded indicators that simplify analysis and sharpen visibility across the log stream. This improvement empowers you to navigate logs more efficiently and locate the critical issues with precision. 

For more details, view [Basic troubleshooting](../user-guide/generate-output-basic-troubleshooting.md).


## Temporary files for published output now include Author and Publish URLs in a new config file

The latest publishing enhancements to Experience Manager Guides now adds a new `system_config.xml` file to the temporary files generated while publishing HTML, PDF, and JSON outputs using DITA-OT, as well as Native PDF output. This file is automatically included in the publishing job and also accessible through temporary files when you enable the **Retain temporary files** option for the presets and generate the output.

The `system_config.xml` file contains key instance details, including the Author URL, Local URL, and Publish URL, which provide clearer context and improve the traceability of the downloaded URLs.

For more details, view [Understand the output presets](../user-guide/generate-output-understand-presets.md).

## New output path variable support for output generation

This update introduces dynamic output path configuration for output presets like Native PDF, DITA-OT PDF, JSON, HTML5, and Custom by enabling . Rather than relying on static paths, users can now define the output location using a variable (`${base_output_path}`) during installation, offering greater flexibility. the previous default path `/content/dam/fmdita-outputs` is no longer mandatory

All the output paths associated with the global folder profile presets will be automatically migrated to utilize the new base output path variable. For custom folder profiles, however, migration is not automatic; you are advised to contact the Customer Success team for assistance.

For more details, view [Understand the output presets](../user-guide/generate-output-understand-presets.md)

## UI improvements in Editor toolbar and User preferences

With this release the settings within the **User preferences** on the Home page for General and Appearance tabs have been re-structured. It includes renaming the label **Opening preferences for Maps** and moving the Non-breaking spaces toggle to Editor toolbar.

Additionally, in the Editor toolbar some quick-access toggles for enabling or disabling Track Changes, Tags, and Non-Breaking Spaces are now grouped under **Show** option within the Menu dropdown for better usability.

For more details, view [Toolbar in the Editor](../user-guide/web-editor-toolbar.md#menu-dropdown).






