---
title: Release Notes | What's New in Adobe Experience Manager Guides 5.2.0 Service Pack 1 release
description: Learn about the new and enhanced features in the 5.2.0 Service Pack 1 release of Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/dXXQ1YvVduT11vvF5qyXHLqnuo1xMKkAb5I-EoD2JAA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
---
# What's new in the 5.2.0 Service Pack 1 release (September 2026)

This article covers the new and enhanced features introduced with version 5.2.0 Service Pack 1 of Adobe Experience Manager Guides.

For the list of issues that have been fixed in this release, view  [Fixed issues in the 5.2.0 Service Pack 1 release](fixed-issues-5-2-0-sp1.md).

Learn about [upgrade instructions for the 5.2.0 Service Pack 1 release](../release-info/upgrade-instructions-5-2-0-sp1.md).


## Experience Manager Guides adds MCP support

Experience Manager Guides now supports Model Context Protocol (MCP). You can connect your AI tools like Claude, Cursor, etc. to Guides without requiring any custom work. Through a single MCP endpoint, in this version, authenticated users can use Guides as a headless system and manage topics and maps, create and export baselines, and generate reports, all while operating under their existing AEM permissions. This empowers documentation teams to work more efficiently using AI applications and agents. 

For more details, view [Using Adobe Experience Manager Guides MCP Server](../install-conf-guide/conf-aem-guides-mcp.md).


## Support for external data sources and citations now available in the New Editor

The New Editor now supports two existing Experience Manager Guides capabilities: Ability to connect with external data sources and use citations in the documents.

Authors can continue using configured external data sources while creating or updating content in the New Editor. Citations are also supported, so authors can add and manage references in their content without switching editors. 

## Support for AMA citation style

Experience Manager Guides now supports the American Medical Association (AMA) citation style, extending the existing citation framework to meet the documentation standards required by customers in healthcare, regulatory, and life sciences sectors.

When AMA is selected as the citation style in **Workspace settings**, citations are automatically formatted according to AMA guidelines, including numeric superscript rendering, sequential numbering, and accurate reference list ordering. The **Parse citation** option in the Editor is available exclusively when AMA is selected, allowing authors to add and parse citations without switching contexts.

AMA citation style is supported across the Native PDF and AEM Sites output formats. To configure the citation style, go to **Workspace settings** and select AMA from the citation style options. For details, view [Work with citations](../user-guide/web-editor-apply-citations.md).


