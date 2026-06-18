---
title: Configure title for Cehck in and Check out icons
description: Learn how to configure the title for Check in and check out icons
exl-id: a8888a17-e819-4fa2-bb6f-cafe1002803a
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/NytwQkk18-M0MpxxBP3OWg3WFJf6Oy3N5dBaiKlc6Gg
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
# Configure the title for Check in and Check out icons

AEM Guides allows you to configure the title for Check in and Check out icons in the Editor. Perform the following steps to configure the title for Check in and Check out icons:

1.  Download the UI configuration file by logging into Adobe Experience Manager as an administrator.
1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.
1.  Select **Guides** from the list of tools and click the **Folder Profiles**.
1.  Click on the **Global Profile** tile.
1.  Select the **XML Editor Configuration** tab and click the **Edit** icon on the top.
1.  In the **XML Editor UI configuration** section, click the **Download** icon to download the `ui_config.json` file on your local system.
1.  In the `ui_config.json` file, change the title  in the "topbar" section. You can change the following values:

    ```json
    //Change title to "Check out" instead of "Lock"
            "title": "Check out"

    //Change title to "Check in" instead of "@checkOutBy
             "title": "Check in"
    ```

1. Save the file and upload it.
