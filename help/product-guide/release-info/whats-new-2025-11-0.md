---
title: Release Notes | What's New in Adobe Experience Manager Guides 2025.11.0 release
description: Learn about the new and enhanced features in the 2025.11.0 release of Adobe Experience Manager Guides
role: Leader

---
# What's new in the 2025.11.0 release (November 2025)

This article covers the new and enhanced features introduced with the 2025.11.0 release of Adobe Experience Manager Guides as a Cloud Service.

For the list of issues fixed in this release, view [Fixed issues in the 2025.11.0 release](fixed-issues-2025-11-0.md).

Learn about [upgrade instructions for the 2025.11.0  release](../release-info/upgrade-instructions-2025-11-0.md).


## Introducing new Repository on Home page and enhanced search experience

The Repository, now accessible directly from the Home page, serves as a centralized space for improved discoverability of folders and files. It features dedicated **Folder navigation panel** and a customizable **tabular view of Repository**. The revamped Search and filter experience makes finding and locating files significantly easier. For more details, view [Know the Repository interface](../user-guide/home-page-repository-view.md).

![](assets/repository-view-home.png){align="left"}

Within Editor, the Search and filter experience for files is now consistent with the Home page. A new [Search panel](../user-guide/search-panel-explorer.md) located at the bottom of the Editor interface is introduced to display search results. Additionally, the Repository is now renamed to **Explorer** in the Editor, allowing you to browse folders and files as before.

![](assets/search-panel-explorer.png){align="left"}


## Enhanced indexing for Smart suggestions in AI Assistant

You can now easily track the status of each indexing attempt for Smart suggestions in AI Assistant with new status indicators: Indexing completed, Not in sync, In progress, and Indexing failed. The last indexing timestamp is now recorded at the folder profile level for better traceability. Additionally, parent-child folder restrictions are enforced when specifying a folder or file path for indexing.

For more details, view [Configure AI Assistant for smart help and authoring](../cs-install-guide/conf-folder-level.md#configure-ai-assistant-for-smart-help-and-authoring).

## Performance improvements

### Automated B-tree cleanup for optimal performance

To maintain system efficiency and prevent resource congestion, a new background process  regularly cleans up the system-level B-trees. This ensures that assets which no longer exist or were added temporarily do not occupy unnecessary space. 

The system intelligently identifies candidates for cleanup and performs automated removal. Additionally, this feature is configurable, giving Administrators control over its behavior based on operational needs.

For more details, view [Configure B-tree clean up](../cs-install-guide/configure-btree-cleanup-cs.md).

### Improved handling of DITA maps with large number of keys

You can now work seamlessly with DITA maps that contain large number of keys. This enhancement ensures faster loading and improved performance, making it easier to manage complex maps without interruptions.

After the build upgrade, the system may experience a temporary increase in load, causing a delay in post-processing of newly uploaded data. This is due to an automated one-time script (OTS) running in the background. Once the script completes, system performance will return to normal. 

### Improved asset processing

An automated process is introduced to keep assets in the `/content/dam` up to date. The system triggers asset reprocessing every 15 minutes. During each cycle, assets that were newly added or remained unprocessed within the most recent 15-minute interval are picked up and reprocessed, improving efficiency and consistency across your content repository.

For more details, view [Process assets](../user-guide/asset-processor.md).




