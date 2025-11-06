---
title: Release Notes | What's New in Adobe Experience Manager Guides 2025.11.0 release
description: Learn about the new and enhanced features in the 2025.11.0 release of Adobe Experience Manager Guides
role: Leader

---
# What's new in the 2025.11.0 release (November 2025)

This article covers the new and enhanced features introduced with the 2025.11.0 release of Adobe Experience Manager Guides as a Cloud Service.

For the list of issues fixed in this release, view [Fixed issues in the 2025.11.0 release](fixed-issues-2025-11-0.md).

Learn about [upgrade instructions for the 2025.11.0  release](../release-info/upgrade-instructions-2025-11-0.md).


## Discover more with Repository on Home page and advanced Search and Filter experience

The Repository, accessible directly from the Home page, serves as a centralized space for improved discoverability of folders and files. It features dedicated **Folder navigation panel** and a customizable **tabular view of Repository**. The revamped Search and filter experience makes finding and locating files significantly easier. For more details, view [Repository on the Home page](../user-guide/home-repository-view.md).

![](assets/repository-view-home.png){align="left"}

Within Editor, the Search and filter experience for files is now aligned with the Home page. A new [Search panel](../user-guide/explorer-editor.md) located at the bottom of the Editor interface has been introduced to display search results. Additionally, the Repository has been renamed **Explorer** in Editor, allowing you to browse folders and files as before.

![](assets/search-panel-explorer.png){align="left"}


## Enhanced indexing for Smart suggestions in AI Assistant

You can now easily track the status of each indexing attempt for Smart suggestions in AI Assistant with new status indicators: Indexing completed, Not in sync, In progress, and Indexing failed. The last indexing timestamp is now recorded at the folder or profile level for better traceability. Additionally, parent-child folder restrictions are now enforced when specifying a folder or file path for indexing.

For more details, view [Configure AI Assistant for smart help and authoring](../cs-install-guide/conf-folder-level.md#folder-profile-restrictions).

## Performance improvements

### Automated B-Tree cleanup for optimal performance

To maintain system efficiency and prevent resource congestion, a new background process will regularly clean up system-level B-Trees. This ensures that assets which no longer exist or were added temporarily do not occupy unnecessary space. 

The system intelligently identifies candidates for cleanup and performs automated removal. Additionally, this feature is configurable, giving administrators control over its behavior based on operational needs.

For more details, view [Configure B-tree clean up job](../cs-install-guide/configure-btree-cleanup-cs.md).

### Improved handling of DITA maps with large number of keys

You can now work seamlessly with DITA maps that contain a large number of keys. This enhancement ensures faster loading and improved performance, making it easier to manage complex maps without interruptions.

After a build upgrade, the system may experience a brief period of increased load due to an automated one-time script (OTS) that runs in the background. This is expected behavior and will stabilize shortly.

### Automatic system enabled asset processing

This update offers a streamlined way to keep your assets up to date. The system now automatically triggers asset processing for the /content/dam folder every 15 minutes. This scheduled process ensures that any newly added or unprocessed assets (within the 15 minutes cycle) are picked up and processed, improving efficiency and consistency across your content repository.

For more details, view [Asset processing](../user-guide/asset-processor.md).




