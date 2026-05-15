---
title: Configure Base Output Location for Publishing Output for On-Premise services
description: Configure Base Output Location for Publishing Output for On-Premise services
feature: Output Generation
role: Admin
level: Experienced
exl-id: ae1d805a-7b79-4b76-8be2-a19c5552530c
TQID: https://experienceleague.adobe.com/qf1UZh14gvlc7ZHUUBaDlHe1U3zDvzGlGjYavYKITWY
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
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
    internal-label: Native PDF publishing
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Configure Base Output Location for publishing output for On-Premise services

Perform the following steps to configure the base output location:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and select the *com.adobe.fmdita.config.ConfigManager* bundle.

1.  Update the property **Base Output Location** to specify the default path in the AEM repository where the PDF will be saved after publishing. Additionally, if an invalid path is entered, it will automatically revert to the default path: /content/dam/fmdita-outputs.

1.  Click **Save**.
