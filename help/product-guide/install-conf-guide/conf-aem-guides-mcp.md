---
title: Using MCP with Adobe Experience Manager Guides
description: Learn how to use the Model Context Protocol (MCP) with AEM Guides to work with topics, maps, baselines, and reports through an AI assistant
feature: Authoring, Publishing
role: User
---

# Using Adobe Experience Manager Guides MCP Server

The Model Context Protocol (MCP) is a standard way for AI assistants to connect to external tools and data, instead of you switching context to operate those tools yourself.

The Adobe Experience Manager Guides MCP server brings this to Experience Manager Guides. It allows an MCP-enabled AI assistant, such as Anthropic Claude, to connect to your Experience Manager Guides environment and act on your behalf, under your own AEM permissions. Once connected, you can work with your maps, topics, baselines, and reports on Experience Manager Guides as a Cloud Service using plain natural language.

This article explains why MCP is useful for Experience Manager Guides, what the MCP server covers, which applications it works with, and how to use it.

## Why MCP for Experience Manager Guides is useful

Documentation teams often spend significant time on repetitive, navigation-heavy tasks such as finding topics in a large map, checking document states, tracking down broken links, creating baselines for a release, or exporting reports. With the Experience Manager Guides MCP server, you can ask an AI assistant to handle these directly, without switching into the Experience Manager Guides UI.

For example:

- Instead of opening a map and checking each topic's state one by one, ask the assistant to list the topics and their states.
- Instead of manually starting a broken-links report and waiting on the Experience Manager Guides UI, ask the assistant to run the report and tell you when it is done.
- Instead of navigating to the baseline screen, ask the assistant to create a baseline for a specific map.

## MCP server provided by Experience Manager Guides

Experience Manager Guides exposes MCP capabilities for working with Experience Manager Guides content and related workflows. Depending on your AEM permissions, the MCP server provides access to the following capabilities:

* **Topics and maps**: Work with topics and maps throughout the content lifecycle, from creating and viewing content to updating, versioning, locking, and deleting it.
* **Baselines**: Work with baselines by creating, listing, exporting, duplicating, rebuilding, and labeling them.
  >[!NOTE]
  >
  > For both Cloud Service and on-premises environments, baseline capabilities are available only when [new baseline](../user-guide/web-editor-baseline-v2.md) is enabled.
* **Reports**: Gain insights into your content by accessing topic lists and metadata, identifying broken links, and reviewing multimedia usage.
* **System**: Understand the state of your system by checking package versions, bundle health, and environment diagnostics.

If you don't have permission to perform an action in AEM, you can't perform the same action through MCP.

The exact tools available may change over time. Instead of relying on a fixed list, ask your assistant to show you what is available:

`List all Experience Manager Guides tools available and describe what they do.`


## Supported applications

The Experience Manager Guides MCP server is a **remote** server. It works with any MCP client that supports remote servers, including:

- **Chat applications**: Anthropic Claude (web and desktop)

- **Developer tools**: Cursor, Visual Studio Code, and other MCP-capable IDEs

Based on your environment, connect your MCP client and authenticate to the Experience Manager Guides MCP server. For details, view [Set up the Experience Manager Guides MCP server](./configure-aem-guides-mcp.md).

## Using the Experience Manager Guides MCP Server

Once connected, describe what you want in plain language. The assistant selects the appropriate tool and fills in its parameters, such as the map path or baseline name.

>[!IMPORTANT]
>
> Requests that involve several steps or take time to finish, such as exports, baseline builds, and bulk updates, work best with a thinking model. These run in the background: the assistant starts the job, then checks its status until the result, or a download link, is ready.

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


