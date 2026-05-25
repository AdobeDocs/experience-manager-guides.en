---
title: Java-based APIs for conversion workflow
description: Learn about the Java-based APIs for conversion workflow
exl-id: 807d9ffa-23e3-476c-992d-c1f495233892
feature: Java-Based API Conversion Workflow
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/gAntb7T-OGlwRNInxAsV8orxL3H9qL19Dsjwf5FZ14I
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
# Java-based APIs for conversion workflow {#id175UB30E05Z}

>[!NOTE]
>
> You can use Java-based APIs available in Experience Manager Guides to create custom plugins and extend out-of-the-box workflows. This article will be archived in November 2024.
> View [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) for the latest and detailed documentation on using the Java-based API.




The following Java-based APIs allow you to convert HTML and Word documents into DITA format. These APIs are available in the form of a bundle. You must include this bundle in your code to use these APIs.

**Bundle details**:

- Group ID: **com.adobe.fmdita**

- Artifact ID: **api**

- Version: **3.2**

- Package: **com.adobe.fmdita.api.conversion**

- Class details:

    ```JAVA
    public class ConversionUtils extends Object
    ```

    The **ConversionUtils** class contain methods for converting HTML and Word documents into DITA format.


## Convert HTML documents 

The `convertHtmlToDita` method converts HTML documents into DITA format.

**Syntax**:  

```JAVA
public static void convertHtmlToDita(Session session, 
                  String inputFile, 
                  String destPath, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parameters**:

|Name|Type|Description|
|----|----|-----------|
|`session`|javax.jcr.Session|A valid JCR session.|
|`inputFile`|String|Absolute path of the source HTML files in AEM repository.|
|`destPath`|String|Absolute path of the destination location where the converted DITA files will be saved.|
|`createRev`|Boolean|Specify whether a revision of the files is created \( `true`\) at the specified destination or not \( `false`\). This is considered only when the destination location contains an existing version of the converted files.|

**Exception**:
Throws `RepositoryException`.

## Convert Word documents 

The ``convertWordToDita`` method converts Word documents into DITA format.

**Syntax**:

```JAVA
public static void convertWordToDita(Session session, 
                  String inputFile,
                  String destPath, 
                  String style2tagMap, 
                  boolean createRev) 
                  throws RepositoryException, WorkflowException
```

**Parameters**:

|Name|Type|Description|
|----|----|-----------|
|`session`|javax.jcr.Session|A valid JCR session.|
|`inputFile`|String|Absolute path of the source Word files in AEM repository.|
|`destPath`|String|Absolute path of the destination location where the converted DITA files will be saved.|
|`style2tagMap`|String|Absolute path of the style mapping file that will be used for conversion.|
|`createRev`|Boolean|Specify whether a revision of the files is created \( `true`\) at the specified destination or not \( `false`\). This is considered only when the destination location contains an existing version of the converted files.|

**Exception**:
Throws `RepositoryException`.
