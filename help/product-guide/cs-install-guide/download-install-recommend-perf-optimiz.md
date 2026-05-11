---
title: Recommendations for performance optimization
description: Learn Recommendations for performance optimization
exl-id: 92ac1f81-2f51-44b0-82c3-56b39e8f3027
feature: Performance Optimization
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/vh0hogZNMjKrCL12WdKVuwF2qXdzy64KxIhhB-K4esA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: b1210526-416b-4ef6-bcc0-1692e99f30e9
    internal-label: Administration and security
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: baa3aa24-d162-4a57-b73a-d27341145083
    internal-label: Performance optimization
  - id: c8841798-1a28-4264-a46a-984860f8e6f6
    internal-label: User administration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
---
# Recommendations for performance optimization {#id213BD0JG0XA}

For performance optimization, consider the following points:

-   To optimize content and indexing experience, see [Optimize Content Search and Indexing](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html) in AEM documentation.

-   Patch Xerces Jar while using custom DITA-OT for publishing. This is a mandatory configuration, depending on your use case. This change is required only if you use custom DITA-OT for publishing output.

    *Required configuration*: Replace the Xerces Jar file in your custom DITA-OT package with the one shipped OOTB. The default OOTB xercesImpl-2.11.0.jar file is available within the /libs/fmdita/dita\_resources/DITA-OT.zip file. Ensure that you rename the xercesImpl-2.11.0.jar file to match the old Xerces Jar file being replaced. This can be done at run time.

    This change reduces the publishing time and memory utilization while publishing DITA maps with a large number of topics.


**Parent topic:**[Download and install](download-install.md)
