---
title: Configure valid file names for AEM Site output
description: Learn how to Configure valid file names for AEM Site output
feature: Filename Configuration
role: Admin
level: Experienced
---
# Configure valid file names for AEM Site output {#id214GK0X0KXA}

Similar to the list of valid file name characters allowed for DITA topics, you can also configure a list of valid file name characters for AEM Site output. Some of the known characters that are not allowed in a URL are: ``'<>`@$``. These characters are configured to automatically convert into an underscore "`_`" when they are found while generating AEM Site output file names.

The following tabs provide instructions based on your Experience Manager Guides setup: Cloud Service or On-Premise:

>[!BEGINTABS]

>[!TAB Cloud Service]

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to set valid characters in AEM Site output:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.common.SanitizeNodeNameImpl`|`aemsite.DisallowedFileNameChars`|Add characters that you want to replace with an underscore in the AEM Site output file names. <br> **Default value**: ``'<\>\`@$``|

>[!TAB On-Premise]

The configuration that allows you to set valid characters in AEM Site output is present in the `com.adobe.fmdita.common.SanitizeNodeNameImpl` bundle. **Set the Disallowed Character Set for Publishing to AEM Sites** setting to include characters that you want to replace with an underscore in the AEM Site output file names.

>[!ENDTABS]

**Parent topic:**[Configure filenames](conf-file-names.md)
