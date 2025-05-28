---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 5.0.0 Service Pack 1 release
description: Learn about the bug fixes in the  4.6.0 Service Pack 4 release of Adobe Experience Manager Guides
role: Leader
---
# Fixed issues in the 5.0.0 Service Pack 1 release (June 2025)


This article covers the bugs fixed in various areas of 5.0.0 Service Pack 1 release of Adobe Experience Manager Guides.

Learn about [upgrade instructions for the 4.6.0 Service Pack 4 release](upgrade-instructions-5-0-0-sp1.md).

## Authoring

- When content is pasted into a code block or when spaces are added in the code block and the view is switched, the spacing is lost. (GUIDES-27478)
- In a <codeblock>, wrapping words with inline tags like <b>, <i>, or <varname> in the Source Editor removes surrounding spaces after switching views.

## Asset Management

- When you open a topic in Author view after refreshing the browser, the previously applied tags in the **File Properties** panel are lost, and adding new tags overwrites the existing ones. (GUIDES-29078)
- For a DITA map with a large number of dependent files, the **Manage** button in the metadata panel either becomes unresponsive or responds slowly. (GUIDES-29778)

## Translation 

- After the maintenance update, the Start button needed to initiate the translation job was not available from, preventing you to begin the translation workflow (GUIDES-28237) .

## Platform

- When modifying an already applied preset using **Apply Preset Changes** in a folder profile, the updates are not reflected on the map. (GUIDES-26694)
