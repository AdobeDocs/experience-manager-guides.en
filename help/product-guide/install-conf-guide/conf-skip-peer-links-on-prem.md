---
title: Configure skipping of peer links for Baseline V1 in On-Premise
description: Learn how to Configure skipping of peer links for Baseline V1 in On-Premise
feature: Web Editor Configuration
role: Admin
level: Experienced
---
# Configure skipping of peer links for Old Baseline in On-Premise

The following steps explain how to enable skipping of peer links for Olde Baseline in your On-Premise environment.

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and select the **com.adobe.fmdita.xmleditor.config.XmlEditorConfig** bundle.

1.  Enable the setting **Skip peer links for Baseline V1**. By default this setting is diabled.

1.  Select **Save**.
