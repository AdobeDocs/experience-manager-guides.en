---
title: Download and install AEM Sites templates
description: Learn how to Download and install AEM Sites templates
feature: Installation
role: Admin
level: Experienced
exl-id: ca446ee4-a377-4e08-8008-21db3a2fe669
---
# Download and install AEM Sites templates

Perform the following steps to download and install AEM Sites templates on Experience Manager Guides for On-premise Software:


## Package installation

1.  Download the following packages

    - Components: [guides-components-all.zip](https://github.com/adobe/aemg-sites-components/releases/tag/v1.0.0)

    - Sites for On-Premise Software: [Docs](https://github.com/adobe/aemg-docs/releases/tag/v1.0.0) 

1.  Log into your AEM instance and navigate to the CRX Package Manager. The default URL to access the package manager is:

    ```http
    http://<server name>:<port>/crx/packmgr/index.jsp
    ```

    The Package Manager manages the packages on your local AEM installation. For more information about working with the Package Manager, view [How to Work With Packages](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html) in AEM documentation.

1.  To upload the package, click **Upload Package**.

1.  In the **Upload Package** dialog box, navigate to the file that you downloaded in Step 1 and click **OK**.

    The package is uploaded to your AEM instance.

1.  To install the package, click **Install**.

1.  In the **Install Package** dialog box, click **Install** to install the packages. 


## Configure the templates to use with the AEM Sites presets

Once the packages are installed, a site named **AEMG** is created in the Sites UI. This sample site shows how you can set up the site structure for generating AEM Sites output. This is just a sample. You can create custom sites per your requirements.

![AEMG Sites sample pages](assets/aemg-sites-sample-pages.png)


 **AEMG** contains the following components. 
- A folder for English(en) language is present in the **AEMG** folder. You can create similar language copies as per your requirements. For example, a multilingual website includes English (en), German (de), and French(fr) language copies.  Learn more about how to create a language copy using the [Language Copy Wizard](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/introduction/tc-wizard).
- Within the English(en) language folder, Experience Manager Guides provides many out-of-the-box sample pages like **Search**, **Sign in**, **Docs**, and **Support**. 

- **Docs** is the sample Documentation Home Page. It serves as a central location for all product-related documentation
 and displays each product for which documentation is available as individual tiles.

- Along with the Documentation Home Page, there are sample pages for **Search**, **Sign in**, and **Support**. You can customize these samples as per your requirements.  
- You can have home pages for individual products such as Product1. A sample page **Product1** is present under **Docs**, which is the Documentation Home Page. 
 
- Experience Manager Guides also provides the following predefined templates: 

    - **Content Page** template: Use this template to create the standard pages that contain most of the product site's content. They can include text, images, videos, and other content elements. This template contains only the header and the footer. Customize and use it to create any page as per your requirements. For example, you can create the support page or the sign-in page for your product.
    - **Home Page** template: The main landing page of a website, which includes an overview, key sections like the key elements and features, and navigation links. For example, the main page of a product ABC connects to the other content or feature pages.
    - **Topic Page** template: The pages used for organizing and presenting topic-based content. For example, a user guide contains different topic pages, each of which contains a specific topic related to features and troubleshooting.
   
   ![Sites template](assets/sites-ui-templates.png)
   
Use these samples and templates to generate your AEM Sites outputs:
- A product home page corresponds to a map home page and is created using the Home Page template. Select this path in the AEM Sites preset to publish the map’s contents under it. The product home page can include other home pages. 
- For example, you have a product like Experience Manager Guides and need three manuals for users, administrators, and developers.  Create a home page for each manual using the Home Page template and then select the corresponding home page in the AEM Sites output preset.

Learn more about how the create and configure [AEM Sites presets in the Web Editor](../user-guide/generate-output-aem-site-web-editor.md).

## Create a home page using the template

Perform the following steps to create the home page for your product:  
1. Once the package is installed, select **Sites** from the Global Navigation.
1. Select the "AEMG Docs" template installed in the Sites UI.
1. Within the Sites UI, click the **Create** button on the top-right corner.
1. Select **Page** from the **Create** dropdown.
1. Select **Home Page** and then click **Next**. 
1. Enter the Site title and the Site name and click **Create** on the top-right corner. An AEM site template is created using the **Home Page** site template. For example, you can create a home page for your product `Product ABC`.


>[!NOTE]
>
>Once you have created the home page, you can use this path as the **Publish Path** for generating the output of your AEM Sites presets. For example, `aemg-docs-en/docs/product-abc`.

## Edit topic templates for AEM Sites

You can also customize the topic templates for your AEM Sites. You can edit the content or configure the properties of the different AEM components in your topic. For example, you can add or remove components as per your requirements.  
Perform the following steps to edit the topic templates:
1. Select the template that you wish to edit. 
1. Select the **Edit** icon on the top.

The AEM Template Editor opens. You can edit your topic template. Learn more about [Creating Page Templates](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/authoring/siteandpage/templates#editing-a-template-structure-template-author).


## Customize existing AEM Sites templates 

Besides the predefined templates, you can also use your existing templates with the AEM Sites presets. Perform the following steps to customize existing AEM Sites templates:

### Template Setup

You need the following two types of templates:

- Category or Landing Template: This template is used for the Product documentation landing page and corresponds to a DITA map.  AEM Site Page for a DITA map is generated using this template. You can use this template at any level.
        - Add a text component to your existing template. The text component should have a mandatory property, `text="$category.html$"`.
        - For example, you can pick we-retail templates and use the section-page template as the landing page template for the DITA map. To do so, make the changes as shown in the following screenshot:
![section page template](assets/customize-existing-aem-templates-section.png)
    -  Detail Page or Topic Page Template: Use this template for the content of topics of a map. All the Sites pages of DITA/XML content are created using Topic Page templates. To create these templates, there are two pre-requisites:
        - Add a text component to the template, contained in a container component, with a mandatory property. `text="$topic.content$"`. 
![container page template](assets/customize-existing-aem-templates-container.png)
       - Reflect the same container and text component in the structure of the same template, as shown in the following screenshot:
![structure of container template](assets/customize-existing-aem-templates-structure.png)

### Tag Category Page as documentation container

Assuming a site hierarchy is created for the documentation pages using the previous template, choose one of the category pages created in that site hierarchy. Tag the category page as a Documentation container by giving it an ID. 
To do so, assign its property `id` a value `category-page`. Refer to the following screenshot:
 
![tag category page](assets/customize-existing-aem-templates-tagging.png)
