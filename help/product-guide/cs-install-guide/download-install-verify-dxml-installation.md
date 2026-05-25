---
title: Verify AEM Guides installation
description: Learn how to Verify AEM Guides installation
exl-id: 4e566c57-a522-4605-bc70-47155f20b429
feature: Installation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/WDiYcOCdCuaJCrGYCupOS0TEk5TV-1q6Zi5z-S7KWLA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Verify AEM Guides installation {#id213BD030FBE}

Once you have installed AEM Guides, you need to verify whether the installation was successful or not. Perform the following steps to verify the installation:

1.  Access the Developer Console of your Cloud Service.

    For details of accessing Developer Console, see [Developer Console access](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html) in AEM documentation.

1.  Access the list of OSGi Bundles in AEM.

    For details of accessing Bundles, see [Bundles](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/debugging/debugging-aem-as-a-cloud-service/developer-console.html?lang=en#bundles) in AEM documentation.

1.  Search for fmdita in the list of bundles and check its status.

    The status should show *Active* for successfully deployed bundles. If any of the bundle does not have an Active status, then check the AEM logs to troubleshoot the installation issue.


**Parent topic:**[Download and install](download-install.md)
