---
title: Manage replication of DITA source assets
description: Learn how to do replication of DITA source assets
feature: Publishing
role: User
exl-id: 71aec782-2cc1-4fd5-b35b-97a603c3dd48
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: f59890ff-de81-47d5-9ef8-7ab2dd10c6c3
    internal-label: Authoring and publishing content
subfeature_v2:
  - id: f901afa4-5613-4581-add5-219fa5f03fb5
    internal-label: Publishing
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Manage replication of DITA source assets

When the output generated from DITA content are published using **Quick Publish** or **Manage Publication** on some publish environment, AEM also attempts to publish the associated DITA source assets, such as DITA maps and, in some cases, DITA topics. This occurs because AEM treats DITA assets as dependencies of the generated Sites pages. 

 ![](images/quick-publish-site-instance.png){width="350"}

To prevent the unintended replication of DITA content to the publish environment and to avoid performance issues, Administrators must explicitly manage DITA asset replication through the Configuration Manager. This configuration enables administrators to control the replication of supported DITA asset types, including DITA maps, DITA topics, XML files, and Markdown (.md) files. 

To configure the DITA assets replication feature, view  [Configure DITA assets replication for Cloud Service](../cs-install-guide/configure-dita-assets-replication.md) or [Configure DITA assets replication for On-Premise](../install-guide/configure-dita-asset-replication.md) depending on the setup you are using
