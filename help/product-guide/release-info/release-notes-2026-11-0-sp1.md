---
title: Release Notes | Release notes for the 2026.11.0 Service Pack 1 release | AEM Guides
description: Learn about the bug fixes, known issues, and Java SDK compatibility for the 2026.11.0 Service Pack 1 release of Adobe Experience Manager Guides as a Cloud Service.
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Release notes for the 2026.11.0 Service Pack 1 release (November 2026)

This article provides information about the fixed issues, Java SDK compatibility, and known issues in the 2026.11.0 Service Pack 1 release of Adobe Experience Manager Guides as a Cloud Service.

## Java SDK compatibility

Use the following resources when developing custom Java plugins or integrations with Experience Manager Guides. Ensure that the SDK version matches your installed Experience Manager Guides release. 

|Release|Java SDK version|Maven Central|Java API reference|
|---|---|---|----|
|2026.11.0 Service Pack 1|2026.11.0|[AEM Guides SDK API 2026.11.0](https://central.sonatype.com/artifact/com.adobe.aem/aem-dox-sdk-api/2026.11.0)|[Javadoc 2026.11.0](https://javadoc.io/doc/com.adobe.aem/aem-dox-sdk-api/latest/index.html)|

For more details, view [Configure and use the API JAR from Maven Central repository](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/api-reference/introduction).


## Fixed issues

The following issues occur when publishing to AEM Sites (with composite component mapping):

- Regenerating selected topics or a sub-map  with `microservice-based` publishing takes about as long as generating the complete map. (GUIDES-59322)
- Regenerating a sub-map that contains chunked topics  causes the TOC to display incorrect titles and links. Every chunked topic entry shows the title of the last chunked topic. (GUIDES-58650)

The following issues occur when publishing to AEM Sites using a dynamic baseline, either Baseline (legacy) or New Baseline:

- The baseline is rebuilt more than once during the same publish operation, which lengthens publishing time and, in some cases, causes the rebuild to stall. With New Baseline, incremental publish also uses a stale baseline instead of the current one, so the output may not reflect the latest content. (GUIDES-60189)
- Some performance issues are observed when using the Map dashboard. (GUIDES-60189, GUIDES-55646)

## Known issues

Adobe has identified the following known issues for the 2026.11.0 Service Pack 1 release:

- When using Experience Manager Guides as a Cloud Service 2026.11.0 or later, publishing fails with an application error if AEM restarts certain internal services during the publishing process, such as when a server instance starts. (GUIDES-60804)<br>**Workaround:** To resolve the issue, retry publishing.  
- When generating output for multiple AEM Sites (using composite component mapping) presets or Native PDF presets using same baseline via **Map collection** or API, the output generation fails with a `Rebuild the Baseline` exception. (GUIDES-60877) <br>**Workaround:** Publish the presets sequentially instead of simultaneously to avoid the issue.

