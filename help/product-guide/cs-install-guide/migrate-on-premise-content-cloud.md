---
title: Migrate content from On-premise to Cloud Services 
description: Learn how to migrate the content from On-premise software to Cloud Services 
feature: Migration
role: Admin
level: Experienced
---
# Migrate content from On-premise to Cloud Service

Experience Manager as a Cloud Service provides a scalable, secure, and agile technology foundation for Experience Manager Assets, Forms, and Screens. This allows marketers and IT professionals to focus on delivering impactful experiences at scale.
With Experience Manager as a Cloud Service, your teams can focus on innovating instead of planning for product upgrades. New product features are thoroughly tested and delivered to your teams without interruption so they can always access the latest version of Adobe Experience Manager.
This article provides a detailed, step-by-step process for migrating your On-premise or Managed Services Experience Manager Guides content to Cloud Services, ensuring a smooth transition to the cloud-based platform.

## Migration process

**Content Transfer Tool** is a tool developed by Adobe that you can use to initiate the migration of existing content from a source Adobe Experience Manager On-premise or Managed Services instance to the target Experience Manager Cloud Service instance.
This tool also transfers principals (users or groups) automatically. 

You can download the **Content Transfer Tool** as a ZIP file from the **Software Distribution** portal:

1. Select **AEM as a Cloud Service** tab on the **Software Distribution** portal.
1. Search **Content Transfer Tool**.
1. Select **Content Transfer Tool** from the list and download it. 
 ![download content trasfer tool](../cs-install-guide/assets/software-distribution-downloads.png)

Then install the package via **Package Manager** on your source Adobe Experience Manager instance. Make sure to download the latest version. 
For more details on the latest version, view  [Release Notes](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/release-notes/release-notes-current.html?lang=en). 

>[!NOTE]
> 
> Only version 2.0.0 and higher is supported, and it's recommended to use the latest version.

### Pre-requisites

* Adobe Experience Manager 6.4 or later versions
* Upto 20TB repository size is supported
* Total Lucene Index size of 25 GB
* Length of a node name must be less than 150 bytes 


Perform the following steps to migrate your Experience Manager Guides content to Experience Manager as a cloud service.

1. Log in to [experience.adobe.com](https://experience.adobe.com/) and select **Experience Manager**.

    ![experience manager](./assets/migration-experience-manager.png) 


1. Click **Launch** on the **Cloud Acceleration Manager** tile.
 ![cloud acceleration manager](./assets/migration-experience-manager-cloud.png)

1. Create your first project.
  ![create project](./assets/migration-cloud-create-project.png)

1. Add the name and description and click **Create**. Your project is created.  
1. Select the created project and open the project screen.
1. Click **Review** on the **Content Transfer** tile.
 
    ![Review content transfer](./assets/migration-content-transfer-review.png)

1. Click **Create migration set**.

1. Provide the name and description for the migration set.
 
  
     ![create-migration-set](./assets/migration-cloud-create-migration-set.png)


1. After the creation, select the three dots and select **Copy extraction key**.
 

1. Click **Copy to clipboard**.
  Create your first project.
  ![extraction key](./assets/migration-copy-to-clipboard.png)

1. Select **Adobe Experience Manager**  on the top and then select the **Software Distribution** tile. 
 ![software distribution portal](./assets/migration-software-portal.png)


1. On the **Software Distribution** portal, select **Adobe Experience Manager as the Cloud Service** tab, search "content transfer tool",  and download the content transfer tool package.

    >[!NOTE]
    >
    >  Ensure you download the latest version.

1. Upload and install the package `content-transfer.all-3.0.10.zip` in the **Package Manager** of your On-premise instance.
    ![install package](./assets/migration-aem-cloud-service.png)

1. On the On-premise instance select **Tools** > **Operations** > **Content Migration** > **Content Transfer**.
 

1. Select **Content Transfer**, create a migration set, and paste the extraction key copied from the cloud acceleration manager. This establishes a connection between the source and the target. Then it verifies the key and shows the validity after entering the value.

1. Enable the **Include versions** option to include the file versions. 
 ![](./assets/migration-create-migration-set.png)

1. Provide the path you want to migrate and click **Save**. 
For example,  `/content/we-retail`
or
`/content/dam/wknd-events`
![included  paths](./assets/migration-included-paths.png)

 

    >[!NOTE]
    >
    > You need to migrate the following paths mandatorily for **Experience Manager Guides** content.

    * `/content/dam`
    * `/var/dxml`

    The following paths are restricted while creating a migration set:
    * `/apps`
    * `/libs`
    * `/home`
    * `/etc` You are allowd to select some `/etc` paths in CTT.

1. Click **Save** 
1. Select the **migration set** and then select **Extract** on the top.
 ![migration set extraction ](./assets/migration-extract.png)

1. Verify details in the **Migration Set Extraction** pop up for the paths and configurations you selected and click **Extract**. 
Extraction will take minutes, and you'll view the status as updated.
    ![migration set extraction](./assets/migration-set-extraction.png)
 
1. Once the extraction is complete and indicated by the status `finished`, go to Cloud Acceleration Manager  and select the project you created in step 18. 
For more information select the three dots, and then select **View details**. 


1. In the Migration set details pop-up, verify the migration set configuration and close the pop up.
 
    You can view the paths and other setings as shown in the following screenshot:
 ![migration-details](./assets/migration-details.png)


1. Click **Ingestion Jobs** > **New Ingestion**. 
1. Acknowledge the required checkmark values and then click **Create**.
 ![acknowledge migration checks](./assets/migration-new-ingestion-acknowledge.png)

1. Pick the migration set, select your environment's required server, and then click **Ingest**.

    ![new ingestion](./assets/migration-new-ingestion.png)



## Run Content Transfer Tool on a Publish Instance

Install Content Transfer Tool on the source Publish instance to move content to the target Publish instance. 
The Content Transfer Tool does not differentiate between published and unpublished content when ingesting content into a Publish environment. The content specified in the migration set is ingested into the chosen target instance. The user can ingest a migration set into an Author instance, Publish instance, or both. 

### Recommended Approach 

Consider the following recommendations: 

* Use the same version of the **Content Transfer Tool** that was used on the Author instance. 
* During ingestion to Publish, the Publish tier will not be scaled down (unlike the author). 
* Migrate only a single Publish node. Prior to beginning the extraction, remove it from the load balancer. 

>[!NOTE]
>
> As a precaution, make sure that no write operations happen on the Publish instances including user initiated actions like:
> * Content distribution from AEM as a Cloud Service Author to Publish in that environment 
> * User Sync between Publish instances

    
## Troubleshooting

If extraction fails due to the following error then you can resolve this by importing the relevant CA certificate: 

`javax.net.ssl.SSLHandshakeException: sun.security.validator.ValidatorException: PKIX path building failed: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target` 

**Reason**: The Adobe Experience Manager server has firewall restrictions, so add the following endpoint to the allowed list.

`casstorageprod.blob.core.windows.net`


![ssl logging](./assets/migration-ssl-logging.png)


*Enable SSL Logging.*
 



