---
title: Conversion process event handler
description: Learn about the Conversion process event handler
exl-id: 8033935d-2113-4e39-ab74-b7431b89f948
feature: Conversion Process Event Handler
role: Developer
level: Experienced
TQID: 'https://experienceleague.adobe.com/VhlUaVSMTZpfyh5MiJI0WHFpc46s41xjLbuLMUnKH58'
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
    internal-label: APIs
subfeature_v2:
  - id: bb416568-e09c-46e3-b3e9-fa7154401215
    internal-label: Conversion process event handler
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
---
# Conversion process event handler {#id175UB30E05Z}

AEM Guides exposes com/adobe/fmdita/conversion/complete event that is used to perform any post-processing operations after completion of a document conversion process. This event is triggered whenever an non-DITA document is migrated into DITA file format. For example, if you run a Word to DITA conversion or InDesign to DITA conversion process, this event is called after the conversion process ends.

You need to create an AEM event handler to read the properties available in this event and do further processing.

Event details are explained below:

**Event name**:

```HTTP
com/adobe/fmdita/conversion/complete 
```

**Parameters**:

|Name|Type|Description|
|----|----|-----------|
|`status`|String|The return status for the operation performed. The possible options are: -   SUCCESS: The conversion process completed successfully. <br> -   COMPLETED WITH ERRORS: The conversion process completed, but with some errors. <br>-   FAILED: The conversion process failed due to some fatal error.|
|`filePath`|String|Absolute path of the source file \(to be converted\) in AEM repository.|
|`outputPath`|String|Absolute path of the destination location where the converted DITA files will be saved.|
|`logPath`|String|Absolute path of the node where the conversion log will be saved.|
