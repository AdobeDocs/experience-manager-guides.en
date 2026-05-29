---
title: API to track post processing for a folder or an asset
description: Learn about the API to track post processing for a folder or an asset
feature: Post-Processing Event Handler
role: Developer
level: Experienced
exl-id: f902fac1-2717-4696-a835-c4b0bb8add3d
TQID: https://experienceleague.adobe.com/Lyv-S5o-Z40bMqqIHhbxKrsmn9CCqHRnqnpiq91EjGU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
---
# API to track post processing status for a folder or an asset

>[!NOTE]
>
> For the latest REST API endpoint definitions and related details, view the Swagger documentation at `https://<aem-author-url>/libs/fmdita/clientlibs/api-docs/index.html` (replace `<aem-author-url>` with your AEM server URL). As this article is scheduled to be archived in October 2026, we recommend using the Swagger documentation going forward for the most up-to-date API information.

The following is a POST method that starts an async job to get the status of assets. 

## Find status of assets in Guides 

**Request URL**

`http://<aem-guides-server>:<port-number>bin/guides/v1/assets/status `

**Parameters**

|Name|Type|Required|Description|
|----|----|--------|-----------|
|`path`|String|Yes|Folder or asset path for which status needs to be fetched.|
|`excludedPaths`|String|No|Folder paths to exclude from the above list.|

```JSON
{ 

    "paths": [ 

        "/content/dam/status-fetch1", 

        "/content/dam/status-fetch2" 

    ], 

    "excludedPaths": [ 

        "content/dam/status-fetch1/excluded-folder" 

    ] 

} 
```

**Response values** 
jobId to poll over to get the status of async job.

```JSON
{ 

  "jobId": "akjhdfalkj1132", 

  "status": "WAITING", 

 

} 
```

## Poller API

A GET method that gets the status of async job run by above API.

**Request URL** 

`http://<aem-guides-server>:<port-number>bin/guides/v1/assets/status` 

**Parameters**

|Name|Type|Required|Description|
|----|----|--------|-----------|
|`jobId`|String|Yes|Job Id which was returned by above API .|

**Response values** 

List of assets and their status.

```JSON
{ 

  "jobId": " akjhdfalkj1132", 

  "status": "SUCCESS", 

  "assets": [ 

    { 

      "path": "/content/dam/status-fetch1/a.dita", 

      "uuid": "GUID-1293914ansd", 

      "status": "SUCCESS", 

      "exists": true 

    }, 

    { 

      "path": "/content/dam/status-fetch1/b.dita", 

      "uuid": "GUID-1883241", 

      "status": "FAILURE", 

      "exists": true 

    } 

 

  ] 

} 
```

**Status values:** SUCCESS, FAILURE, PROCESSING, PENDING
