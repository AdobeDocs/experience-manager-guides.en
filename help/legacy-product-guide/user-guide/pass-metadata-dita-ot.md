---
title: Pass on the metadata to the output using DITA-OT
description: Learn how to pass on the metadata to the output using DITA-OT publishing in AEM Guides.
feature: Publishing, Metadata Management
role: User
hide: true
exl-id: 55d70c6d-feb0-43f7-9f18-6d1ccdd1e728
TQID: https://experienceleague.adobe.com/I-DddG1Wq9cXsF1IZt6B0XFzbR1gbtvtKPoO-g2nLM0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
---
# Pass on the metadata to the output using DITA-OT {#id21BJ00QD0XA}

Metadata is additional information about the output. In AEM Guides you can pass on the existing metadata or create custom metadata tags. You can pass on metadata to AEM, PDF, HTML5, EPUB, and Custom format outputs using DITA-OT publishing.

Perform the following steps to pass on the metadata to the output using DITA-OT publishing:

1.  In the **Assets UI**, navigate to and click on the DITA map file for which you want to pass the metadata to the DITA-OT.
1.  Select and edit an output preset to which you want to pass the metadata fields. For example, select PDF output preset.
1.  Select **DITA-OT** under Generate <output\> Using option in the selected output preset.

    ![](images/custom-meta-data-output-preset.png){width="800"}

1.  From the Properties drop down select the metadata that you want to pass to DITA-OT publishing.

    Properties dropdown lists both the custom and the default properties. For example, in the above screenshot author is the custom property while `dc:description`, `dc:language`, `dc:title`, and `docstate` are the default properties.

    >[!NOTE]
    >
    > These properties are picked from the metadataList file available at the following location:`/libs/fmdita/config/metadataList`. By default, there are four properties listed in this file- `dc:description`, `dc:language`, `dc:title`, and `docstate`.

    This file can be overlaid at: `/apps/fmdita/config/metadataList`.

    To pass a custom property for which you have already defined the values, see [Use AEM Metadata in DITA-OT PDF output](https://experienceleaguecommunities.adobe.com/t5/xml-documentation-discussions/use-aem-metadata-in-dita-ot-pdf-output/td-p/411880).

1.  From the **Properties** dropdown, select the required custom and default properties. For example, select `author`, `dc:title`, and `dc:description`. These are the standard `metadata/properties` that gets created once we create a file. The selected properties are listed below the dropbox.

    ![](images/selected-metadata-properties.png){width="300"}

1.  Click **Done** on the top left to save the changes.
1.  Generate the output.

The selected metadata properties will be passed to the output generated using DITA-OT.

**Parent topic:**[Output generation](generate-output.md)
