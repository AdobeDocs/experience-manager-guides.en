---
title: Smart Tagging
description: Learn how to add smart tags in AEM Guides. Use XML Keyword Extract tool to extract relevant keywords.
feature: Metadata Management
role: User
hide: true
exl-id: dd5b2648-37e1-4737-bd9d-8618f735d11f
TQID: https://experienceleague.adobe.com/eP6k8NDSN2OAjO9JIa8qcNDDAqg2B1lpFjPzacLsG5c
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
---
# Smart Tagging {#id216KH0ID0Y8}

>[!IMPORTANT]
>
> The smart tagging feature is not available out of the box and it requires custom implementation for which you need to consult your system administrator.

AEM Guides comes with the feature to add smart tags. You can use XML Keyword Extract tool to extract smart tags. This tool uses artificial intelligence to understand the content and provide relevant keywords. You can use smart tags to improve your search engine optimization \(SEO\) and help the users to find your related content.

Perform the following steps to create smart tags:

1.  In the Assets UI, navigate to the topic for which you want to create the smart tags.
1.  Open the topic in Preview mode and select **Reprocess Assets** icon from the main toolbar.
1.  Select XML Keyword Extract to extract relevant keywords.

    ![](images/smart-tag-reprocess-asset.png){width="300"}

1.  Select the Run Post Process option. A message is displayed on the successful initiation of the tool.
1.  The tags are automatically extracted and can be seen on the Properties page of the selected topic.

    ![](images/properties-smart-tags.png){width="800"}

    >[!NOTE]
    >
    > Besides extracting the keywords through the XML Keyword Extract tool you can also add, delete, or customize the smart tags in the properties page.


*Contact your customer success team to get this feature enabled in the environment. This is not enabled as a part of the out-of-the-box support.*

**Parent topic:**[Manage metadata](manage-metadata.md)
