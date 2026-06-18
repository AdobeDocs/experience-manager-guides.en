---
title: Configure auto-filenames based on UUID
description: Learn how to Configure auto-filenames based on UUID
exl-id: 2a599228-6d46-494f-a57a-96c3f30e073a
feature: Filename Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/2oXpOlXt4gZ3GELX7SmwPJoWJYM71f0cZFy2--M6AYM
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: ccd46b93-df7f-4458-ba4c-90a3562d9ab0
    internal-label: Filename configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Configure auto-filenames based on UUID {#id205QG070D5Z}

By default, when a topic or map file is created, authors are given an option to specify the file name as well. Authors are free to assign the file names as per their requirements. However, this can bring in inconsistency and a wide range of files name can be seen in a large documentation system. As an administrator, you can restrict your authors from assigning file names for the files they create in your system. For every new topic or map file, you can choose to assign UUID-based file names automatically.

Perform the following steps to automatically assign the UUID-based file name for all new files created in the system:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the *com.adobe.fmdita.xmleditor.config.XmlEditorConfig* bundle.

1.  Select the **Use UUID Based System Filenames** option.

1.  Click **Save**.


>[!NOTE]
>
> By default, this option is turned OFF. When this option is turned on, authors will not see the option to specify the file name while creating a new topic or map file. A new topic or map file can be created from the Assets UI and the Editor.

**Parent topic:**[Configure filenames](conf-file-names.md)
