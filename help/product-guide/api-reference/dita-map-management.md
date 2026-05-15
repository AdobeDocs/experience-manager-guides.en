---
title: REST API to work with DITA maps
description: Learn about the REST API to work with DITA maps
exl-id: 6277e52d-1b05-4dd7-8d2b-4b94f329e2d7
feature: Rest API DITA Map
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/GT4JRw1nFV7M18tJX-0t0Gx-g0I9tA8XfXLGnnhvif0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
    internal-label: APIs
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
subfeature_v2:
  - id: b7cb7f25-3b6d-4e58-beab-fe9279275fe4
    internal-label: REST API DITA Map
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
---
# REST API to work with DITA maps {#id175UB30E05Z}

The following REST API allows you to work with DITA maps in AEM Guides.

## Download DITA map with dependents 

A GET method that downloads a DITA map with all its dependents such as referenced topics, sub-maps, images, and DTDs used in the map and topics.

**Request URL**:
http://*<aem-guides-server\>*: *<port-number\>*/bin/fmdita/exportditamap

**Parameters**:

|Name|Type|Required|Description|
|----|----|--------|-----------|
|`ditamap`|String|Yes|Absolute path of the DITA map file in AEM repository.|
|`baseline`|String|No|The title of the baseline that is used to retrieve the versioned content. <br> **Note:** The value is case-sensitive. |

**Response values**:
A .zip file whose contents are written to the output stream of the response.

## Initiate export for DITA map with dependents 

A POST method that initiates an export for a DITA map with all its dependents such as referenced topics, sub-maps, images, and DTDs used in the map and topics. The status can later on be queried and the download URL can be retrieved once completed.

**Request URL**:
http:*//<aem-guides-server\>: <port-number\>/bin/dxml/async-export*

**Parameters**:

|Name|Type|Required|Description|
|----|----|--------|-----------|
|`ditamap`|String|Yes|Absolute path of the DITA map file in AEM repository.|
|`baseline`|String|No|The title of the baseline that is used to retrieve the versioned content. <br> **Note:** The value is case-sensitive.|
|`flatFS`|Boolean|No|\(Optional\) If set to true, then a flat structure of files is returned in the ZIP file. For example, if your DITA map refers to content in multiple folders, then all referenced files are pulled into a single folder. In case there are files with same name, then those files are renamed by adding a numeric suffix. All references \(in DITA map and topics\) are handled automatically, as they are updated based on the new location of files in the flat folder structure. If set to false, then the folder structure is maintained as is in the ZIP file. If the DITA map refers to files from multiple locations, then all those locations are also created in the ZIP file. When you restore the ZIP file, the exact folder structure is created at the destination location. <br> The default value for this parameter is false.|

**Response values**:

|Element|Description|
|-------|-----------|
|`status`|The return status for the operation performed. Thepossible options are: STARTED, FAILED, INPROGRESS, SUCCEED, MISSING, DELETED|
|`jobId`|The unique ID of the job. Can be used later on to query for the status.|
|errorMessage|The error message of the job in case of a failure \(if the status is FAILED, MISSING or DELETED\).|
|`filePath`|The file path of the ZIP. It is present only when the job is completed and the status is SUCCEED. This can be used to download the ZIP file.|

## Query export DITA map status 

A GET method that retrieves the status of export for a DITA map with all its dependents. It can be polled at an interval if the status is STARTED or INPROGRESS until it is finished \(successfully or with an error\).

**Request URL**:
http:*//<aem-guides-server\>: <port-number\>/bin/dxml/async-export*

**Parameters**:

|Name|Type|Required|Description|
|----|----|--------|-----------|
|`jobId`|String|Yes|The job id retrieved when the export job is initiated.|

**Response values**:

|Element|Description|
|-------|-----------|
|`status`|The status of the export job. Thepossible options are: STARTED, FAILED, INPROGRESS, SUCCEED, MISSING, DELETED|
|`jobId`|The unique ID of the job. Can be used later on to query for the status.|
|`errorMessage`|The error message of the job in case of a failure \(if the status is FAILED, MISSING or DELETED\).|
|`filePath`|The file path of the ZIP. It is present only when the job is completed and the status is SUCCEED. This can be used to download the ZIP file.|
