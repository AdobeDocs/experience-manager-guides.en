---
title: Java-based API to work with output generation
description: Learn about the Java-based API to work with output generation
exl-id: e19439df-39ec-47fd-9da5-24f51750a7e5
feature: Java-Based API Publishing
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/i5mTM1VtBg3QFUa-sBmF2pH8BITRn9j-efw2dr8VwCU
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
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
---
# Java-based API to work with output generation {#id175UB30E05Z}

>[!NOTE]
>
> You can use Java-based APIs available in Experience Manager Guides to create custom plugins and extend out-of-the-box workflows. This article will be archived in November 2024.
> View [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) for the latest and detailed documentation on using the Java-based API.

The following Java-based API allows you to generate output for a DITA map. This API is available in the form of a bundle. You must include this bundle in your code to use this APIs.

Bundle details:

- Group ID: **com.adobe.fmdita**

- Artifact ID: **api**

- Version: **3.4**

- Package: ****com.adobe.fmdita.api.maps****

- Class details:

  ```JAVA
  public class **PublishUtils** extends Object
  ```

  The **`PublishUtils`** class contains a method for generating output for one or more output presets.


## Generate output 

The ``generateOutput`` method generates output for a DITA map file using the specified output presets.

**Syntax**:

```JAVA
public static void generateOutput(Session session,
String sourcePath,
String outputName)
throws GuidesApiException
```

**Parameters**:

|Name|Type|Description|
|----|----|-----------|
|`session`|javax.jcr.Session|A valid JCR session.|
|``sourcePath``|String|Path \(in the AEM repository\) of the DITA map file for which the output needs to be generated.|
|``outputName``|String|Name of the output preset\(s\) to be used to generate output. Multiple output presets can be specified using a pipe \("\|"\) delimiter, for example `aemsite\|pdfoutput`.|

**Exception**:
Throws ``javax.jcr.RepositoryException``, `java.io.IOException`, and `java.lang.Exception`.
