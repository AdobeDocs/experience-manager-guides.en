---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2025.07.0 release
description: Learn about the bug fixes in the 2025.07.0 release of Adobe Experience Manager Guides as a Cloud Service.

---
# Fixed issues in the 2025.07.0 release 

This article covers the bugs fixed in various areas of the 2025.07.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2025.07.0 release](whats-new-2025-07-0.md).

Learn about [upgrade instructions for the 2025.07.0 release](upgrade-instructions-2025-07-0.md).

## Authoring

- When an XML comment is added within an element in the Source view, the leading and trailing spaces around the comment are lost upon switching views. (GUIDES-29781)
- Multimedia options do not work when present inside the ellipsis icon (the **More** menu) in the toolbar. (GUIDES-29583)
- When creating a new topic through the Assets UI or Editor, the topic does not automatically open in the Editor if the `xmleditor.uniquefilenames` setting is set to true in `XMLEditorConfig`. (GUIDES-28171)
- Spaces added within a MathML equation in the Source view are not retained upon switching the Editor views. (GUIDES-26111)

## Asset management

- When opening a topic in Author view after a browser refresh, previously applied tags in the File Properties panel are not retained, and adding new tags overwrites the existing ones, particularly when a large number of tags are available for selection. (GUIDES-29078)
- When generating a Metadata report for a DITA map containing a large number of assets, the **Manage** button becomes unresponsive or exhibits a delayed response. (GUIDES-28443)

## Review

- Attempts to create review tasks through the AEM workflow consistently fail because the review node is not created. (GUIDES-28214)

## Publishing

- Code quality error occurs when deploying the AEM Sites publishing components package `guides-components.all-1.3.0.zip` through Cloud Manager. (GUIDES-28873)
- Publishing a DITA map with `chunk=to-content` attribute creates duplicate JCR nodes in the new AEM Sites output, leading to redundant content structure in AEM Sites. (GUIDES-28104)
- When publishing a DITA map using the new AEM Sites output, if a topic has the `chunk =to-content` attribute and the output is set to use topic titles as page names, the generated page name incorrectly displays the word **chunk** instead of retaining the original topic name. (GUIDES-28102)
- The `cq:template` property set in the AEM Guides topic template for new AEM Sites publishing displays an incorrect value, affecting template structure and content rendering. (GUIDES-27789)


## Platform

- Performance issues like longer loading times and intermittent timeouts are observed when working with large collections. (GUIDES-29065), (GUIDES-28793)
- Vulnerabilities associated with the deprecated Guava library being used in the AEM Guides components uploaded on Experience Manager Guides.(GUIDES-27402)

