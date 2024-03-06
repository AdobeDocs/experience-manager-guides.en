---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 4.3.1.5 release
description: Learn about the bug fixes in the  4.3.1.5 release of Adobe Experience Manager Guides
role: Leader
---
# Fixed issues in the 4.3.1.5 release 


This article covers the bugs fixed in various areas of 4.3.1.5 release of Adobe Experience Manager Guides.



Learn about [upgrade instructions for the 4.3.1.5 release](../release-info/upgrade-instructions-4-3-1-5.md).


## Authoring

- Adding spaces between inline elements within `<codeblock>` causes a line break in the generated output. (15247)
- Experience issues occur while adding elements from the "Insert Element" dialog box. (15108)

## Publishing
- Error logs display incorrect information on publishing content with external scopes. (15242)
- Internal links to DITA files that start with `HTTP` are treated like external links and cause scope errors. (15155)
- AEM Site regeneration fails for DITA maps. (14369)

## Management
- **fmditaTopicrefs** property shows relative paths instead of absolute paths. (15341)

