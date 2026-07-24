---
title: Using MCP with Adobe Experience Manager Guides
description: Learn how to use the Model Context Protocol (MCP) with AEM Guides to work with topics, maps, baselines, and reports through an AI assistant
feature: Authoring, Publishing
role: User
---

# Using Adobe Experience Manager Guides MCP Server

The Model Context Protocol (MCP) is a standard way for AI assistants to connect to external tools and data, instead of you switching context to operate those tools yourself.

The Adobe Experience Manager Guides MCP server brings this to Experience Manager Guides. It allows an MCP-enabled AI assistant, such as Anthropic Claude, to connect to your Experience Manager Guides environment and act on your behalf, under your own AEM permissions. Once connected, you can work with your maps, topics, baselines, and reports on Experience Manager Guides as a Cloud Service using plain natural language.

This article explains why MCP is useful for Experience Manager Guides, what the MCP server covers, which applications it works with, how to set it up, and how to use it.

## Why MCP for Experience Manager Guides is useful

Documentation teams often spend significant time on repetitive, navigation-heavy tasks such as finding topics in a large map, checking document states, tracking down broken links, creating baselines for a release, or exporting reports. With the Experience Manager Guides MCP server, you can ask an AI assistant to handle these directly, without switching into the Experience Manager Guides UI.

For example:

- Instead of opening a map and checking each topic's state one by one, ask the assistant to list the topics and their states.
- Instead of manually starting a broken-links report and waiting on the Experience Manager Guides UI, ask the assistant to run the report and tell you when it is done.
- Instead of navigating to the baseline screen, ask the assistant to create a baseline for a specific map.

## MCP server provided by Experience Manager Guides

Experience Manager Guides exposes its MCP capabilities through a single HTTP endpoint.

| MCP server | Endpoint | Description |
| --- | --- | --- |
| **Experience Manager Guides** | `https://mcp.adobeaemcloud.com/adobe/mcp/guides` | Work with topics and maps, baselines, and reports in Experience Manager Guides. |

This one endpoint covers four areas:

- **Topics and maps** - Create, read, update, delete, version, and lock topics and maps.
- **Baselines** - Create, list, export, duplicate, rebuild, and label baselines.
- **Reports** - Topic lists, metadata, broken links, and multimedia usage.
- **System** - Package version, bundle health, and environment diagnostics.

The exact tools available may change over time. Instead of relying on a fixed list, ask your assistant to show you what is available:

```
List all Experience Manager Guides tools available from the author https://author-pXXXX-eXXXX.adobeaemcloud.com and describe what they do.
```

## Request access for your organization

Access to the Experience Manager Guides MCP server is **opt-in per organization**. Before anyone in your organization can connect:

- Experience Manager Guides must be enabled on your AEM as a Cloud Service environment.
- Your organization's IMS Organization ID (Org ID) must be allow-listed by the Adobe Guides team.

To request access, contact your Adobe Customer Success team.

## Supported applications

The Experience Manager Guides MCP server is a **remote** server. It works with any MCP client that supports remote servers, including:

### Chat applications

- Anthropic Claude (web and desktop)

### Developer tools

- Cursor
- Visual Studio Code
- Other MCP-capable IDEs

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

## Authentication

The Experience Manager Guides MCP server uses **Adobe IMS** for authentication.

- On first connection, your client opens a browser sign-in window. Sign in with your Adobe ID to complete the connection.
- After you sign in, every action runs under your existing AEM permissions. If you do not have permission for an action in AEM, the same action fails through MCP.

## Using the Experience Manager Guides MCP Server

Once connected, describe what you want in plain language. The assistant selects the appropriate tool and fills in its parameters, such as the map path or baseline name.

>[!IMPORTANT]
>
>Requests that involve several steps or take time to finish, such as exports, baseline builds, and bulk updates, work best with a thinking model. These run in the background: the assistant starts the job, then checks its status until the result, or a download link, is ready.

### Example prompts

The following prompts illustrate typical requests, each triggering a different tool:

1. **Check topic states in a map**

   > List all topics in the map at `/content/dam/docs/user-guide.ditamap`, and show their titles and document states.

1. **Create a baseline**

   > Create a static baseline of `/content/dam/docs/user-guide.ditamap` titled "Release 3.2".

1. **Run a report**

   > Run the broken-links report for the user guide, and give me the download link when it is ready.

## Expectation management

- **Validate the result** - The assistant can make mistakes, such as picking the wrong map or topic. Review a report or a new baseline before you use it.
- **It improves over time** - As the assistant gets better, tasks that take a few prompts today may take one prompt later.
- **You still make the call** - The assistant can tell you a topic's state or list broken links, but deciding whether content is ready to publish is still up to the Reviewer or Publisher.
- **Be careful with auto-approval** - Some MCP clients, including Claude, let you auto-approve actions instead of confirming each one. This is acceptable for read-only actions, such as running a report. For actions that create, change, or lock content, confirm each one so that you can review it before it takes effect.

For questions about Experience Manager Guides MCP, contact your Adobe Customer Success team.


