---
title: Configure valid file names for AEM Site output
description: Learn how to Configure valid file names for AEM Site output
exl-id: 1e69d6f8-7baf-4189-bbbd-34cd0fec6634
feature: Filename Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/vGe4--XJ9VL5q74J7hVFCmD0vrBRnUkBAdZDCFcUxeU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
    internal-label: Filename configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Configure valid file names for AEM Site output {#id214GK0X0KXA}

Similar to the list of valid file name characters allowed for DITA topics, you can also configure a list of valid file name characters for AEM Site output. Some of the known characters that are not allowed in a URL are: ```'<>`@$```. These characters are configured to automatically convert into an underscore "_" when they are found while generating AEM Site output file names. The configuration that allows you to set valid characters in AEM Site output is present in the `com.adobe.fmdita.common.SanitizeNodeNameImpl` bundle. **Set the Disallowed Character Set for Publishing to AEM Sites** setting to include characters that you want to replace with an underscore in the AEM Site output file names.

**Parent topic:**[Configure filenames](conf-file-names.md)
