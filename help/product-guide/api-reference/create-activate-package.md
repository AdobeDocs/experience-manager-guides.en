---
title: REST API for creating and activating packages
description: Learn about the REST API for creating and activating packages
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
feature: Rest API Packages
role: Developer
level: Experienced
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
