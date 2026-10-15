---
title: Recommendations for performance optimization for Cloud Service
description: Learn Recommendations for performance optimization
feature: Performance Optimization
role: Admin
level: Experienced
exl-id: 6c9684d4-180f-4ccb-bfd6-6c82a8a7b720
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: baa3aa24-d162-4a57-b73a-d27341145083
    internal-label: Performance optimization
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
---
# Recommendations for performance optimization for Cloud Service {#id213BD0JG0XA}

For performance optimization, consider the following points:

-   To optimize content and indexing experience, see [Optimize Content Search and Indexing](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html) in AEM documentation.

-   Patch Xerces Jar while using custom DITA-OT for publishing. This is a mandatory configuration, depending on your use case. This change is required only if you use custom DITA-OT for publishing output.

    *Required configuration*: Replace the Xerces Jar file in your custom DITA-OT package with the one shipped OOTB. The default OOTB `xercesImpl-2.11.0.jar` file is available within the `/libs/fmdita/dita\_resources/DITA-OT.zip` file. Ensure that you rename the `xercesImpl-2.11.0.jar` file to match the old Xerces Jar file being replaced. This can be done at run time.

    This change reduces the publishing time and memory utilization while publishing DITA maps with a large number of topics.
