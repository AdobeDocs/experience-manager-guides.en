---
title: API to start bulk processing for assets
description: Learn about the API to start bulk processing for assets
feature: Post-Processing Event Handler
role: Developer
level: Experienced
---
# API to start bulk processing for assets

A POST method that starts bulk asset processing for the specified path. This API can be used for both JCR-based and database-based asset processing. It initiates an asynchronous job that processes all assets under the given path and its sub-paths. The API returns a unique processingID that can later be used to check the status of the job.

**Request URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process`

**Request Parameters**

|Name|Type|Required|Description|
|----|----|--------|-----------|
|`path`|String|Yes|Absolute path of the folder or asset in the AEM repository to be processed.|
|`excludedPaths`|String|No|List of paths to exclude from processing|
|`type`|String|Yes|Type of processing to be performed. For example: ASSET_PROCESSING.|

**Request Example**

```JSON
{ 

    "path": 

        "/content/dam/status-fetch1",         

    "excludedPaths": 
    
    [ 

        "content/dam/status-fetch1/excluded-folder" 

    ],

    "type": "ASSET_PROCESSING"

    
} 
```

**Response values** 
processingId to poll over to get the status of async job.

```JSON
{ 

  "processingId": "akjhdfalkj1132", 

 
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
|`processingId`|String|Yes|Unique job ID to query.|

**Request Example**

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

  "migrationSet": { "totalFiles": 0, "calculationStatus":   
  "WAITING" },

  "eta": { "value": 0, "unit": "string" },

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

A GET method that retrieves logs for a given job ID. This API fetches the logs of the asset processing job. The processingid is mandatory. This API provides the offset/limit as well as tail strategy. 

**Request URL**

`http://<aem-guides-server>:<port-number>/bin/guides/v1/assets/process/logs`

**Request Parameters**

|Name|Type|Required|Description|
|----|----|--------|-----------|
|`processingId`|String|Yes|Unique ID of the job whose logs are to be viewed.|
|`offset`|Integer|No|The starting point (line number) from which logs should be read. Used for pagination - skip the first N lines.|
|`limit`|String|No|The maximum number of log lines to fetch.|
|`tail`|String|Yes|The number of log lines from the end.|


**Request Example**

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


**Request Example**

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

A POST API that cancels an already running bulk asset processing request. In case job is not found, it will return an error.

**Request Parameters**

|Name|Type|Required|Description|
|----|----|--------|-----------|
|`processingId`|String|Yes|Unique ID of the job whose log file needs to be downloaded.|


**Response Codes**

- 200 Success
- 400 Invalid input
- 401 Unauthorized access
- 500 Internal server error


## Resume job

A POST API restarts a previously cancelled or failed bulk asset processing request. It resumes the processing from the last checkpoint. In case job is not found or is in running state, it will return an error.

**Request Parameters**

|Name|Type|Required|Description|
|----|----|--------|-----------|
|`processingId`|String|Yes|Unique ID of the job whose log file needs to be downloaded.|


**Response Codes**

- 200 Success
- 400 Invalid input
- 401 Unauthorized access
- 500 Internal server error

## View job history

A GET API that returns the last 'N' executions of Asset Post-Processing.

**Request Example**

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



