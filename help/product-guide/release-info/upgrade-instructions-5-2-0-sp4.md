---
title: Release Notes | Upgrade instructions for Adobe Experience Manager Guides 5.2.0 Service Pack 4 release
description: Learn about the compatibility matrix and how to upgrade to the 5.2.0 Service Pack 4 release of Adobe Experience Manager Guides.
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Upgrade instructions for the 5.2.0 Service Pack 4 release

Learn how to install the AEM Guides 5.2.0 Service Pack 4 release on your AEM instance.

>[!NOTE]
>
>This is an LTS-only hotfix. The supported service pack is AEM 6.5 LTS Service Pack 2.

## Prerequisites

Before you start the Experience Manager Guides 5.2.0 Service Pack 4 upgrade process ensure that you are using version 5.2.0 Service Pack 1.

## Upgrade process for Experience Manager Guides 5.2.0 Service Pack 4

1. Download the AEM Guides package version 5.2.0 Service Pack 4.
1. Upload the package to your instance by using Package Manager (`/crx/packmgr`).
1. Install the package. Check that the state of the `fmdita` bundles returns to **Active**.
1. Clear your browser cache.
1. After all bundles are active, test the functionality.
