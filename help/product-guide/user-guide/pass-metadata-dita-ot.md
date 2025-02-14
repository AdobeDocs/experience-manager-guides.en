---
title: Pass on the metadata to the output using DITA-OT
description: Learn how to pass on the metadata to the output using DITA-OT publishing in AEM Guides.
exl-id: 70ca32dc-56c3-45ee-b6b9-0efb8cc79ea1
feature: Publishing, Metadata Management
role: User
---
# Pass on the metadata to the output using DITA-OT {#id21BJ00QD0XA}

Metadata is additional information about the output. In Adobe Experience Manager Guides, you can pass on the existing metadata or create custom metadata tags. You can pass on metadata to AEM, PDF, HTML5, EPUB, and Custom format outputs using DITA-OT publishing.

Perform the following steps to pass on the metadata to the output using DITA-OT publishing:

1.  [Open the DITA map file in map console](./open-files-map-console.md) for which you want to pass the metadata to the DITA-OT. 
1.  Select and open an output preset to which you want to pass the metadata fields. For example, select PDF output preset. Ensure that it is created using the **DITA-OT** option. 

    >[!NOTE]
    >
    > You can also use the Map dashboard to pass on the metadata to the output. For this, you can open the DITA Map file in the Assets UI for which you want to pass the metadata to the DITA-OT. In the **Output Presets** tab, select and edit an output preset to which you want to pass the metadata fields. Select the **DITA-OT** option under Generate <output\> Using in the selected output Preset.

1.  From the **File properties** dropdown select the metadata that you want to pass to DITA-OT publishing.

    ![](images/custom-metadata-output-preset-new.png){width="800" align="left"}

    Properties dropdown lists both the custom and the default properties. For example, in the above screenshot `dc:description`, `dc:language`, `dc:title`, and `docstate` are the default properties.

    >[!NOTE]
    >
    > These properties are picked from the metadataList file available at the following location:`/libs/fmdita/config/metadataList`. By default, there are four properties listed in this file- `dc:description`, `dc:language`, `dc:title`, and `docstate`.

    This file can be overlaid at: `/apps/fmdita/config/metadataList`.

    To pass a custom property for which you have already defined the values, view [Use AEM Metadata in DITA-OT PDF output](https://experienceleaguecommunities.adobe.com/t5/xml-documentation-discussions/use-aem-metadata-in-dita-ot-pdf-output/td-p/411880).

1.  The selected properties are listed below the dropdown.

    ![](images/metadata-added-dropdown.png){width="300" align="left"}

1.  Select **Save** on the top right to save the changes.
1.  Select **Generate output**. 

The selected metadata properties will be passed to the output generated using DITA-OT.

>[!NOTE]
>
> As of 2025.02.0 and 5.0 release of Experience Manager Guides, the functionality to pass root map metadata arguements through DITA-OT command line has been deprecated. However, to avoid any disruptions, a new property has been added in the `Config.Manager` to enable or disable the functionality.  For more details, view [Configure output generation settings](../cs-install-guide/conf-output-generation.md#configure-the-dita-ot-command-line-arguement-field-on-the-dita-map-dashboard).

**Using Map dashboard**

If working on the **Assets UI**, perform the following steps to pass on the metadata to the output using DITA-OT publishing:

1. In the **Assets UI**, navigate to and choose the DITA map file for which you want to pass the metadata to the DITA-OT.
1. Select and edit an output preset to which you want to pass the metadata fields. For example, select PDF output preset.
1. Select **DITA-OT** under **Generate /<output> Using** option in the selected output preset.

    ![](images/custom-meta-data-output-preset.png){width="800" align="left"}

1. From the Properties drop down select the metadata that you want to pass to DITA-OT publishing.

    Properties dropdown lists both the custom and the default properties. For example, in the above screenshot author is the custom property while `dc:description`, `dc:language`, `dc:title`, and `docstate` are the default properties.

    >[!NOTE]
    >
    > These properties are picked from the metadataList file available at the following location:`/libs/fmdita/config/metadataList`. By default, there are four properties listed in this file- `dc:description`, `dc:language`, `dc:title`, and `docstate`.

    This file can be overlaid at: `/apps/fmdita/config/metadataList`.

    To pass a custom property for which you have already defined the values, see [Use AEM Metadata in DITA-OT PDF output](https://experienceleaguecommunities.adobe.com/t5/xml-documentation-discussions/use-aem-metadata-in-dita-ot-pdf-output/td-p/411880).

1.  From the **Properties** dropdown, select the required custom and default properties. For example, select `author`, `dc:title`, and `dc:description`. These are the standard `metadata/properties` that gets created once we create a file. The selected properties are listed below the dropbox.

    ![](images/selected-metadata-properties.png){width="300" align="left"}

1.  Select **Done** on the top left to save the changes.
1.  Generate the output.

The selected metadata properties will be passed to the output generated using DITA-OT.



**Parent topic:**[Output generation](generate-output.md)
