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

## Enhancements to the Repository and Reports filters

The **Locked by** filter under the Advanced filters in the Repository and **Author** filter in the DITA map Reports now load user lists gradually as you scroll, instead of all at once. This paginated loading improves speed and makes working with large user datasets more efficient and seamless.

## Access status of review tasks directly from the Review panel

As an initiator of a review task, you can now check the status of your review task directly from the Review panel. With the latest enhancements, the **Update task** dialog within the Review panel includes a new **Check review status** option. Selecting this option takes you directly to the review dashboard, where you can view the task status for each reviewer, enabling quicker access to task progress without needing to switch contexts.

For more details, view [Request a re-review or close a review task as an Author](../user-guide/review-close-review-task.md).

![](assets/check-review-status-icon.png){width="350" align="left"}



## API to track post-processing status for folders or assets

A new API is now available for tracking the post-processing status of individual assets and folders. This is especially useful for teams using automated workflows, where publishing needs to happen only after content is fully processed. The API offers a reliable way to confirm readiness, reducing the risk of publishing failures caused by incomplete processing.

For details, view [API to track post-processing status for folders or assets](../api-reference/track-post-processing-status.md).

