---
title: Setting up MCP for Adobe Experience Manager Guides
description: Learn how to connect an AI assistant to the Experience Manager Guides MCP server for both Cloud Service and on-premises deployments
meta-feature: Authoring, Publishing
meta-product: Experience Manager, Experience Manager Guides
meta-role: User
meta-type: Documentation
---

# Set up the Experience Manager Guides MCP server

This article covers the environment-specific details for connecting to the Experience Manager Guides MCP server. Setup differs depending on whether your Experience Manager Guides instance runs as a Cloud Service or on-premises. Select the tab that matches your environment.

>[!BEGINTABS]

>[!TAB Cloud Service]

## MCP server endpoint

Experience Manager Guides exposes its MCP capabilities through a single HTTP endpoint.

| MCP server | Endpoint | Description |
|---|---|---|
| **Experience Manager Guides** | `https://mcp.adobeaemcloud.com/adobe/mcp/guides` | Work with topics and maps, baselines, and reports in Experience Manager Guides. |

To discover the current tool list for your environment, ask your assistant:

```
List all Experience Manager Guides tools available from the author https://author-pXXXX-eXXXX.adobeaemcloud.com and describe what they do.
```

## Request access for your organization

Access to the Experience Manager Guides MCP server is **opt-in per organization**. Before anyone in your organization can connect:

- Experience Manager Guides must be enabled on your AEM as a Cloud Service environment.
- Your organization's IMS Organization ID (Org ID) must be allow-listed by the Adobe Guides team.

To request access, contact your Adobe Customer Success team.

## Setup

You do not install anything locally. You point your client at the server URL and authenticate through the Adobe IMS sign-in flow.

### Anthropic Claude

Follow the official walkthrough: [Set up Claude for AEM MCP](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/ai-in-aem/mcp-support/chat-applications/setup-claude). When adding the custom connector, use the Experience Manager Guides endpoint:

```
https://mcp.adobeaemcloud.com/adobe/mcp/guides
```

### Cursor / Visual Studio Code

Add the server to your MCP configuration. For Cursor, add it to `.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "aem-guides": {
      "url": "https://mcp.adobeaemcloud.com/adobe/mcp/guides"
    }
  }
}
```

For clients that only support local (stdio) servers, bridge to the remote endpoint with [`mcp-remote`](https://www.npmjs.com/package/mcp-remote):

```json
{
  "mcpServers": {
    "aem-guides": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://mcp.adobeaemcloud.com/adobe/mcp/guides"]
    }
  }
}
```

>[!TAB On-premise]

You can connect supported AI clients to an Experience Manager Guides on-premises instance using the Model Context Protocol (MCP). After you establish the connection, the client can access the Experience Manager Guides operations available to your AEM user account.

All operations are performed using **your AEM identity and permissions**. The connected client can view or modify only the content and resources that your AEM account is authorized to access.

Authentication uses OAuth 2.0 Authorization Code flow with Proof Key for Code Exchange (PKCE). You authenticate with AEM when you connect a client for the first time. After successful authentication, the connection refreshes access tokens automatically.

You can connect the following clients:

| Client  | Connection method | AEM instance requirements                                                                           |
| ------------------ | ----------------------------------------- | ----------|
| **Claude Desktop** | Desktop Extension (`.mcpb`)               | Supports HTTP and HTTPS endpoints, including internal hosts accessible from your corporate network. |
| **ChatGPT (web)**  | Custom connector                          | Requires a publicly accessible HTTPS endpoint with a valid, publicly trusted TLS certificate.       |
| **Cursor**         | MCP configuration in `~/.cursor/mcp.json` | Supports HTTP and HTTPS endpoints, including internal hosts accessible from your corporate network. |

## Prerequisites

Before you connect a client, work with your AEM administrator to verify the following configuration:

1. Verify that the MCP feature is deployed and running on your Experience Manager Guides instance.
2. **Configure the Granite base URL.**: In the AEM Web Console Configuration Manager (`/system/console/configMgr`), locate the **Experience Manager Guides OAuth — PKCE Token Wrapper** configuration and verify that the Granite base URL is configured.

   If the Granite base URL isn't configured correctly, the client can't establish the connection.

3. **Configure the Day CQ Link Externalizer.**: In the AEM Web Console Configuration Manager, locate the **Day CQ Link Externalizer** configuration and verify that the external author URL points to the correct AEM author instance.

   The external author URL is used during OAuth discovery. An incorrect URL can prevent the client from completing the connection.

4. **Obtain the MCP server URL.**: The MCP server URL uses the following format:

   ```
   http(s)://<AEM-HOST>/bin/guides/v1/mcp/sse
   ```

   >[!NOTE]
   >
   > Use the complete SSE endpoint when configuring a client. Don't add a trailing slash to the URL.

   For example:

   **Internal AEM author instance:**

   ```
   http://10.42.42.20:4502/bin/guides/v1/mcp/sse
   ```

   **Public AEM author instance:**

   ```
   https://author.example.com/bin/guides/v1/mcp/sse
   
   ```

5. **Verify your AEM credentials and permissions.**: You must have a valid account for the AEM instance. Use the same credentials that you use to sign in to the AEM user interface.

   The operations available through MCP are determined by the permissions assigned to this account.

## Connect Claude Desktop

Claude Desktop supports Desktop Extensions (`.mcpb`). The Experience Manager Guides MCP extension packages the connection configuration so that you don't need to manually edit an MCP JSON configuration.

### Install and configure the extension

1. Obtain the `aem-guides-mcp.mcpb` extension file.

2. Open **Claude Desktop** and navigate to **Settings > Extensions**.

3. Install `aem-guides-mcp.mcpb` by double-clicking the file or dragging it into the Extensions window.

   The **Adobe Experience Manager Guides MCP** is displayed in the Installation dialog.

4. Select **Install**.

5. In the **Experience Manager Guides MCP Server URL** field, enter the complete SSE endpoint for your AEM instance.

   For example:

   ```
   http://<AEM-HOST>:4502/bin/guides/v1/mcp/sse
   ```

6. Select **Save** and ensure that the extension is enabled.

### Authenticate with AEM

When Claude Desktop accesses the MCP connection for the first time, your default browser opens the AEM sign-in page.

1. Sign in using your AEM credentials.
2. Approve the access request when prompted.
3. After the browser displays the successful authentication message, return to Claude Desktop.

After successful authentication, the connection refreshes authentication tokens automatically. You typically don't need to sign in again unless the session expires or access is revoked.

### Verify the connection

Start a conversation in Claude Desktop and open the tools menu.

Verify that the Experience Manager Guides tools are available, and then try a prompt such as:

```
List the available Experience Manager Guides operations.
```

You can also try a task-specific prompt:

```
Show me the broken-link report for my map.
```

### Troubleshoot the Claude Desktop connection

| Issue                                                                            | Possible cause and resolution                                                                                                    |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| The extension can't be installed or is disabled.                                 | Your version of Claude Desktop might not support the extension. Update Claude Desktop and try again.                             |
| The browser doesn't open for authentication, or the connection doesn't complete. | Verify the MCP server URL. It must end with `/bin/guides/v1/mcp/sse` and shouldn't contain a trailing slash.                     |
| Registration fails during authentication.                                        | Verify the server-side OAuth registration configuration with your AEM administrator.                                             |
| Experience Manager Guides tools aren't displayed after authentication.                          | Verify that the AEM instance is accessible from your computer and that your AEM account has the required Experience Manager Guides permissions. |
| Claude Desktop requests authentication after the connection previously worked.   | The authentication session might have expired or access might have been revoked. Authenticate with AEM again.                    |

## Connect ChatGPT

You can configure the Experience Manager Guides MCP server as a custom connector in ChatGPT.

>[!IMPORTANT]
>
> ChatGPT requires the MCP server to be available through a **publicly accessible HTTPS endpoint with a valid, publicly trusted TLS certificate**.
>
> HTTP endpoints, `localhost`, private IP addresses, and self-signed certificates aren't supported for this connection. The AEM instance must be exposed through an HTTPS host, such as a load balancer, reverse proxy, or Dispatcher configured with TLS.
>
> The external author URL configured in **Day CQ Link Externalizer** must also point to the public HTTPS address. Otherwise, the OAuth discovery metadata can advertise incorrect authentication endpoints and prevent sign-in.

### Configure the connector

1. Verify that your MCP server is available at a public HTTPS URL in the following format:

   ```
   https://<PUBLIC-AEM-HOST>/bin/guides/v1/mcp/sse
   ```

   Open the endpoint in a browser and verify that you can reach the host without a certificate warning or connection error.

2. In ChatGPT, open **Settings > Plugins**.

   >[!NOTE]
   >
   > Connector availability depends on your ChatGPT plan and workspace configuration. Your workspace Administrator might need to enable custom or developer connectors.

3. Select the option to add or create a plugin.

4. Specify the connector details:

   * **Name:** Enter `AEM Guides`, or another descriptive name.
   * **MCP Server URL:** Enter the public HTTPS SSE endpoint.
   * **Authentication:** Select **OAuth**.

   You don't need to provide an OAuth client ID or client secret. The MCP server supports automatic client registration.

5. Create the connector.

### Authenticate with AEM

After you create the connector, ChatGPT redirects you to the AEM sign-in page.

1. Sign in using your AEM credentials.
2. Approve the access request.
3. After authentication completes, return to ChatGPT.

The connector should display a connected status.

### Use Experience Manager Guides in a chat

Start a new conversation and enable the Experience Manager Guides connector from the available tools or connectors.

For example:

```
Using Experience Manager Guides, list the available operations.
```

Or:

```
Get the topic list for my map in Experience Manager Guides.
```

The operations and content available to ChatGPT are limited to the permissions of the AEM account that you used to authenticate.

### Troubleshoot the ChatGPT connection

| Issue                                                                              | Possible cause and resolution                                                                                                                             |
| ---------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ChatGPT can't reach the MCP server or doesn't allow you to add the connector.      | Verify that the endpoint is publicly accessible over HTTPS. HTTP endpoints, `localhost`, and private network endpoints aren't supported.                  |
| A certificate or security error is displayed.                                      | Verify that the server uses a valid, unexpired certificate issued by a publicly trusted certificate authority. Self-signed certificates aren't supported. |
| Registration fails during authentication.                                          | Verify the server-side OAuth registration configuration with your AEM administrator.                                                                      |
| The connector is connected, but Experience Manager Guides operations or results aren't available. | Verify that the authenticated AEM account has the required Experience Manager Guides permissions and that the requested operation is available to that account.          |
| Authentication redirects to an incorrect host or fails during discovery.           | Verify that the external author URL in **Day CQ Link Externalizer** points to the public HTTPS AEM author address.                                        |

## Connect Cursor

Configure the Experience Manager Guides MCP server in Cursor by adding the server details to the MCP configuration.

### Configure the MCP server

1. In Cursor, navigate to **Customize > MCPs > New**.

   Cursor opens the `~/.cursor/mcp.json` configuration file.

2. Add the Experience Manager Guides MCP server configuration.

   For example:

   ```json
   {
     "mcpServers": {
       "aem-guides": {
         "url": "http://10.42.34.176:4502/bin/guides/v1/mcp/sse",
         "type": "http"
       }
     }
   }
   ```

3. Replace the example URL with the MCP SSE endpoint for your AEM instance.

4. Save the configuration.

### Authenticate with AEM

1. Enable the configured MCP server in Cursor.
2. Select **Authenticate**.
3. When the AEM sign-in page opens, sign in using your AEM credentials.
4. Approve the access request.

After authentication completes, return to Cursor.

### Use Experience Manager Guides in Cursor

After the MCP server is connected, you can invoke the Experience Manager Guides operations available to your account directly from Cursor chat.

>[!ENDTABS]


