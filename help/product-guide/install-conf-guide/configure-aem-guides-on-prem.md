---
title: Configure MCP connection settings for AEM Guides On-Premise
description: Learn how to configure MCP connection settings for AEM Guides On-Premise.
meta-feature: Authoring, Publishing
meta-product: Experience Manager, Experience Manager Guides
meta-role: Admin
meta-type: Documentation
---

# Configure MCP connection settings for AEM Guides On-Premise

AI tools such as Claude, Cursor, and Codex can connect to AEM Guides On-Premise using Model Context Protocol (MCP). You can configure the connection and authentication behavior from the AEM Web Console Configuration page.

The available configurations control token handling, client registration, inactive client cleanup, temporary authentication data cleanup, and referrer validation.

## Access the configuration page

To configure the MCP connection settings:

1. Open the Adobe Experience Manager Web Console Configuration page. The default URL is:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

2. Search for the configuration name specified in the following sections and open the configuration:

  - [Configure sign-in token handling](#configure-sign-in-token-handling)
  - [Configure client registration](#configure-client-registration)
  - [Configure inactive client cleanup](#configure-inactive-client-cleanup)
  - [Configure authentication data cleanup](#configure-authentication-data-cleanup)
  - [Configure requests without referrer information](#configure-requests-without-referrer-information)

3. Update the required fields and select **Save**.

The following sections describe the available MCP configurations and their supported fields.

### Configure sign-in token handling

Configuration name: **AEM Guides OAuth PKCE Token Wrapper**

This configuration manages the token exchange during authentication and converts the authorization request from the client into an AEM access token.

| Field                | Default                 | Description                                                                                                                                                             |
| -------------------- | ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Granite Base URL     | `http://localhost:4502` | Specifies the URL that AEM uses to communicate with the author instance during authentication. Update this value if your author instance uses a different host or port. |
| Granite Timeout (ms) | `5000`                  | Specifies the maximum time, in milliseconds, to wait for the authentication request to complete.                                                                        |

### Configure client registration

Configuration name: **AEM Guides OAuth DCR Registration Gate**

This configuration controls which MCP clients can register with AEM Guides and the maximum number of registered clients.

| Field                    | Default                                      | Description                                                                                                                                                                                                                       |
| ------------------------ | -------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Allowed Redirect Schemes | `http`, `https`, `cursor`, `claude`, `codex` | Specifies the redirect URI schemes that are allowed when an MCP client registers with AEM Guides. Plain `http` is supported only when the client runs on the same machine as the server.                                          |
| Max Clients              | `1000`                                       | Specifies the maximum number of clients that can be registered at a time. When the limit is reached, new clients can't register until inactive clients are removed. Set the value to `0` to allow an unlimited number of clients. |

### Configure inactive client cleanup

Configuration name: **AEM Guides MCP Inactive Client Sweeper**

This configuration automatically removes MCP clients that haven't been active for the configured period. A client that is removed must reconnect and authenticate again.

| Field                | Default        | Description                                                                                                                                                 |
| -------------------- | -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| MCP TTL (days)       | `30`           | Specifies the number of days a client can remain inactive before it's removed. Set the value to `0` or a negative value to disable inactive client cleanup. |
| Scheduler Expression | `0 0 10 * * ?` | Specifies how often the cleanup task runs, using a cron expression. By default, the task runs once a day at 10:00 AM server time.                           |

>[!NOTE]
>
> If MCP clients in your environment are used infrequently, consider increasing the **MCP TTL (days)** value instead of disabling inactive client cleanup.

### Configure authentication data cleanup

Configuration name: **AEM Guides MCP PKCE Store Sweeper**

This configuration removes expired temporary data generated during the PKCE authentication process.

| Field                | Default       | Description                                                                                                    |
| -------------------- | ------------- | -------------------------------------------------------------------------------------------------------------- |
| Scheduler Expression | `0 0 * * * ?` | Specifies how often the cleanup task runs, using a cron expression. By default, the task runs once every hour. |

### Configure requests without referrer information

Configuration name: **Apache Sling Referrer Filter**

Some MCP clients, including Cursor, might send requests without referrer information. Configure the Apache Sling Referrer Filter to allow these requests so that the authentication process can complete successfully.

| Field       | Set to | Description                                                                                                                                                                 |
| ----------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Allow Empty | `true` | Allows requests that don't contain referrer information. Enable this option for Cursor and other MCP clients that don't provide referrer information during authentication. |
