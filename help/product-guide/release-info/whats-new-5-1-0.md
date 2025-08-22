---
title: Release Notes | What's New in Adobe Experience Manager Guides 5.1.0 release
description: Learn about the new and enhanced features in the 5.1.0 release of Adobe Experience Manager Guides
role: Leader
---
# What's new in the 5.1.0 release (September 2025)

This article covers the new and enhanced features introduced with version 5.1.0 of Adobe Experience Manager Guides.

For the list of issues that have been fixed in this release, view  [Fixed issues in the 5.1.0 release](fixed-issues-5-1-0.md).

Learn about [upgrade instructions for the 5.1.0 release](../release-info/upgrade-instructions-5-1-0.md).


## Enhanced review workflow

With this release, the review workflow has been significantly enhanced to better support seamless communication between authors and reviewers. Key updates include:

- Task management workflows with actionable notifications
- Ability to tag users to seek immediate attention
- Access to project and task details from review panel for ease of use

With these enhancements users can now expect:

- Efficient and timely review cycles
- Reduced manual effort during feedback exchanges

For more details, view [Introduction to review](../user-guide/review.md)

## Improved experience for creating and using DITAVAL files

This update introduces several enhancements that simplify creating, managing, and applying DITAVAL files, enabling better control over conditional content and styling across outputs.

The key highlights are as follows:

- **Enhanced flagging support in authoring DITAVAL files:** Experience Manager Guides brings new capabilities for customizing the content publishing through enhanced flagging support in DITAVAL files. You can now apply start and end flags around specific content, including images, and enrich flagged sections with formatting options like bold, italics, and more. To handle condition overlaps, the **Style conflict** can be configured, which includes setting a default background and text color, ensuring clarity and consistency in the output. These flags are fully supported in Native PDF generation, and the resulting output accurately and comprehensively reflects all applied styling elements.
For more details, view [Use the DITAVAL Editor](../user-guide/ditaval-editor.md).

    ![](assets/ditaval-flag-style-new.png){width="350" align="left"}

- **Multiple DITAVAL files support for Native PDF:** For Native PDF, now multiple DITAVAL files can be added, each displayed as a tagged entry for easy identification and removal, providing greater flexibility and control over conditional content in PDF outputs

    Additionally, this update enhances output preset creation by enabling editable DITAVAL fields across formats, allowing users to manually specify DITAVAL paths.

    For more details, view [Understand the output presets](../user-guide/generate-output-understand-presets.md) in Experience Manager Guides.

## Publishing enhancements

**Improved output generation log filtering**

This release brings in UI improvements to output generation log filtering capability. You can now filter the output generation logs better for all the four distinct levels; **Info**, **Warn**, **Error** (including both errors and exceptions), and **Fatal**; with improved and intuitive color-coded indicators that simplify analysis and sharpen visibility across the log stream. This improvement empowers you to navigate logs more efficiently and locate the critical issues with precision. 

For more details, view [Basic troubleshooting](../user-guide/generate-output-basic-troubleshooting.md).

![](./assets/log-file-new.png){align="left"}


**Temporary files for published output now include Author and Publish URLs in a new config file**

The latest publishing enhancements to Experience Manager Guides now adds a new `system_config.xml` file to the temporary files generated while publishing HTML, PDF, and JSON outputs using DITA-OT, as well as Native PDF output. This file is automatically included in the publishing job and also accessible through temporary files when you enable the **Retain temporary files** option for the presets and generate the output.

The `system_config.xml` file contains AEM instance details, including the Author URL, Local URL, and Publish URL, which provide clearer context and improve the traceability of the downloaded URLs.

For more details, view [Understand the output presets](../user-guide/generate-output-understand-presets.md).

**New output path variable support for output generation**

This update introduces dynamic `output path` configuration for output presets like Native PDF, DITA-OT PDF, JSON, HTML5, and Custom. Instead of using a fixed path, users can now define the output location using the `${base_output_path}` variable during installation, offering greater flexibility. The previous default path `/content/dam/fmdita-outputs` is no longer mandatory.

All the output paths associated with the global folder profile presets will be automatically migrated to utilize the new base output path variable. For custom folder profiles, however, migration is not automatic; you are advised to contact the Customer Success team for assistance.

For more details, view [Understand the output presets](../user-guide/generate-output-understand-presets.md).

**Exported Baseline now includes Document state**

The Export Baseline feature now includes the **document state** alongside key details such as title, file name, file type, and version number in the baseline snapshot. This enhancement improves baseline management by providing a more comprehensive overview of the baseline.

For more details, view [Create and manage baselines from Map console](../user-guide/web-editor-baseline.md#manage-baselines).

**Support for baseline driven incremental publishing via map dashboard for AEM Sites output using legacy component mapping**

The incremental output generation process has been enhanced to support publishing specific versions of topics defined in the selected baseline for AEM sites using legacy component mapping, ensuring accurate propagation of the content in the output.

For more details, view [Incremental output generation](../user-guide/generate-output-aem-site.md).

## Editor enhancements

**UI improvements in Editor toolbar and User preferences**

With this release the settings within the **User preferences** on the Home page for General and Appearance tabs have been re-structured. It includes renaming the label **Opening preferences for Maps** and moving the Non-breaking spaces toggle to the Editor toolbar.

Additionally, in the Editor toolbar some quick-access toggles for enabling or disabling Track Changes, Tags, and Non-Breaking Spaces are now grouped under **Show** option within the Menu dropdown for better usability.

For more details, view [Toolbar in the Editor](../user-guide/web-editor-toolbar.md#menu-dropdown).

**Enhanced `navref` handling in the Editor**

The latest enhancements to the Editor improve the handling of `navref` elements in a DITA map. Now, when you add a `navref` element to a map, the **Select path** dialog opens, allowing you to easily choose the map references to include as navigation links in your map. Once added, the title of the added map is displayed in both Author view and Layout view, providing better visibility of the included navigation during authoring.  Additionally, the added `navref` element resolves automatically to display the referred map in the Editor.

For more details, view [Add navigation references](../user-guide/map-editor-other-features.md#add-navigation-references).

**Session timeout prompt to prevent accidental content loss**

A pop-up message now notifies you when your Adobe Experience Manager session expires and you are logged out due to inactivity. This message is triggered when you attempt to edit content in Experience Manager Guides after the session has ended. The feature helps reduce the risk of losing unsaved work and enhances the overall reliability and fluidity of the experience, even during periods of inactivity.

![](assets/sign-out-prompt.png)

Learn more about [session timeout prompt](../user-guide/session-timeout-prompt.md) in Experience Manager Guides. 

**Enhanced search experience for Reusable content panel**

Experience Manager Guides introduces an enhanced search experience in the Reusable Content Panel. With this update, searching for any keyword now scans all the files added as reusable content, and not just the open ones, ensuring you find the exact position of the keyword across all occurrences, whether the containers are open or collapsed. Additionally, when you clear the search bar, the original state of all containers is retained, providing a more efficient and user-friendly search functionality.

For more details, view [Reusable content](../user-guide/web-editor-features.md#reusable-content).

**'Format' attribute added for reference links**

Adobe Experience Manager Guides now adds a **format** attribute for reference links within the Editor. This attribute is displayed in the **Source view** and clearly indicates the file type, such as:

- For files with a **.pdf** extension, the format will be set to **pdf**
- For files with a **.html** extension, the format will be set to **html**
- For files with a **.dita** or **.ditamap** files, the format will be set to **dita**

Additionally, files with a **.xml** extension will also have their format set to **dita**. For files without any extension, the format will be left blank. Furthermore, for any reference links  with a scope set to **external**, the format will be set to **html** regardless of the file extension in the reference links.

**Enhanced map download options in the Editor**

Experience Manager Guides introduces a new **Use actual file names** option in the **Download map** dialog. Now, when you download map files, you can choose to keep their original filenames instead of default UUIDs, making it much easier to recognize and manage your files. This option is only available if you select **Retain file hierarchy** and is disabled when you choose **Flatten file hierarchy**, giving you more flexibility in organizing your downloaded maps.

For more details, view [Download files](../user-guide/authoring-download-assets.md#download-a-dita-map-file-from-the-editor).

![](assets/download-map-dialog-new.png){width="300" align="left"}







