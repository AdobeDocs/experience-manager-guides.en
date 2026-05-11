---
title: REST APIs for conversion workflow
description: Learn about the REST APIs for conversion workflow
exl-id: f091782e-ab54-4db4-9018-9bcbff9da7b2
feature: Rest API Conversion Workflow
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/EG-ugDPVpviaEI1SXHOaFLPfChkzqQ8tSkPV-LZ-X3o
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
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
---
# REST APIs for conversion workflow {#id175UB30E05Z}

The following REST APIs allows you to convert Word, HTML, and InDesign documents into DITA format.

## Convert Word documents 

A GET method that converts Word documents into DITA format.

**Request URL**:
http://*<aem-guides-server\>*: *<port-number\>*/bin/fmdita/conversion

|Name|Type|Required|Description|
|----|----|--------|-----------|
|``operation``|String|Yes|Name of the operation being called. The value of this parameter is ``word2dita``. <br> **Note:** The value is case-insensitive. |
|`inputFile`|String|Yes|Absolute path of the source Word files in AEM repository.|
|`destPath`|String|Yes|Absolute path of the destination location where the converted DITA files will be saved.|
|`createRev`|Boolean|Yes|Specify whether a revision of the files is created \( `true`\) at the specified destination or not \( `false`\). This is considered only when the destination location contains an existing version of the converted files.|
|`style2tagMap`|String|Yes|Absolute path of the style mapping file that will be used for conversion.|

**Response values**:
Returns a HTTP 200 \(Successful\) response.

## Convert HTML documents 

A GET method that converts HTML documents into DITA format.

**Request URL**:

http://*<aem-guides-server\>*: *<port-number\>*/bin/fmdita/conversion

**Parameters**:

|Name|Type|Required|Description|
|----|----|--------|-----------|
|`operation`|String|Yes|Name of the operation being called. The value of this parameter is ``html2dita``. <br> **Note:** The value is case-insensitive.|
|`inputFile`|String|Yes|Absolute path of the source HTML files in AEM repository.|
|`destPath`|String|Yes|Absolute path of the destination location where the converted DITA files will be saved.|
|`createRev`|Boolean|Yes|Specify whether a revision of the files is created \( `true`\) at the specified destination or not \( `false`\). This is considered only when the destination location contains an existing version of the converted files.|

**Response values**:

Returns a HTTP 200 \(Successful\) response.

## Convert InDesign documents 

A GET method that converts InDesign documents into DITA format.

**Request URL**:
http://*<aem-guides-server\>*: *<port-number\>*/bin/fmdita/conversion

**Parameters**:

|Name|Type|Required|Description|
|----|----|--------|-----------|
|``operation``|String|Yes|Name of the operation being called. The value of this parameter is ``idml2dita``. <br> **Note:** The value is case-insensitive.|
|`inputFile`|String|Yes|Absolute path of the source InDesign files in AEM repository.|
|`destPath`|String|Yes|Absolute path of the destination location where the converted DITA files will be saved.|
|`createRev`|Boolean|Yes|Specify whether a revision of the files is created \( `true`\) at the specified destination or not \( `false`\). This is considered only when the destination location contains an existing version of the converted files.|

**Response values**:
Returns a HTTP 200 \(Successful\) response.
