---
title: Configure valid file names for AEM Site output
description: Learn how to Configure valid file names for AEM Site output
feature: Filename Configuration
role: Admin
level: Experienced
exl-id: b2bc5159-2144-4683-970d-738949ac9662
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
    internal-label: Filename configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
---
# Configure valid file names for AEM Site output {#id214GK0X0KXA}

Similar to the list of valid file name characters allowed for DITA topics, you can also configure a list of valid file name characters for AEM Site output. Some of the known characters that are not allowed in a URL are: ``'<>`@$``. These characters are configured to automatically convert into an underscore "`_`" when they are found while generating AEM Site output file names.

The following tabs provide instructions to configure valid file names for AEM Site output based on your Experience Manager Guides setup: Cloud Service or On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Use the instructions given in [Configuration overrides](download-install-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to set valid characters in AEM Site output:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.common.SanitizeNodeNameImpl`|`aemsite.DisallowedFileNameChars`|Add characters that you want to replace with an underscore in the AEM Site output file names. <br> **Default value**: ``'<\>\`@$``|

>[!TAB On-Premise]

The configuration that allows you to set valid characters in AEM Site output is present in the `com.adobe.fmdita.common.SanitizeNodeNameImpl` bundle. **Set the Disallowed Character Set for Publishing to AEM Sites** setting to include characters that you want to replace with an underscore in the AEM Site output file names.

>[!ENDTABS]
