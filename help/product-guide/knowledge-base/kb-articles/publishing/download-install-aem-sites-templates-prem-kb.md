---
title: Download and install AEM Sites templates for on-Prem Services
description: Learn how to Download and install AEM Sites templates for on Prem Services
feature: Installation
role: Admin
level: Experienced

---
# Download and install AEM Sites templates (On-Premise services)

This guide provides step-by-step instructions to set up and configure the latest AEM Guides template for generating AEM Sites. Follow these steps to install the required packages, create and configure presets, and generate AEM Sites.

## Prerequisites

Before proceeding with the setup, ensure the following pre-requisites are met:

- **Adobe Experience Manager (AEM):** A running instance of **AEM 6.5** with **Service Pack** 21, 20, and 19 and **AEM Guides 4.6.0**, or later versions installed.

- **Required Permissions**: Ensure to have the following permissions:

    - Access to  **Software Distribution Portal** to download the required packages
    - Access to **CRX Package Manager** to install packages in AEM.
    - Permissions to create and modify presets in AEM Guides.

- **Download Packages**: Download the following packages from **Software Distribution Portal**:

    - Components package: on-prem-guides-components.all-1.x.0.zip
    - Sites package: aemg-docs.all-1.x.0.zip    

## Package installation using CRX Package Manager
  
1. **Install the Components Package:**  
    1. Navigate to [**CRX Package Manager**](http://<your-aem-instance>/crx/packmgr).
    2. Upload and install the on-prem-guides-components.all-1.x.0.zip package.
    
2. **Install the Sites Package:** Upload and install the aemg-docs.all-1.x.0.zip package using the CRX Package Manager.
   

## Create and configure AEM Site Preset

1. **Create a new preset:**
    1. Open a DITA map in AEM Guides and navigate to the **Output** panel.
    2. Select **Create Preset**.
    3. Select the type as **AEM Sites**.
    4. Enter a name for the preset.
    5. Uncheck the **Use legacy component mapping** setting.
    6. Select **Add** to create the preset.

        ![New output preset dialog](/help/product-guide/knowledge-base/kb-articles/assets/publishing/new-output-preset.png){width="350" align="left"}

    
2. **Configure AEM Site Preset:** There are two options to configure the out-of-the-box (OOTB) site:

    **Option 1: Use the Site Dropdown**

    1. Select **Site** as **AEMG Docs**.
    2. Verify that the **Publish path** and **Topic page template** are automatically set to:    
        - Publish path: aemg-docs/en/docs/product1 
        - Topic page template: Topic Page.

        ![Use Site Dropdown](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-dropdown.png){width="350" align="left"}

    **Option 2: Use the Site Path**

    1. Set the **Site path** manually as /content/aemg-docs/en/docs/product1.
    2. Verify that the **Topic page template** is automatically set to Topic Page.

        ![Use Site Path](/help/product-guide/knowledge-base/kb-articles/assets/publishing/use-site-path.png){width="350" align="left"}

3. **Save the preset:** Save the changes made to the preset.

## Generate AEM Sites

1. **Generate Site:**
    1. With the preset configured, you can now generate the AEM Site for the corresponding DITA map.
    2. The generated site will be available at the path: /content/aemg-docs/en/docs/product1.
2. **Change the Default Generation Path (Optional):** If you want to change the default path for site generation, perform the following steps:

    1. Navigate to **AEM Sites**.
    2. Create a new product page under the OOTB site structure.
    3. Navigate to **AEMG Docs** > **English** > **Docs**.

        ![Create page in AEM Site structure ](/help/product-guide/knowledge-base/kb-articles/assets/publishing/create-new-page.png){width="350" align="left"}

    4. Select the **Home page** tile and then select **Next**.

        ![Select home page tile](/help/product-guide/knowledge-base/kb-articles/assets/publishing/home-page-tile.png){width="350" align="left"}

    5. Enter the **Title** and **Name** for the page.
    6. Select **Create**.

