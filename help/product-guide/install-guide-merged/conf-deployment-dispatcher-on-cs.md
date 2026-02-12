---
title: Deployment and dispatcher configuration
description: Learn Deployment and dispatcher configuration in Experience Manager Guides as a Cloud Service 
feature: Introduction, Installation
role: Admin
level: Experienced
---
# Deployment and dispatcher configuration 

This article provides information on how to deploy Experience Manager Guides as a Cloud Service and configure dispatcher. 

>[!NOTE]
>
> Starting 2024.2.0 release, Experience Manager Guides is only available as an automated add-on for Experience Manager as a Cloud Service. If you are using December 2023 or earlier releases, you can download the Adobe Experience Manager Guides from the GitHub repository and install it. 

## Deploy Experience Manager Guides as a Cloud Service

You can start by deploying Experience Manager Guides via the Cloud Manager. To deploy the module you can follow the instructions mentioned in [AEM Guides as a Cloud Service deployment](../release-info/deploy-xml-on-aemaacs.md).

## Configure dispatcher

Dispatcher is Adobe Experience Manager's caching and/or load balancing tool. For more details, refer to [Dispatcher in the Cloud](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/content-delivery/disp-overview.html?lang=en).

1.  For migrating dispatcher configuration from AMS to cloud service, refer to [Migrating the Dispatcher configuration from AMS to AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/content-delivery/ams-aem.html?lang=en).
1.  For details on how to configure dispatcher, see [Configuring Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=en).

>[!NOTE]
>
> AEM as a cloud service doesn't support dispatcher for author instance.
