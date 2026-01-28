---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 5.0.0 Service Pack 3 release
description: Learn about the bug fixes in the 5.0.0 Service Pack 3 release of Adobe Experience Manager Guides
role: Leader

---
# Fixed issues in the 5.0.0 Service Pack 3 release (January 2026)


This article covers the bugs fixed in various areas of 5.0.0 Service Pack 3 release of Adobe Experience Manager Guides.

Learn about [upgrade instructions for the 5.0.0 Service Pack 3 release](upgrade-instructions-5-0-0-sp3.md).

## Translation

- When an image previously managed as a language‑specific asset (e.g., under /en/) is moved to a global, non‑translatable folder and baseline export is performed, it continues to reference outdated language‑specific versions of that image, leading to missing‑asset errors and incomplete or failed export packages. (GUIDES-39394)
