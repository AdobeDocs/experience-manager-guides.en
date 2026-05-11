---
title: Configure the number of LimitReads for a query
description: Learn how to Configure the number of LimitReads for a query
exl-id: f6010cc3-5fec-4ec7-adf7-5ad3c9bd8879
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/BwhrVPLcY4zw-pzB2wYGXnzBQHV2eFruoQnHWOE4F88
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
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Configure the number of LimitReads for a query {#id231RC0HL0ID}

To increase the number of nodes that a query may read at a time, perform the following steps:

1.  Open the Adobe Experience Manager Web Console JMX page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/jmx
    ```

1.  Search for and click on **QueryEngineSettings**.

1.  Change attribute value for the **LimitReads** attribute.

1.  Click **Save**.


When you increase this attribute value, it helps you generate the report for larger DITA maps.

**Parent topic:**[Customize Web Editor](conf-web-editor.md)
