---
title: API to track post processing for a folder or an asset
description: Learn about the API to track post processing for a folder or an asset
feature: API to track post processing for a folder or an asset
role: Developer
level: Experienced
---
# API to track post processing status for a folder or an asset

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
