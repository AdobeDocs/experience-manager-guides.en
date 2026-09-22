---
title: Configure MCP connection settings for AEM Guides On-Premise
description: Learn how to configure MCP connection settings for AEM Guides On-Premise.
meta-feature: Authoring
meta-product: Experience Manager, Experience Manager Guides
meta-role: Admin
meta-type: Documentation
---

# Configure MCP connection settings for Experience Manager Guides (On-Premise)

AI tools such as Claude, Cursor, and Codex can connect to Experience Manager Guides using Model Context Protocol (MCP). You can configure the MCP connection and authentication settings from the Adobe Experience Manager Web Console Configuration page.

The available configurations control token handling, requests without referrer information, and the external URL for the AEM author instance.

## Configure sign-in token handling

To configure sign-in token handling, perform the following steps:

1. Open the Adobe Experience Manager Web Console Configuration page.

   The default URL to access the configuration page is:

   ```
   http://<server name>:<port>/system/console/configMgr
   ```

2. Search for and select **AEM Guides OAuth PKCE Token Wrapper**.

3. Configure the following properties:

   | Property | Default | Description |
   |---|---|---|
   | Granite Base URL | `http://localhost:4502` | Specifies the URL that AEM uses to communicate with the author instance during authentication. Change the default port 4502 only if your author instance uses a different port.|
   | Granite Timeout (ms) | `5000` | Specifies the maximum time, in milliseconds, to wait for the authentication request to complete. |

4. Select **Save**.

## Configure requests without referrer information

>[!NOTE]
>
> This setting needs to be configured only if you are using Cursor.

Some MCP clients, including Cursor, might send requests without referrer information. To allow these requests, configure the Apache Sling Referrer Filter as follows:

1. Open the Adobe Experience Manager Web Console Configuration page.

   The default URL to access the configuration page is:

   ```
   http://<server name>:<port>/system/console/configMgr
   ```

2. Search for and select **Apache Sling Referrer Filter**.

3. In the **Allow Empty** property, set the value to `true`.

   This setting allows requests that do not contain referrer information during authentication.

4. Select **Save**.

## Configure the external URL for the author instance

The **Day CQ Link Externalizer** service allows you to centrally define the external URLs used to prefix resource paths, including the URL of the AEM author instance.

To configure the external URL, perform the following steps:

1. Open the Adobe Experience Manager Web Console Configuration page.

   The default URL to access the configuration page is:

   ```
   http://<server name>:<port>/system/console/configMgr
   ```

2. Search for and select **Day CQ Link Externalizer**.

3. Under **Domains**, add or update the `author` mapping using the following format:

   ```
   author [scheme://]server[:port][/contextpath]
   ```

   For example:

   ```
   author https://author.mycompany.com
   ```

4. Select **Save**.