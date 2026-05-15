---
title: Configure Translation feature in the Web Editor
description: Learn how to Configure Translation feature in the Web Editor
exl-id: e25473c3-9a84-4658-87c9-6fd72bcaa2b6
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/7-SFQ0FXQ6bGo3pjAOK-18sEsU4-zriruioG2nMx2o0
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
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
    internal-label: Profiles
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Configure Translation feature in the Web Editor {#id21BONI0J0YR}

The Web editor provides a powerful translation feature to translate your content into multiple languages.

You can use the **Manage** tab in the Web Editor to translate your content. This tab is available by default.

To hide the **Manage** tab in the Web Editor, perform the following steps:

1.  Log into **Adobe Experience Manager** as an administrator.
1.  Click on the **Adobe Experience Manager** link at the top and choose **Tools**.
1.  Select **Guides** from the list of tools and click the **Folder Profiles**.
1.  Click on the **Global Profile** tile.
1.  Click on **XML Editor Configuration**.
1.  Click on **Edit** icon on the top.
1.  Download the `ui\_config.json` file.Remove the following code snippet from the downloaded file:

    ```json
    {
        "component":"tab",
        "id":"workflow",
        "title":"Manage",
        "on-click":"APP_MODE_CHANGE",
        "items":
        [
            {
                "component":"label",
                "label":"Manage"
            }
        ]
    },
    ```

1.  Upload the updated ui\_config.json file.

Note that the **Manage** filter is no longer available.

**Parent topic:**[Customize Web Editor](conf-web-editor.md)
