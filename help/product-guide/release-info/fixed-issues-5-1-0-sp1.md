---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 5.1.0 Service Pack 1 release
description: Learn about the bug fixes in the 5.1.0 Service Pack 1 release of Adobe Experience Manager Guides
role: Leader

---
# Fixed issues in the 5.1.0 Service Pack 1 release (October 2025)


This article covers the bugs fixed in various areas of 5.1.0 Service Pack 1 release of Adobe Experience Manager Guides.

Learn about [upgrade instructions for the 5.1.0 Service Pack 1 release](upgrade-instructions-5-0-0-sp1.md).


## Platform

- When migrating from non-UUID to UUID and upgrading to the latest version (5.0+), if you move referred images between folders and then revert the DITA files (where these images were referred) to previous versions, it results in broken image references. (GUIDES-34315)

## Publishing

- When publishing a DITA map using baseline on AEM Sites (with legacy component mapping), the map elements with the attribute `processing-role = resource-only` are also getting published. (GUIDES-34298)
