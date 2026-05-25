---
title: Install Adobe Experience Manager
description: Learn how to Install Adobe Experience Manager
exl-id: 4693b102-b75a-4904-b2d5-914e774305f3
feature: Introduction, Installation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/yoV8cMoMPIDbFi-cTm2LmmOSTpOjx8TrhengJ3WPrBs
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
---
# Install Adobe Experience Manager {#id213BCI020E8}

AEM Guides is a plug-in that installs on top of Adobe Experience Manager. Installing AEM requires understanding of some basic AEM concepts and recommended deployment scenarios. The following links will help you get started with AEM installation:

-   [Basic AEM Concepts](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/deploy.html#BasicConcepts)

-   [Recommended AEM Deployments](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/recommended-deploys.html)


>[!IMPORTANT]
>
> If you are using Java 11 with AEM 6.5.x, you might face an issue - *JDK 11 causes `NoClassDefFoundError`*. Refer [JDK 11 causes NoClassDefFoundError \| AEM 6.5](https://helpx.adobe.com/experience-manager/kb/jdk-11-causes-noclassdeffounderror---aem-6-5.html) article to resolve this issue.

Once you have identified the deployment strategy that works best for your organization, perform the installation process as described in the *[Getting Started](https://helpx.adobe.com/experience-manager/6-5/sites/deploying/using/deploy.html#GettingStarted)* section in AEM documentation.

If you plan to upgrade your AEM instance, then you must follow the given sequence:

1.  Uninstall AEM Guides.
1.  Upgrade your AEM instance.
1.  Install AEM Guides.

>[!IMPORTANT]
>
> There are a number of performance optimization recommendations that you can consider to improve your system performance. See [Recommendations for performance optimization](download-install-recommend-perf-optimiz.md#) for details.

**Parent topic:**[Download and install](download-install.md)
