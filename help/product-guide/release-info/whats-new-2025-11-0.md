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

The Repository is now accessible directly from the Home page, making it easier than ever to discover folders and files within the content DAM. With a dedicated **Folder navigation panel** and a customizable **Repository view**, you can seamlessly browse and manage your content. 

The new Repository view introduces an advanced **Search and filter** experience, including the ability to mirror search results directly to the Editor through the **Search panel** option. 

Additionally, the Editor interface now features a **Search panel** at the bottom, displaying the search results from both the Home page Repository view and the Explorer panel on the Editor interface, ensuring a unified and efficient content navigation experience.

For more details, view [Repository on the Home page](../user-guide/home-repository-view.md).

![](assets/repository-view-home.png){align="left"}

## Enhancements in publishing performance and scalability

Adobe experience Manager Guides offers faster, more scalable publishing with automatic job scaling and a fault-tolerant architecture. You can run up to 40 concurrent publishing jobs, monitor real-time status, and rely on uninterrupted authoring, even during peak loads. These updates ensure efficient, resilient publishing for enterprise teams.

For more details, view [FAQ on publishing performance](../user-guide/publishing-scalability-faq.md).

## Automated B-Tree Cleanup for Optimal Performance

To maintain system efficiency and prevent resource congestion, a new background process will regularly clean up system-level B-Trees. This ensures that assets which no longer exist or were added temporarily do not occupy unnecessary space. 

The system intelligently identifies candidates for cleanup and performs automated garbage collection. Additionally, this feature is configurable, giving administrators control over its behavior based on operational needs.

For more details, view [Configure B-tree clean up job](../cs-install-guide/configure-btree-cleanup-cs.md).

## Enhanced Folder Indexing

The release introduces folder-based indexing with improved automation, validation, and visibility. 

Now we have the indexing status, Completed, In Progress, or Failed, clearly shown on the dashboard, with options to view logs and reindex failed folders. Access controls ensure profiles cannot index each other's paths, and last indexed timestamps are profile-specific. 

Additional improvements include error handling for invalid folders or character limits, continuity of previously indexed files after upgrade, automatic status updates on moves, and unique site_id generation.

For more details, view [Configure AI Assistant for smart help and authoring](../cs-install-guide/conf-folder-level.md#folder-profile-restrictions).

## Automatic system enabled Asset processing

This update offers a streamlined way to keep your assets up to date. The system now automatically triggers asset processing for the /content/dam folder every 15 minutes. This scheduled process ensures that any newly added or previously unprocessed assets are picked up and processed without manual effort, improving efficiency and consistency across your content repository.

To configure the automatic asset processing feature, navigate to the system console and enable the scheduled processing option.

For more details, view [Asset processing](../user-guide/asset-processor.md).




