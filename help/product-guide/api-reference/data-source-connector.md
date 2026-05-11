---
title: REST API to register a data source connector
description: Learn about the REST API to register a data source connector
exl-id: e2811892-c3cf-41f5-94d8-c2b37823a53a
feature: Rest API Data Source
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/WkCyxrOF9CD7KpD9J2255WepzYLLJo8ilvB2keTxgJ0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
---
# REST API to register a data source connector {#id236LG0Y0CXA}

The following REST API allows you to register a data source connector.

## Register a data source connector 

A GET method that registers a data source connector.

**Request URL**:

`http://server:port/bin/guides/v1/konnect/config/register?path=<uploaded file path>`

**Parameters**:

|Name|Type|Required|Description|
|----|----|--------|-----------|
|`path`|String|Yes|A string which points to a path in the AEM repository. It can be a path in the `/content/dam or /var/dxml`.|

**Example**:

`http://host:4502/bin/guides/v1/konnect/config/register?path=/var/dxml/konnect/jira.json`
