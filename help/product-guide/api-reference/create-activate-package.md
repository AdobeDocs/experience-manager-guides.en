---
title: REST API for creating and activating packages
description: Learn about the REST API for creating and activating packages
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
feature: Rest API Packages
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/cJUVS3QdzVhnZjFF7uoHfpOSBefgm5W2jh-kWM1PvmE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
    internal-label: APIs
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
---
# REST API for creating and activating packages {#id198CF0260Y4}

The following REST API allows you to create and activate CRX packages.

## Create and activate package 

A POST method that creates and activates CRX package.

**Request URL**:
http://*<aem-guides-server\>*: *<port-number\>*/bin/fmdita/activate

**Parameters**:
The request query consists of the JSON rules string. The content type of the POST request must be set to `application/json; charset=UTF-8`.

**Example**:
The following example shows the API call using the curl command:

```XML

curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate
```


**Optional parameter**

 `activationTarget`

**Valid values**
    
`preview` or `publish` for Cloud Service and `publish` for On-premise Software

- For Cloud Service, if the parameter contains an invalid value, then the package activation fails. 

- For On-premise Software, if the parameter contains an invalid value, the error is logged, and publishing is done using the default value, `publish`. 

If you do nto define the optional parameter, `activationTarget`, it activates using the default publish agent for both Cloud Service and On-premise Software.



The following example shows the API call using the curl command with optional parameter:


```XML

curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate?activationTarget=`<validActivationTargetValue>`
```
