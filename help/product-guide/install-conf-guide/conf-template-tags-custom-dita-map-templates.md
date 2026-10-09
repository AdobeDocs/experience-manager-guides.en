---
title: Configure custom DITA map template
description: Learn how to Configure custom DITA map template
feature: Template Configuration
role: Admin
level: Experienced
exl-id: 467cc4be-5fe7-466e-887b-eccc63acae8a
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: df6fa66f-4542-4a6d-90ca-9f146eb5d494
    internal-label: Template configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
---
# Configure custom DITA map template {#id1774F04F05Z}

AEM Guides comes with two out-of-the-box map templates — DITA map and Bookmap. You can create maps based on these templates; or, you can define your own map templates that can then be used to create new maps.

The following tabs provide instructions to configure custom DITA map template based on your Experience Manager Guides setup: Cloud Service or On-Premise.


>[!BEGINTABS]

>[!TAB Cloud Service]

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

>[!TAB On-Premise]

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

>[!ENDTABS]

The Map Created message appears.

    You can choose to open the template for editing in the Map Editor, or save the template file in the template store location. Once the template is created, you can use the Map Editor to customize the template as per your authoring needs. Once a template is in place, ensure that you associate it either with a global or folder-level profile.


Next time you create a new map, your template shows up in the Blueprint page. For more information about creating a DITA map, see the *Using Adobe Experience Manager Guides*.

>[!TIP]
>
> See the *Custom templates* section in the Best practices guide for best practices around using custom map templates.


## Customize the number of references in a DITA map (Only for Cloud Service)

You can configure the threshold for asynchronous processing based on the number of references in the DITA map. By default, maps with more than 5 references will be created via asynchronous operations, while maps with fewer references will continue using synchronous operations.

Use the instructions given in [Configuration overrides](download-install-config-override.md#) to create the configuration file. In the configuration file, provide the following (property) details to specify number of references in the DITA map template to keep the process synchronous:

|PID|Property Key|Property Value|
|---|------------|--------------|
|com.adobe.fmdita.xmleditor.config.XmlEditorConfig|xmleditor.asyncmapcreation|> 0 <br> **Default value**: 5|

When creating a DITA map with large topic references using a custom template, the map creation would fail on the cloud server if the total processing time exceeds 60 seconds.

To prevent this, configure **asynchronous dita map creation** in XmlEditorConfig that allows tasks to run in parallel and reduce processing times for larger DITA maps. 


**Parent topic:** [Configure topic and map templates](conf-template-tags.md)
