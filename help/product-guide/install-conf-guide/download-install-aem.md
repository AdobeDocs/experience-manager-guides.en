---
title: Install Adobe Experience Manager
description: Learn how to Install Adobe Experience Manager
feature: Introduction, Installation
role: Admin
level: Experienced
exl-id: d72b007c-9f0a-41be-bca2-2d6b54c30de1
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: c5fd2af0-6cbb-4746-ab0d-40ecb093af12
    internal-label: Introduction
  - id: e557051c-ff02-4ff8-9421-cf452af0edd5
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
---
# Install Adobe Experience Manager {#id213BCI020E8}

AEM Guides is a plug-in that installs on top of Adobe Experience Manager. Installing AEM requires understanding of some basic AEM concepts and recommended deployment scenarios. The following link resources will help you get started with AEM installation:

- [Basic AEM Concepts](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/deploy.html#BasicConcepts)

- [Recommended AEM Deployments](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/recommended-deploys.html)

>[!IMPORTANT]
>
> If you are using Java 11 with AEM 6.5.x, you might face an issue - *JDK 11 causes `NoClassDefFoundError`*. Refer [JDK 11 causes NoClassDefFoundError \| AEM 6.5](https://helpx.adobe.com/experience-manager/kb/jdk-11-causes-noclassdeffounderror---aem-6-5.html) article to resolve this issue.

Once you have identified the deployment strategy that works best for your organization, perform the installation process as described in the *[Getting Started](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/deploy.html#GettingStarted)* section in AEM documentation.

If you plan to upgrade your AEM instance, then you must follow the given sequence:

1. Uninstall AEM Guides.
1. Upgrade your AEM instance.
1. Re-install AEM Guides.

>[!IMPORTANT]
>
> There are a number of performance optimization recommendations that you can consider to improve your system performance. See [Recommendations for performance optimization](./perf-optimization-on-prem.md) for details.
