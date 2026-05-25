---
title: REST API to work with conditional attributes
description: Learn about the REST API to work with conditional attributes
exl-id: 1f0e023a-422c-47b9-917f-b0d80090471c
feature: Rest API Conditional Attributes
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/qtmJN6jjCm3xeNYAaHTWr7G3SZFSOodcVqBOKctR3B8
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
  - id: d27d524e-c4e5-4b77-b86b-3db049db0b25
    internal-label: REST API Conditional Attributes
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
---
# REST API to work with conditional attributes {#id175UB30E05Z}

The following REST API allows you to add conditional attributes in a folder profile.

## Add conditional attribute in a folder-level profile 

A POST method that adds conditional attributes to a given folder-level profile.

**Request URL**:   
http://*<aem-guides-server\>*: *<port-number\>*/bin/fmdita/folderprofiles

**Parameters**:   

|Name|Type|Required|Description|
|----|----|--------|-----------|
|`:operation`|String|Yes|Name of the operation being called. The value of this parameter is ``ADDATTRIBUTEPROFILES``. <br> **Note:** The value is case-insensitive.|
|`profilename`|String|Yes|Display name of the folder-level profile in which the conditional attributes have to be added.|
|`conditionalprofiles`|JSON array|Yes|A JSON array consisting of the conditional attribute name and values. The following example code snippet shows the JSON array with two attributes - `platform` and `product` with multiple values assigned to them.|

```JSON
[  {    name: "platform",    
        values: [       
                {value: "win", label: "Windows"},       
                {value: "mac", label: "Mac OS"}    
                ]},
                {    
                    name: "product",    
                    values: [      
                        {value: "aem_1", label: "AEM 6.1"},     
                        {value: "aem_4,  label: "AEM 6.4"}  
                        ]  
                }]
``` 

**Response values**:   
Returns a HTTP 200 \(Successful\) response.
