---
title: Download and install AEM Sites templates
description: Learn how to Download and install AEM Sites templates
feature: Installation, AEM Sites
role: Admin
level: Experienced
---

# Download and install AEM Sites templates

Perform the following steps to download and install AEM Sites templates:


## Package installation

1.  Download the following AEM Sites templates: 
    * [guides-components-all.zip](
https://github.com/adobe/aemg-sites-components/).

    * [aemg-docs-1.0.0.zip](https://github.com/adobe/aemg-docs)

1.  Log into your AEM instance and navigate to the CRX Package Manager. The default URL to access the package manager is:

    ```http
    http://<server name>:<port>/crx/packmgr/index.jsp
    ```

    The Package Manager manages the packages on your local AEM installation. For more information about working with the Package Manager, see [How to Work With Packages](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/package-manager.html) in AEM documentation.

1.  To upload the package, click **Upload Package**.

1.  In the **Upload Package** dialog box, navigate to the file that you downloaded in Step 1 and click **OK**.

    The package is uploaded to your AEM instance.

1.  To install the package, click **Install**.

1.  In the **Install Package** dialog box, click **Install** to install the packages. 


## Configure the templates to use with the AEM Sites presets

Once the package is installed, **AEMG** folder is created in the Sites UI with the following components. 
- Within the **AEMG** folder, Experience Manager Guides provides many out-of-the-box samples like **Search**, **Sign in**, **Docs**,  and **Support**. 
- A language folder for English(en)is present in the **AEMG** folder. You can create similar folders for other languages. For example, French (fr).   
- A sample folder **Product1** is present in the **Docs** folder.   
- Experience Manager Guides also provides the following out-of-the-box templates: 

    - **Content Page**
    - **Home Page**
    - **Topic Page**
   
   ![Sites template](assets/sites-ui-templates.png)
   
Use these samples and templates to generate your AEM Sites outputs. For example, you can use the **Home Page** template in the **Product1** folder to create your product Home page. You can also create your topic pages using the **Topic Page** template.


Besides the out-of-the-box templates, you can also create your custom templates.

Perform the following steps to create the custom templates for your AEM Sites:  
1. Once the package are installed, select **Sites** from the Global Navigation.
1. Select the "AEMG Docs" template installed in the Sites UI.
1. Within the Sites UI, click **Create** button on the top-right corner.
1. Select **Page** from the **Create** dropdown.
1. Select **Home page** and then click **Next**. 
1. Enter the Site title and the Site name and click **Create** on the top-right corner. An AEM site template is created using the **Home page** site template. For example, you can create a Home page for your product `Product ABC`.


>[!NOTE]
>
>Once you have created the Home Page, you can use this path as the **Publish Path** for generating the output of your AEM Sites presets. For example, `aemg-docs-en/docs/product-abc`.

## Editing topic templates for AEM Sites
You can also customize the topic templates for your AEM Sites. You can edit the content or configure the properties of the different AEM components in your topic. For example, you can add components, or change the font, or the background of the components.  
Perform the following steps to edit the topic templates:
1. Select the template that you wish to edit. 
1. Select the **Edit** icon on the top.

The AEM Template Editor opens. You can edit your topic template. Learn more about [Creating Page Templates](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/authoring/siteandpage/templates#editing-a-template-structure-template-author).





