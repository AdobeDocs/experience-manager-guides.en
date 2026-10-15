---
title: Download and install AEM Guides for the first time
description: Learn how to Download and install AEM Guides for the first time
feature: Introduction, Installation
role: Admin
level: Experienced
exl-id: 1c4a93c2-e477-4466-8390-3fda21ead9ff
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: c5fd2af0-6cbb-4746-ab0d-40ecb093af12
    internal-label: Introduction
  - id: e557051c-ff02-4ff8-9421-cf452af0edd5
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
---
# Download and install AEM Guides for the first time {#id213BCL00KEV}

Perform the following steps to download and install AEM Guides for the first time:

>[!IMPORTANT]
>
> If you want to use Livefyre along with AEM Guides, ensure that you install the Livefyre versions earlier than 3.0 before installing AEM Guides. If you are using Livefyre version 3.0 or higher, then there is no such restriction.

1.  Download AEM Guides from [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).

    >[!NOTE]
    >
    >Before installing Experience Manager Guides, ensure your system meets the [technical requirements](../install-conf-guide/aemg-technical-requirements.md).

1.  Log into your AEM instance and navigate to the CRX Package Manager. The default URL to access the package manager is:

    ```http
    http://<server name>:<port>/crx/packmgr/index.jsp
    ```

    The Package Manager manages the packages on your local AEM installation. For more information about working with the Package Manager, see [How to Work With Packages](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html) in AEM documentation.

    ![](assets/package-manager.png){width="650"}

1.  To upload the AEM Guides package, click **Upload Package**.

1.  In the Upload Package dialog, navigate to the AEM Guides file that you downloaded in Step 1 and click **OK**.

    The package is uploaded to your AEM instance.

1.  To install the package, click **Install**.

    ![](assets/install-package.png){width="650"}

1.  In the Install Package dialog, click **Install**.

1.  To get started with AEM Guides, click the Home button ![](assets/home-button.png) in the upper-left corner of the CRX Package Manager.


>[!NOTE]
>
> Perform the installation procedure on all instances of AEM servers in your setup.
