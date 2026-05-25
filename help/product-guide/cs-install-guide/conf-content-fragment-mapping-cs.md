---
title: Configure the JSON-based mapping between a topic and a content fragment model.
description: Learn how to configure the JSON-based mapping between a topic and a content fragment model.
exl-id: 438e2964-b9c7-462a-a68c-8031bd97911c
feature: Output Generation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/w1XQiP79ta2-huLRGIdevylhP7VCYvmmOQVpQgI7w4w
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
    internal-label: Profiles
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
    internal-label: Native PDF publishing
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Create a mapping between a topic and a content fragment



Adobe Experience Manager Guides allows you to create a JSON-based mapping between a topic and a content fragment model. You can use JSON-based mapping to publish content present in some or all elements within a topic to a content fragment. 

>[!NOTE] 
> 
> If you are using 4.6 or later versions, you need not create this mapping, you can drag the topic elements to the fields present in the content fragment model.
> Learn more about how to [publish content fragments](../user-guide/publish-content-fragment.md). 


1. To download the *contentFragmentMapping.json*, log into Adobe Experience Manager as an administrator.
1. Select the Adobe Experience Manager link at the top and choose **Tools**.
1. Select Guides from the list of tools and select the **Folder Profiles**.
1. Select the **Global Profile** tile.
1. Select the **XML Editor Configuration** tab and select the **Edit** icon on the top.
1. Select the **Download** icon to download the *contentFragmentMapping.json*  file on your local system. You can then make changes to the file and then upload the same.

1.  You need to follow the following validations:

    1. It should be a JSON file
    2. It should contain an array containing at least one object, and every object should contain the following:


        `"name": string `

        `"mapping": array`

        Each object of mapping must contain the following:
        
       `"modelField": string`

        `"xpath": string`

        `"outputType": string`
1. Save the file and upload it.

Sample file:

```
[
  {
    "mapping": [
      {
        "modelField": "title",
        "xpath": "/topic[1]/title[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "shortdesc",
        "xpath": "/topic[1]/shortdesc[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "topicData",
        "xpath": "/topic[1]/body[1]",
        "outputType": "outerHTML"
      }
    ],
    "name": "Full Topic"
  },
  {
    "mapping": [
      {
        "modelField": "title",
        "xpath": "/topic[1]/title[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "shortdesc",
        "xpath": "/topic[1]/shortdesc[1]",
        "outputType": "textContent"
      },
      {
        "modelField": "heroImage",
        "xpath": "/topic[1]/body[1]/p[1]/image[1]",
        "outputType": "outerHTML"
      },
      {
        "modelField": "dataTable",
        "xpath": "/topic[1]/body[1]/table[1]",
        "outputType": "outerHTML"
      }
    ],
    "name": "Sample Example with XPath"
  }
]
```

 You can publish the whole topic with the default mapping. Select the `Full Topic` mapping from the dropdown **Generate Content Fragment** dialog box, and have "topicData" field in the content fragment model.
