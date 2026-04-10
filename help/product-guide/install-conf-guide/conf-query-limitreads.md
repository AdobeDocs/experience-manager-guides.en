---
title: Configure the number of LimitReads for a query
description: Learn how to Configure the number of LimitReads for a query
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 53748636-f3d1-4b3b-a772-2730b78741cb
---
# Configure the number of LimitReads for a query for On-Premise

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

**Parent topic:**[Customize Web Editor](customize-overview.md)
