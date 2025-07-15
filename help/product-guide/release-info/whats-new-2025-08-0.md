---
title: Release Notes | What's New in Adobe Experience Manager Guides 2025.08.0 release
description: Learn about the new and enhanced features in the 2025.08.0 release of Adobe Experience Manager Guides
role: Leader
---
# What's new in the 2025.08.0 release (August 2025)

This article covers the new and enhanced features introduced with the 2025.08.0 release of Adobe Experience Manager Guides as a Cloud Service.

For the list of issues fixed in this release, view [Fixed issues in the 2025.08.0 release](fixed-issues-2025-08-0.md).

Learn about [upgrade instructions for the 2025.08.0  release](../release-info/upgrade-instructions-2025-08-0.md).

## Temporary files for published output now include Author and Publish URLs in a new config file

The latest publishing enhancements to Experience Manager Guides now adds a new `system_config.json` file to the temporary files generated while publishing HTML, PDF, and JSON outputs using DITA-OT, as well as Native PDF output. This file is automatically included in the publishing job and also accessible through temporary files when you enable the **Retain temporary files** option for the presets and generate the output.

The `system_config.json` file contains key instance details, including the Author URL, Local URL, and Publish URL, which provide clearer context and improve the traceability of the downloaded URLs.

For more details, view [Understand the output presets](../user-guide/generate-output-understand-presets.md).
