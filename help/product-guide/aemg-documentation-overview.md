---
title: Experience Manager Guides documentation
description: Find documentation for Adobe Experience Manager Guides. Learn about native DITA support, structured authoring, and multichannel publishing in Experience Manager.
feature: AEM Guides Tutorials
role: User
TQID: https://experienceleague.adobe.com/S4wTM-7gfU7D-JfKVbb9nK3qoQIG6PdiY7jtpsc6kDs
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
    internal-label: Reports
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
subfeature_v2:
  - id: aad65a09-20cc-4780-ad44-329d14dc8481
    internal-label: Workflows
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
    internal-label: Web Editor
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
    internal-label: Content reuse
---
# Experience Manager Guides documentation

Experience Manager Guides is an enterprise-grade CCMS with native DITA support for structured authoring, multichannel publishing, and content lifecycle management.

Select your deployment to find version-specific documentation and release notes.

>[!BEGINTABS]

>[!TAB Cloud service]

You are running Experience Manager Guides as a cloud service. Find the latest release notes, known issues, and upgrade information for the cloud deployment.

[Cloud service release notes](release-info/latest-release-info.md)

>[!TAB On-premises (4.x)]

You are running the on-premises deployment of Experience Manager Guides. Find installation requirements, configuration steps, and upgrade paths for the 4.x release line.

[On-premises installation guide](install-guide/install-configure-xml-documentation.md)

>[!TAB Managed services]

You are running Experience Manager Guides on managed services. Contact your Adobe customer success manager for deployment-specific documentation and upgrade schedules.

>[!ENDTABS]

## Start by your role

<!-- Author note: The landing-cards-container component is in beta with known display issues in preview and review environments. Verify rendering in production before publishing. Update icon paths below once confirmed against the ExL CDN icon library. Role card links point to the first topic in each role's section of the left nav — update paths to match the actual repo structure. -->

::::landing-cards-container

:::card
![Authors icon](https://cdn.experienceleague.adobe.com/icons/pencil.svg)

Authors

Create and manage DITA topics, maps, content reuse, and review workflows.

[Go to authoring guide](user-guide/authoring-content-xml-editor.md)
:::

:::card
![Administrators icon](https://cdn.experienceleague.adobe.com/icons/settings.svg)

Administrators

Configure folder profiles, permissions, workflow settings, and output templates.

[Go to administration guide](install-guide/configure-server-settings.md)
:::

:::card
![Publishers icon](https://cdn.experienceleague.adobe.com/icons/send.svg)

Publishers

Set up output presets, manage baselines, and generate output across channels.

[Go to publishing guide](user-guide/output-understanding.md)
:::

:::card
![Architects icon](https://cdn.experienceleague.adobe.com/icons/sitemap.svg)

Architects

Design DITA specializations, schemas, and content architecture for your implementation.

[Go to architecture guide](user-guide/ditaval-editor.md)
:::

::::

## Explore by feature area

<!-- Author note: Six cards will wrap to two rows of three in production. Same beta caveat as the role cards above applies here. -->

::::landing-cards-container

:::card
![Authoring icon](https://cdn.experienceleague.adobe.com/icons/edit.svg)

Authoring

Web editor, FrameMaker integration, reusable content, and review cycles.

[Explore authoring](user-guide/authoring-content-xml-editor.md)
:::

:::card
![Publishing icon](https://cdn.experienceleague.adobe.com/icons/export.svg)

Publishing

PDF, AEM Sites, HTML5, EPUB, and JSON output types.

[Explore publishing](user-guide/output-understanding.md)
:::

:::card
![Translation icon](https://cdn.experienceleague.adobe.com/icons/globe.svg)

Translation

Human and machine translation workflows for multilingual content.

[Explore translation](user-guide/translation.md)
:::

:::card
![Reports icon](https://cdn.experienceleague.adobe.com/icons/chart-bar.svg)

Reports

Content coverage, broken links, and metadata audit reports.

[Explore reports](user-guide/reports-intro.md)
:::

:::card
![Configuration icon](https://cdn.experienceleague.adobe.com/icons/gear.svg)

Configuration

Folder profiles, DITA-OT customisation, and output templates.

[Explore configuration](install-guide/configure-server-settings.md)
:::

:::card
![Migration icon](https://cdn.experienceleague.adobe.com/icons/import.svg)

Migration

FrameMaker-to-DITA conversion and legacy content import.

[Explore migration](user-guide/migrate-content.md)
:::

::::

## What's new

<!-- Author note: Badges render correctly in markdown table cells per ExL spec. <br> is supported within cells. Update release version, links, and descriptions each release cycle. The What's new table is the primary update touchpoint on this page — aim to refresh it within one week of each cloud service release. -->

| | | |
|---|---|---|
| [!BADGE 2026.06.0]{type=Informative} <br> **[AI assistant enhancements](whats-new/2026-06-0.md)** <br> Smart suggestions and context-aware authoring in the web editor. | [!BADGE Beta]{type=Caution} <br> **[Native PDF conditional output](native-pdf/components-pdf-template.md)** <br> Condition-based publishing profiles without DITA-OT overrides. | [!BADGE Video course]{type=Informative} <br> **[Getting started course](https://experienceleague.adobe.com/en/docs/experience-manager-guides-learn/videos/getting-started/overview){target="_blank"}** <br> Create, organise, author, and publish with AEM Guides. |

## Additional resources

* [Release notes](release-info/latest-release-info.md)
* [AEM Guides community](https://experienceleague.adobe.com/en/community/experience-manager){target="_blank"}
* [GitHub repository](https://github.com/AdobeDocs/experience-manager-guides.en){target="_blank"}
* [Support](https://helpx.adobe.com/support/xml-documentation-for-experience-manager.html){target="_blank"}
* [Video tutorials](https://experienceleague.adobe.com/en/docs/experience-manager-guides-learn/videos/getting-started/overview){target="_blank"}

>[!NOTE]
>
>Adobe Experience Manager Guides was formerly branded as XML Documentation for Adobe Experience Manager. References to the prior branding in the documentation are still applicable to the current offering.
