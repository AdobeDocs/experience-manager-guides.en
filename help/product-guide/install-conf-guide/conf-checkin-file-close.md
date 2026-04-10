---
title: Configure prompt to check in a file on close
description: Learn how to Configure prompt to check in a file on close
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 6b1b5894-0d55-4230-83cf-6b219e969116
---
# Configure prompt to check in a file on close {#id222HC040PE8}

When the user tries to close a file that is opened in the Web Editor using the **Close** button on the file's tab or the **Close** option in the Options menu, a dialog appears if the file has unsaved data or an unsaved version. The user is prompted to unlock the file if it is locked.

The following tabs provide instructions to configure prompt to check in a file on close option by default in the Web Editor based on your Experience Manager Guides setup: Cloud Service or On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

Use the instructions given in [Configuration overrides](download-install-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to configure a prompt to check in a file on close:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`xmleditor.checkin`|Boolean \( true/ false\).<br> **Default value**: false |

When this configuration is enabled, the **Unlock the File** checkbox is selected by default in the dialog box.

For more details, see *File close and save scenarios* section in the Using Adobe Experience Manager Guides as a Cloud Service guide.

>[!TAB On-Premise]

>[!NOTE]
>
>The **Unlock the File** checkbox is not enabled by default and you need to enable this from the configMgr. Perform the following steps to enable the option by default in the Web Editor:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundle.

1.  Select the **Ask for check-in on close** option.

1.  Click **Save**.


When this configuration is enabled, the **Unlock the File** checkbox is selected by default in the dialog box.

For more details, see *File close and save scenarios* section in the Using Adobe Experience Manager Guides as a Cloud Service guide.

>[!ENDTABS]

**Parent topic:**[Customize Web Editor](customize-overview.md)
