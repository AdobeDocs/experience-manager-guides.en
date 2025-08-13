---
title: Download and install AEM Sites templates
description: Learn how to Download and install AEM Sites templates
feature: Installation
role: Admin
level: Experienced

---
# Download and install AEM Sites templates (on Prem Services)

This guide provides step-by-step instructions to set up and configure the latest AEM Guides template for generating AEM Sites. Follow these steps to install the required packages, create and configure presets, and generate AEM Sites.

## Prerequisites

Before proceeding with the setup, ensure the following pre-requisites are met:

- **Adobe Experience Manager (AEM):** A running instance of **AEM 6.5** with **Service Pack** 21, 20, and 19 and **AEM Guides 4.6.0**, or later versions installed.

- **Required Permissions**: Download the following packages:

    - Access to  **Software Distribution Portal** to download the required packages
    - Access to **CRX Package Manager** to install packages in AEM.
    - Permissions to create and modify presets in AEM Guides.

- **Download Packages**: Download the following packages from **Software Distribution Portal**:

    - Components package: on-prem-guides-components.all-1.x.0.zip
    - Sites package: aemg-docs.all-1.x.0.zip    

## Package installation using CRX Package Manager
  
1. **Install the Components Package:**  
    1. Navigate to **CRX Package Manager** (http://<your-aem-instance>/crx/packmgr).
    2. Upload and install the on-prem-guides-components.all-1.x.0.zip package.
    
2. **Install the Sites Package:** o    Upload and install the aemg-docs.all-1.x.0.zip package using the CRX Package Manager.
   

## Create and configure AEM Site Preset

1. **Create a new preset:**
    1. Open a DITA map in AEM Guides and navigate to the **Output** panel.
    2. Select **Create Preset**.
    3. Select the type as **AEM Sites**.
    4. Enter a name for the preset.
    5. Uncheck the **Use legacy component mapping** setting.
    6. Select **Add** to create the preset.
2. **Configure AEM Site Preset:** There are two options to configure the out-of-the-box (OOTB) site:

    **Option 1: Use the Site Dropdown**

    1. Select **Site** as **AEMG Docs**.
    2. Verify that the **Publish path** and **Topic page template** are automatically set to: Publish path: aemg-docs/en/docs/product1 and Topic page template: Topic Page.

    **Option 2: Use the Site Path**

    1. Set the **Site path** manually as /content/aemg-docs/en/docs/product1.
    2. Verify that the **Topic page template** is automatically set to Topic Page.

3. Save the changes made to the preset.

## Generate AEM Sites

1. **Generate Site:**
    1. With the preset configured, you can now generate the AEM Site for the corresponding DITA map.
    2. The generated site will be available at the path: /content/aemg-docs/en/docs/product1.
2. **Change the Default Generation Path (Optional):**
As an optional step, if you want to change the default path for site generation:
    1. Navigate to **AEM Sites**.
    2. Create a new product page under the OOTB site structure.
    3. Navigate to **AEMG Docs** > **English** > **Docs**. 
    4. Select the **Home** page and then select **Next**.
    5. Enter the **Title** and **Name** for the page.
    6. Select **Create**.

## Change the Default Path to generate site pages

1. The default path for site generation can be customized as needed by creating new pages in the AEM Sites structure.
2. Select  Home page and then select **Next**.
3. Enter the **Title** and **Name** for the page and select **Create**.

