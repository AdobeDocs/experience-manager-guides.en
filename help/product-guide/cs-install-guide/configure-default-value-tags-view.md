---
title: Configure default value for the Tags View
description: Learn how to Configure default value for the Tags View
exl-id: 3ab75101-4c23-4e45-bfcf-76c1f5b92c96
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/e-BZ7-itZXflsqHW9-5Vo6ktr9RS73xdIWMZh4BU2MU
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
# Configure default value for the Tags View {#id223GN0M0NDC}

AEM Guides allows you to configure the default state for the Tags View in the Web Editor, which helps you to keep the Tags View on or off by default for a new user's session.Perform the following steps to configure the default value for Tags View:

1.  Download the UI configuration file by logging into Adobe Experience Manager as an administrator.
1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.
1.  Select **Guides** from the list of tools and click the **Folder Profiles**.
1.  Click on the **Global Profile** tile.
1.  Select the **XML Editor Configuration** tab and click the **Edit** icon on the top.
1.  In the **XML Editor UI configuration** section, click the **Download** icon to download the `ui_config.json` file on your local system.
1.  In the `ui_config.json` file, change the default tags view state by changing the defaultValues section as shown below:

```
"defaultValues":
                {
                "tagsView": true
                }
```

1.) Save the file and upload it.

>[!NOTE]
>
> The user's preference in the Web Editor to enable/disable the Tags View has precedence over this default value. So, if a user enables the Tags View from the Web Editor, it remains enabled even across the sessions.

**Parent topic:**[Customize Web Editor](conf-web-editor.md)
