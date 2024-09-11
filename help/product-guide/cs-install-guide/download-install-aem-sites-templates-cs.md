
---
title: Download and install AEM Sites templates
description: Learn how to Download and install AEM Sites templates
feature: Installation, AEM Sites
role: Admin
level: Experienced
---

# Download and install  AEM Sites templates

Perform the following steps to download and install  AEM Sites templates:





## Package installation

To use the templates, install the components package via cloud deployment: 
* [guides-components-all.zip](
https://github.com/adobe/aemg-sites-components/).

    * [aemg-docs-1.0.0.zip](https://github.com/adobe/aemg-docs)
    
Perform the following steps to create an AEM Sites using the template: 


1. Create AEM Sites using the template: 
    1. Go to AEM Sites page.
    1. Select **Create** and then choose **Site** option.
    1. Import sites template `aemg-docs-1.0.0.zip` using **Import** option.
    1. Select `AEMG Docs 1.0.0` and then click **Next**.
    1. Enter `Site title` and `Site name`.
    1. Click **Create**.
    
Learn more about [Adding a Site Template to AEM](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/sites/administering/site-creation/site-templates#adding).


1. Once the package are installed, select **Sites** from the Global Navigation.
1. Select the "AEMG Docs" template installed in the Sites UI.
1. Within the Sites UI, click **Create** button on the top-right corner.
1. Select **Page** from the **Create** dropdown.
1. Select **Home page** and then click **Next**. 
1. Enter the Site title and the Site name and click **Create** on the top-right corner. An AEM site template is created using the **Home page** site template. For example, you can create a Home page for the your product `Product ABC`.


>[!NOTE]
>
>Once you have created the Home Page, you can use this path as the **Publish Path** for generating the output of your AEM Sites presets. For example, `aemg-docs-en/docs/product-abc`.