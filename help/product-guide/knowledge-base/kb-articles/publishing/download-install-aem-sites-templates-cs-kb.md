---
title: Download and install AEM Sites templates for Cloud services
description: Learn how to Download and install AEM Sites templates for Cloud services
feature: Installation
role: Admin
level: Experienced
exl-id: 67f7ff26-fbc7-426c-aa7d-9bf4debf05d8
---
# Download and install AEM Sites templates (Cloud services)

This guide provides step-by-step instructions to set up and configure the latest AEM Guides template for generating AEM Sites pages in a cloud environment. Follow these steps to install the required packages, create and configure presets, and generate AEM Sites.

## Prerequisites

Before proceeding with the setup, ensure the following pre-requisites are met:

- **Adobe Experience Manager (AEM) Cloud**: A running instance of **AEM as a Cloud Service** with **AEM Guides 2502 or later versions**.

- **Required Permissions**: You must have the following permissions:

    - Access to **Cloud Manager** to deploy packages.
    - Access to **Git Repository** associated with your environment.
    - Permissions to create and modify presets in AEM Guides.

- **Download Packages**: Download the following packages from Software Distribution Portal:

    - Components package: guides-components.all-1.x.0.zip
    - Sites template: aemg-docs-1.x.0.zip    

## Package installation via Cloud deployment

Install the **Components Package (guides-components.all-1.x.x.zip)** and perform the following steps
  
1. **Clone Git repository:**  
    1. Navigate to **Repositories** in the left panel of Cloud Manager.
    2. Select **Access Repo Info** and copy the git clone command.

        ![Select Access Repo info](/help/product-guide/knowledge-base/kb-articles/assets/publishing/access-repo.png){width="350" align="left"}

    3. Clone the repository to your local system using the provided username and password (generate password if required).
2. **Add Package to Maven Bundle:**
    1. In your locally cloned repository, create a new Maven bundle or add to an existing one.
    2. Ensure the structure `/jcr_root/apps/fmdita/` install exists in the Maven project.

        ![Structure in Maven project](/help/product-guide/knowledge-base/kb-articles/assets/publishing/maven-structure.png){width="650" align="left"}


    3. Place the downloaded guides-components.all-1.x.x.zip file in the install folder.
     
3. **Update filters.xml:**  

    1. Open the filters.xml file located in the META-INF folder of the parent content directory.
    2. Add the following filter: filter root=`/apps/fmdita` mode=`merge`/


        ![Add filter](/help/product-guide/knowledge-base/kb-articles/assets/publishing/add-filter-xml.png){width="650" align="left"}


4. **Configure pom.xml:** Update the pom.xml file as per your environment requirements.
5. **Push changes and run Pipeline:** 
    1. Push the changes to the main Git repository.
    2. Navigate to **Pipelines** in Cloud Manager and run the pipeline for the desired environment.
6. **Verify installation:** Once the deployment is complete, the components package will be installed on the AEM Cloud environment.

## Create Site using installed templates

1. **Import Sites Template:**
    1. Go to the AEM Sites page (servername/sites.html/content).
    2. Select **Create** > **Site** from Template.
    3. Import the sites template aemg-docs-1.x.x.zip using the **Import** option.
2. **Select Template:** Select **AEMG Docs 1.x.x** and then select **Next**.
3. **Enter Site Details:** Enter the **Site Title** and **Site Name**.

    ![Create Site](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-site.png){width="350" align="left"}

4. Select **Create**.

## Create AEM Site Preset

1. **Create a new preset:**
    1. Open a DITA map in AEM Guides and navigate to the **Output** panel.
    2. Select **Create Preset**.
    3. Select the type as **AEM Sites**.
    4. Enter a name for the preset.
    5. Uncheck the **Use legacy component mapping** setting.

        ![Create new AEM Site preset](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-new-output-preset.png){width="350" align="left"}

    6. Select **Add** to create the preset.
2. **Configure AEM Site Preset:** There are two options to configure the out-of-the-box (OOTB) site:

    **Option 1: Use the Site Dropdown**

    1. Select **Site** as the one created above (e.g., AEMG Docs Site).
    2. Verify that the **Publish path** and **Topic page** template are automatically set to: 
        - Publish path: `/content/AEMG-Docs-Site/en/docs/product`
        - Topic page template: Topic Page

        ![Use the site dropdown to configure the AEM Site](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-dropdown-cs.png){width="350" align="left"}

    **Option 2: Use the Site Path**

    1. Set the **Site path** manually as `/content/AEMG-Docs-Site/en/docs/product`.
    2. Verify that the **Topic page** template is automatically set to Topic Page.

        ![Use the site path to configure the AEM Site](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-path-cs.png){width="650" align="left"}

3. **Save the preset:** Save the changes made to the preset.

## Generate AEM Sites

1. **Generate Site:**
    1. With the preset configured, generate the AEM Site for the corresponding DITA map.
    2. The generated site will be available at the path: `/content/AEMG-Docs-Site/en/docs/product`.
2. **Change the Default Generation Path (Optional):** If you want to change the default path for site generation, perform the following steps:
    1. Navigate to **AEM Sites**.
    2. Create a new product page under the OOTB site structure.
    3. Navigate to **AEMG Docs** > **English** > **Docs**.

        ![Create page](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-page-cs.png){width="650" align="left"}      

    4. Select the **Home page** tile and then select **Next**.

        ![Select Home tile](/help/product-guide/knowledge-base/kb-articles/assets/publishing/home-tile-cs.png){width="650" align="left"}

    5. Enter the **Title** and **Name** for the page.
    6. Select **Create**.

>[!NOTE]
>
> Ensure all configurations are tested in a non-production environment before deploying to production. <br><br> Refer to the official [Deploying to AEM as a Cloud Service documentation](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/deploying/overview) for additional details.
