---
title: Deployment and dispatcher configuration
description: Learn Deployment and dispatcher configuration in Experience Manager Guides as a Cloud Service 
feature: Introduction, Installation
role: Admin
level: Experienced
---
# Deployment and dispatcher configuration 

This article provides information on how to deploy Experience Manager Guides as a Cloud Service and configure dispatcher. 

## Deploy Experience Manager Guides as a Cloud Service

You can start by deploying Experience Manager Guides via the Cloud Manager. To deploy the module follow the instructions mentioned in [AEM Guides as a Cloud Service deployment](../release-info/deploy-xml-on-aemaacs.md).

>[!NOTE]
>
> Starting 2024.2.0 release, Experience Manager Guides is only available as an automated add-on for Experience Manager as a Cloud Service. If you are using December 2023 or earlier releases, you can download the Adobe Experience Manager Guides from the GitHub repository and install it. If you use manual deployments for Experience Manager Guides, remove the line `<module>dox.installer</module> from file dox/pom.xml` in your cloud manage git codebase before enabling Experience Manager Guides for your program.

Perform the following steps to deploy the Experience Manager Guides module:

1. Login to [!UICONTROL Cloud Manager].

1. Edit the program for which you want to configure [!DNL Experience Manager Guides].

1. Switch to **[!UICONTROL Solutions and Add-ons]** tab.

1. In the **[!UICONTROL Solutions and Add-ons]** table, click on **[!UICONTROL Assets]**.

1. Select **[!UICONTROL Guides]** and select **[!UICONTROL Save]**.

You have successfully configured your program for automatic provisioning of Experience Manager Guides solution.

![Configuring Experience Manager Guides solution](assets/addon-configuration.png)

>[!NOTE]
>
>To install [!DNL Experience Manager Guides] on any environment under the integrated program, you must run the pipeline associated with the environment. No additional configuration is required in your CM git codebase for installing [!DNL Experience Manager Guides].


## Configure dispatcher

Dispatcher is Adobe Experience Manager's caching and/or load balancing tool. For more details, refer to [Dispatcher in the Cloud](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/content-delivery/disp-overview.html?lang=en).

1.  For migrating dispatcher configuration from AMS to cloud service, refer to [Migrating the Dispatcher configuration from AMS to AEM as a Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/content-delivery/ams-aem.html?lang=en).
1.  For details on how to configure dispatcher, see [Configuring Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html?lang=en).

>[!NOTE]
>
> AEM as a Cloud Service doesn't support dispatcher for author instance.
