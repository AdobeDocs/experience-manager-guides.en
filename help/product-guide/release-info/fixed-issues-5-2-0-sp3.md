---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 5.2.0 Service Pack 3 release
description: Learn about the bug fixes in the 5.2.0 Service Pack 3 release of Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
---
# Fixed issues in the 5.2.0 Service Pack 3 release (November 2026)

This article covers the bugs fixed in various areas of 5.2.0 Service Pack 3 release of Adobe Experience Manager Guides.

Learn about [upgrade instructions for the 5.2.0 Service Pack 3 release](upgrade-instructions-5-2-0-sp3.md).

## Editor 2.0

- Copying a table from Author mode and pasting it into Author mode removes attributes such as `colwidth` and any other attributes defined on `colspec`, causing the column width settings to be lost. (GUIDES-52916)
- When a table is pasted from Microsoft Word, the header row cells are created but their content is lost. (GUIDES-49847)
- When code is pasted into a `codeblock` element, from Microsoft Word or similar text editors, by using Ctrl+V, line breaks and leading spaces are lost and the code is flattened into a single line. (GUIDES-33247)

## Asset management

- The asset status API does not return the correct status for assets whose path contains a comma. (GUIDES-49065)
- Renaming an asset with a GUID-based filename to a different GUID using the Move operation in the Assets UI replaces the asset’s original unique GUID with the new GUID. (GUIDES-43006)
- When a DITA asset is moved in the Assets UI, the **Name after move** field is disabled and the asset cannot be renamed as part of the move. (GUIDES-59684) 
- When a non-DITA asset, such as an image, that was migrated from a non-UUID setup to a UUID setup is reverted or branched to another version, its UUID changes. Existing references to the asset no longer resolve, and the image appears broken in the topics that reference it. (GUIDES-58414) 

## Publishing

- When publishing a DITA map with `processing-role=resource-only` elements on AEM Sites (with legacy component mapping), orphan site pages are generated for those elements in additional scenarios such as `topicgroup` elements and specific content configurations. (GUIDES-37650)
- Branch filtering generates extra pages for unwanted topics used as `keydef` (which are marked `resource-only ="true"` by DITA-OT). (GUIDES-19701)
- In the Map dashboard, selecting a different preset triggers a call to fetch peer links, resulting in additional processing. (GUIDES-53703)
- In Native PDF output, topic references marked with `toc="no"` attribute are still included in the TOC, resulting in a lengthy and cluttered table of contents. (GUIDES-20156)
- In some cases, when a full DITA map is generated and published to AEM Sites using a dynamic baseline, certain topics are published with earlier or non-approved versions instead of the current approved versions. (GUIDES-55646) 
- When processing a large number of assets, `PurgePresetExecutionDataJob` sometimes encounters an unhandled `RuntimeNodeTraversalException`, causing the job to get stuck in an infinite loop and generate excessive logs. (GUIDES-53897)
- In Native PDF output, the `outputclass` attribute set on a `topichead` or `topicgroup` element is not applied or carried forward to the resulting PDF section. (GUIDES-22950) 
- In scenarios involving a large number of review tasks, opening the Review panel or applying a project filter takes longer than expected to load the task list. (GUIDES-48893) (GUIDES-27790)

## Translation

- Applying a baseline to a map with many assets delays loading of the translation report for the selected language, sometimes leading to request timeout before the report renders. (GUIDES-45508)
- Language groups in Translation tab under Workspace Settings are not retained when the selected language folder uses a hyphenated locale code (for example, `da-DK`) instead of an underscore format (`da_dk`). (GUIDES-37843)
- Starting a translation using an XLIFF project creates an empty project that never moves to an in-progress state. (GUIDES-51759)
- The `propagateVersionLabel` setting in the global folder profile intermittently resets to `false` when the editor loads, which changes translation behavior. (GUIDES-51870) 

## Baseline

- A preset’s saved baseline selection incorrectly displays as *No Baseline* after the baseline is deleted or while a dynamic baseline is still being created. (GUIDES-52690)
- In some cases, dynamic baselines remain stuck in the processing state after a failed rebuild, causing export and output generation to use outdated topic and map versions without displaying any error. (GUIDES-56739) 

## Review

- Opening the Review panel or applying a project filter takes some time to load the task list. (GUIDES-48893)
- The content pane in the Review UI displays a horizontal scrollbar on certain screen resolutions, including the recommended 1600px resolution, causing review comments to be hidden when the content extends beyond the pane width. (GUIDES-44082)
