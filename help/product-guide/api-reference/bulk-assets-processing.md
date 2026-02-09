---
title: API to start bulk processing for assets
description: Learn about the API to start bulk processing for assets
feature: Post-Processing Event Handler
role: Developer
level: Experienced
exl-id: feba6d8e-c363-4360-af33-92a01dcf6672
---
# API to start bulk processing for assets

A POST method that initiates bulk asset processing for a specified path. This API supports both JCR-based and database-based asset processing. It starts an asynchronous job that processes all assets under the given path and its sub-paths. Upon initiation, the API returns a unique processingID, which can be used to track the job status.

**Request URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process`

**Request Parameters**

|Name|Type|Required|Description|
|----|----|--------|-----------|
|`path`|String|Yes|Absolute path of the folder or asset in the AEM repository to be processed.|
|`excludedPaths`|String|No|List of paths to exclude from processing|
|`type`|String|Yes|Type of processing to be performed. For example: ASSET_PROCESSING.|
|`filter`|Object|No|Filters applied to the selected assets|

**Filter object fields**

|Name|Type|Description|
|----|----|-----------|
|fileTypes|String|Asset types to process. Allowed values: DITATOPIC, DITAMAP, MARKDOWN, HTML/CSS, DITAVAL, OTHERS.|
|startTime|Integer|Lower bound for asset creation time|
|endTime|Integer|Upper bound for asset creation time|

**Request Example**

```JSON
{
  "path": "/content/dam/status-fetch1",
  "excludedPaths": [
    "content/dam/status-fetch1/excluded-folder"
  ],
  "type": "ASSET_PROCESSING",
  "filter": {
        "fileTypes": ["DITAMAP", "DITATOPIC"],
        "startTime": 1758876933000
        "endTime": 1764932039000
    }
}

```

**Response values** 

processingId to poll over to get the status of async job.

```JSON
{
  "processingId": "akjhdfalkj1132"
}

```

**Response Codes**

- 200 Success
- 400 Invalid input
- 401 Unauthorized access
- 500 internal server error

## Check job status

A GET method that retrieves the current status of a previously started asset processing job.

**Request URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/status`

**Request Parameters**

|Name|Type|Required|Description|
|----|----|--------|-----------|
|`processingId`|String|Yes|Unique ID of the job whose status is being queried.|

**Response Example**

```JSON
{
  "processingId": "string",
  "path": "string",
  "excludedPaths": ["string"],
  "status": "WAITING",
  "triggeredCount": 0,
  "startedAt": 0,
  "completedAt": 0,
  "hasLogs": true,
  "createdBy": "string",
  "type": "ASSET_PROCESSING",
  "migrationSet": {
    "totalFiles": 0,
    "calculationStatus": "WAITING"
  },
  "eta": {
    "value": 0,
    "unit": "string"
  },
  "comments": "string",
  "restartable": true,
  "resumable": true,
  "cancellable": true
}

```

**Response Codes**

- 200 Success
- 400 Invalid input
- 401 Unauthorized access
- 500 internal server error

## View job logs

A GET method that retrieves logs for a given job ID. This API fetches the logs of the asset processing job. The processingid is mandatory. The API provides offset and limit parameters, as well as a tailing strategy.

**Request URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/logs`

**Request Parameters**

|Name|Type|Required|Description|
|----|----|--------|-----------|
|`processingId`|String|Yes|Unique ID of the job whose logs are to be viewed.|
|`offset`|Integer|No|The starting point (line number) from which logs should be read. Used for pagination to skip the first N lines.|
|`limit`|Integer|No|The maximum number of log lines to fetch.|
|`tail`|Integer|No|Number of log lines to retrieve from the end.|


**Response Example**

```JSON

{
  "lines": [
    "string"
  ],
  "limit": 0,
  "offset": 0,
  "hasMore": true
}

```

**Response Codes**

- 200 Success
- 400 Invalid input
- 401 Unauthorized access
- 500 Internal server error


## Download job logs

A GET method that downloads the log file for a given job as a ZIP.

**Request URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/logs/download`

**Request Parameters**

|Name|Type|Required|Description|
|----|----|--------|-----------|
|`processingId`|String|Yes|Unique ID of the job whose log file needs to be downloaded.|


**Response Example**

```JSON

{
  "logFilePaths": [
    "string"
  ]
}
 
```

**Response Codes**

- 400 Invalid input
- 401 Unauthorized access
- 500 Internal server error

## Cancel job

A POST API that cancels an ongoing bulk asset processing request. If the job is not found, the API returns an error.

**Request URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/cancel`

**Request Parameters**

|Name|Type|Required|Description|
|----|----|--------|-----------|
|`processingId`|String|Yes|Unique ID of the job whose status is being queried.|


**Response Codes**

- 200 Success
- 400 Invalid input
- 401 Unauthorized access
- 500 Internal server error


## Resume job

A POST API that restarts a previously cancelled or failed bulk asset processing request. It resumes processing from the last checkpoint. If the job is not found or is currently running, the API returns an error.

**Request URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/resume`

**Request Parameters**

|Name|Type|Required|Description|
|----|----|--------|-----------|
|`processingId`|String|Yes|Unique ID of the job whose status is being queried.|


**Response Codes**

- 200 Success
- 400 Invalid input
- 401 Unauthorized access
- 500 Internal server error

## View job history

A GET API that returns the last 'N' executions of Asset Post-Processing.

**Request URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/history`

**Request Parameters**

None. This GET request retrieves job history without requiring input parameters.

**Response Example**

```JSON
{
  "executionHistory": [
    {
      "processingId": "165f1de6-68c4-4dcd-9223-2b7242b62306",
      "path": "/content/dam/22858",
      "status": "SUCCESS",
      "triggeredCount": 6,
      "startedAt": 1761291362776,
      "completedAt": 1761291364026,
      "hasLogs": true,
      "createdBy": "user",
      "type": "ASSET_PROCESSING",
      "migrationSet": {
        "totalFiles": 6,
        "calculationStatus": "SUCCESS"
      },
      "eta": {
        "value": 0,
        "unit": "SECONDS"
      },
      "comments": "",
      "filter": {
        "fileTypes": [],
        "filterProcessedAssets": false
      },
      "cancellable": false,
      "resumable": false,
      "restartable": true
    }
  ]
}
```
