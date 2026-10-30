---
title: Uninstall AEM Guides
description: Learn how to Uninstall AEM Guides
feature: Installation
role: Admin
level: Experienced
exl-id: 84b248da-af7b-4811-a184-4ab17838faaa
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: e557051c-ff02-4ff8-9421-cf452af0edd5
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
---
# Uninstall AEM Guides for On-Premise{#id21BHG0C0SXA}

You can uninstall AEM Guides for On-Premise using the CRX Package Manager. During the uninstall, the contents of the repository are reverted to the snapshot made immediately prior to the installation of the package.

Perform the following steps to uninstall AEM Guides for On-Premise:

1.  Log into your AEM instance and navigate to the CRX Package Manager. The default URL to access the package manager is:

    ```http
    http://<server name>:<port>/crx/packmgr/index.jsp
    ```

1.  Search for `com.adobe.fmdita` package.
1.  Click the package to expand it.
1.  Click **More** to open the dropdown.
1.  Click **Uninstall** and wait for the uninstall to complete.
1.  If you no longer need this package, click **Delete** after uninstalling the package.

## After Uninstall 

To clean up the residual files after the uninstall, perform the following steps:

1.  Clean the script cache using:

    ```http
    http://<host>:<port>/system/console/scriptcache
    ```

1.  You can invalidate cache using:

    ```http
    http://<host>:<port>/libs/granite/ui/content/dumplibs.rebuild.html?back=true
    ```

1.  Click **Invalidate Cache**.
1.  Clean the browser's cache.
