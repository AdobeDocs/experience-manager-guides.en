---
title: Configure custom DITA map template
description: Learn how to Configure custom DITA map template
exl-id: a0eeb43c-06e4-4922-a005-704e8929063f
feature: Template Configuration
role: Admin
level: Experienced
---
# Configure custom DITA map template {#id1774F04F05Z}

AEM Guides comes with two out-of-the-box map templates — DITA map and Bookmap. You can create maps based on these templates; or, you can define your own map templates that can then be used to create new maps.

Perform the following steps to add your custom map templates:

1.  Log into Adobe Experience Manager as an administrator.

1.  In the Assets UI, navigate to the folder configured to store the map template files. By default, all map templates are stored in the /content/dam/dita-templates/maps folder.

    >[!NOTE]
    >
    > To configure a custom location to store topic or map templates, see [Configure custom DITA template folder path](conf-template-tags-custom-dita-topic-template.md#id191LCF0095Z)

1.  Click **Create** \> **DITA Template**.

1.  On the Blueprint page, select the type of the map template that you want to create.

    >[!NOTE]
    >
    > You can use the Map or Bookmap template as the base for your new template.

1.  Click **Next**.

1.  On the new template Properties page, enter a **Title** and **Name** for the template.

    >[!NOTE]
    >
    > The name is automatically suggested based on the Title of your template. If you want to manually specify the name, then ensure that the Name does not contain any spaces, apostrophe, or braces and ends with .ditamap.

1.  Click **Create**.

    The Map Created message appears.

    You can choose to open the template for editing in the Map Editor, or save the template file in the template store location. Once the template is created, you can use the Map Editor to customize the template as per your authoring needs. Once a template is in place, ensure that you associate it either with a global or folder-level profile.


Next time you create a new map, your template shows up in the Blueprint page. For more information about creating a DITA map, see the Using Adobe Experience Manager Guides as a Cloud Service guide.

>[!TIP]
>
> See *the Custom templates* section in the Best practices guide for best practices around using custom map templates.


## Customize the number of references in a DITA map

Your DITA map creation fails if the async operation timings exceeds 60 seconds. You can configure the number of references in a DITA map template for which the map creation is a sync operation. 

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following (property) details to specify number of references in the DITA map template to keep the process synchronous:

|PID|Property Key|Property Value|
|---|------------|--------------|
|com.adobe.fmdita.xmleditor.config.XmlEditorConfig|	xmleditor.asyncmapcreation|> 0 <br> **Default value**: 5|



**Parent topic:** [Configure topic and map templates](conf-template-tags.md)
