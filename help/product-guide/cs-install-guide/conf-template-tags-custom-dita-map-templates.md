---
title: Configure custom DITA map template
description: Learn how to Configure custom DITA map template
exl-id: a0eeb43c-06e4-4922-a005-704e8929063f
feature: Template Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/0Twn4ztwqhAEC2p9-YXKJPdoXWIAmimET-F-chIrAHk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: a7bba4a6-624b-4427-a9b8-dd411a1bfd41
    internal-label: Map Editor
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
  - id: df6fa66f-4542-4a6d-90ca-9f146eb5d494
    internal-label: Template configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
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

You can configure the threshold for asynchronous processing based on the number of references in the DITA map. By default, maps with more than 5 references will be created via asynchronous operations, while maps with fewer references will continue using synchronous operations.
 

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following (property) details to specify number of references in the DITA map template to keep the process synchronous:

|PID|Property Key|Property Value|
|---|------------|--------------|
|com.adobe.fmdita.xmleditor.config.XmlEditorConfig|xmleditor.asyncmapcreation|> 0 <br> **Default value**: 5|

When creating a DITA map with large topic references using a custom template, the map creation would fail on the cloud server if the total processing time exceeds 60 seconds.

To prevent this, configure **asynchronous dita map creation** in XmlEditorConfig that allows tasks to run in parallel and reduce processing times for larger DITA maps. 

**Parent topic:** [Configure topic and map templates](conf-template-tags.md)
