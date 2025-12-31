---
title: Release Notes | What's New in Adobe Experience Manager Guides 2026.01.0 release
description: Learn about the new and enhanced features in the 2026.01.0 release of Adobe Experience Manager Guides
role: Leader

---
# What's new in the 2026.01.0 release (January 2026)

This article covers the new and enhanced features introduced with the 2026.01.0 release of Adobe Experience Manager Guides as a Cloud Service.

For the list of issues fixed in this release, view [Fixed issues in the 2026.01.0 release](fixed-issues-2026-01-0.md).

Learn about [upgrade instructions for the 2026.01.0 release](../release-info/upgrade-instructions-2026-01-0.md).

## New Document state filter for Repository on the Home page

Now, filter your Repository search based on the current document state of the files. With the new **Document state** filter, you can narrow down your search using the available filter values defined in the `ui_config.json` file within your Folder profile.  

This means: 

- If you are using the Global Profile, the filters values configured in the Global profile are applied. 
- If you select a specific Folder profile, the filters values defined in that profile are fetched. 

![](assets/document-state-filter-repository.png){width="300" align="left"}

The default filter values available for Document state are: Draft, Edit, In-Review, Approved, Reviewed, and Done. For details on customizing the default document state filters values, view [Configure document state filters](../cs-install-guide/config-doc-state-filters.md). 

