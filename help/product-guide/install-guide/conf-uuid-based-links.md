---
title: Configure display of UUID-based links
description: Learn how to Configure display of UUID-based links
exl-id: ab1b0ecf-cb50-4fcd-b36e-d16a8c396054
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/QlYbIRVwAM10wfcu-Fz3CzOkCCUDZHbVzZo3xCxT3wI
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Configure display of UUID-based links {#id2035G20M0QN}

By default, when you create a link using the Insert Reference or Insert Reuse Content option in the Web Editor, the link is created using the UUID of the referenced content. The **Link** property \(in Properties panel\) of the referenced content can be configured to show the relative file path of the referenced content or the UUID. This display is controlled by the **Enable UUIDs** option in the configMgr. By default, it is turned ON, which implies that the UUID of the referenced content is shown in the Properties panel.

Perform the following steps to show the relative path or the UUID of the referenced content in the Web Editor:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundle.

1.  In the *XmlEditorConfig* settings, the **Enable UUIDs** option is enabled by default. This implies that UUID of the referenced content is shown in the **Link** property in the Properties panel.

    If you want to show the relative path of the linked content, then deselect the **Enable UUIDs** option.

1.  Click **Save**.


**Parent topic:**[Customize Web Editor](conf-web-editor.md)
