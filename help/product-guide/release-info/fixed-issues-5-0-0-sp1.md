---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 5.0.0 Service Pack 1 release
description: Learn about the bug fixes in the 5.0.0 Service Pack 1 release of Adobe Experience Manager Guides
role: Leader
---

# Fixed issues in the 5.0.0 Service Pack 1 release (June 2025)


This article covers the bugs fixed in various areas of 5.0.0 Service Pack 1 release of Adobe Experience Manager Guides.

Learn about [upgrade instructions for the 5.0.0 Service Pack 1 release](upgrade-instructions-5-0-0-sp1.md).

## Authoring

- When content is pasted into a `codeblock` or when spaces are added in the `codeblock` and the view is switched, the spacing is lost. (GUIDES-29347)
- The surrounding space is being lost from inline tags such as `b`, `i`, and `varname` within a `code block`, as well as from XML comments, when switching views. (GUIDES- 28188)

## Asset Management

- When opening a topic in **Author** view after a browser refresh, previously applied tags in the **File Properties** panel are not retained, and adding new tags overwrites the existing ones, particularly when a large number of tags are available for selection. (GUIDES-29078)
- When generating a Metadata report for a DITA map containing a large number of assets, the **Manage** button becomes unresponsive or exhibit delayed response. (GUIDES-29778)

## Translation 

- When sending assets for translation from Guides, the assets are not being added in the Translation job, which causes the **Start** button to not appear thereby preventing you to initiate the translation job. (GUIDES-28237)

## Publishing

- When modifying the settings of an output preset within the folder profile and selecting **Apply Preset Changes**, the changes are not propagated to the output presets present in the DITA map. (GUIDES-26694)

## Review

- Attempts to create review tasks through the AEM workflow consistently fails due to the review node not being created. (GUIDES-28214)
