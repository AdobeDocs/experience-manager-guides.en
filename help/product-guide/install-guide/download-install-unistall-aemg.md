---
title: Uninstall AEM Guides
description: Learn how to Uninstall AEM Guides
exl-id: 6c6b9692-cdec-426f-bc3b-f09d0091da39
feature: Installation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/W6cpFBqAnriNXNYqP6r-GZm7tJhPWnlSI53q33iduvE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
---
# Uninstall AEM Guides {#id21BHG0C0SXA}

You can uninstall AEM Guides using the CRX Package Manager. During the uninstall, the contents of the repository are reverted to the snapshot made immediately prior to the installation of the package.

Perform the following steps to uninstall AEM Guides:

1.  Log into your AEM instance and navigate to the CRX Package Manager. The default URL to access the package manager is:

    ```http
    http://<server name>:<port>/crx/packmgr/index.jsp
    ```

1.  Search for com.adobe.fmdita package.
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

**Parent topic:**[Download and install](download-install.md)
