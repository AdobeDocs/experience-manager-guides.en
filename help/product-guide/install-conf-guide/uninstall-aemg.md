---
title: Uninstall AEM Guides
description: Learn how to Uninstall AEM Guides
feature: Installation
role: Admin
level: Experienced
exl-id: 84b248da-af7b-4811-a184-4ab17838faaa
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
