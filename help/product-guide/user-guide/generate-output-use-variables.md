---
title: Use variables for setting the Destination Path, Site path, Site Name, or File Name options
description: Learn how to use variables for setting the Destination Path, Site Name, or File Name options. Know out-of-the-box variables supported in AEM Guides.
exl-id: 3396c971-6332-45b5-b2ef-b07f0abf97f7
feature: Publishing
role: User
TQID: https://experienceleague.adobe.com/JiQKZ28KLI-TI5cqYdpKLyW79uOzlR2VV3zqZPFoVWc
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
---
# Use variables for setting the Destination Path, Site path, Site Name, or File Name options


While generating outputs in AEM Sites or PDFs, you can use variables to define the Destination Path, Site path, AEM Site Name, or PDF File Name options. You can use a single or a combination of variables to define theses options.

The following table lists the variables that are supported out of the box:

| Variable | Final Destination Path | Example |
| --- | --- | --- |
| `${map_filename}` | Uses the DITA map files name to create the destination path. | **DITA map file name**:<br>`AEMGuides.ditamap`<br><br>**Destination Path** configured as:<br>`/content/output/sites/${map_filename}`<br><br>**Final output location**:<br>`/content/output/sites/aemGuides/AEMGuides.html` |
| `${map_title}` | Uses the DITA map title to create the destination path. | **DITA map file name**:<br>`AEMGuides.ditamap`<br><br>**DITA map Title**:<br>`AEMGuides`<br><br>**Destination Path** configured as:<br>`/content/output/sites/${map_title}`<br><br>**Final output location**:<br>`/content/output/sites/AEMGuides/AEMGuides.html` |
| `${preset_name}` | Uses the output preset name to create the destination path. | **Output Preset Name**:<br>`AEM Guides PDF Output`<br><br>**DITA map file name**:<br>`SampleDita.ditamap`<br><br>**Destination Path** configured as:<br>`/content/output/sites/${preset_name}`<br><br>**Final output location**:<br>`/content/output/sites/AEM Guides PDF Output/SampleDita.html` |
| `${language_code}` | Uses the language code where the map file is located to create the destination path. | **DITA map file name**:<br>`SampleDita.ditamap`<br><br>**DITA map file path**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Destination Path** configured as:<br>`/content/output/sites/${language_code}`<br><br>**Final output location**:<br>`/content/output/sites/en/SampleDita.html` |
| `${map_parentpath}` | Uses the complete path of the map file to create the destination path.<br><br>**Note**:This variable cannot be used to specify the AEM Site Name or PDF File Name. | **DITA map file name**:<br>`SampleDita.ditamap`<br><br>**DITA map file path**:<br>`/content/dam/projects/AEM-Guides/en/user-guide`/<br><br>**Destination Path** configured as:<br>`/content/output/sites/${map_parentpath}`<br><br>**Final output location**:<br>`/content/output/sites/content/dam/projects/AEM-Guides/en/user-guide/SampleDita.html` |
| `${path_after_langfolder}` | Uses the path of the map file after the language folder to create the destination path.<br><br>**Note**: This variable cannot be used to specify the AEM Site Name or PDF File Name. | **DITA map file name**:<br>`SampleDita.ditamap`<br><br>**DITA map file path**:<br>`/content/dam/projects/AEM-Guides/en/user-guide/`<br><br>**Destination Path** configured as:<br>`/content/output/sites/${path\_after\_langfolder}`<br><br>**Final output location**:<br>`/content/output/sites/user-guide/SampleDita.html` |
|`${system_date}` |Uses the current server date to create the destination path.| **DITA map file name**: <br> `SampleDita.ditamap` <br><br> **DITA map file path:** <br> `/content/dam/projects/AEM-Guides/en/user-guide/` <br><br> **Destination Path** configured as: <br> `/content/output/sites/${system_date}` <br> <br> **Final output location:** <br> /`content/output/sites/08252023/SampleDita.html`|
|`${system_time}` |Uses the current server time to create the destination path.|**DITA map file name:** <br>`SampleDita.ditamap` <br> <br> **DITA map file path:** <br>`/content/dam/projects/AEM-Guides/en/user-guide/` <br><Br>**Destination Path** configured as: <br> `/content/output/sites/${system_time}`<br><br>**Final output location:**<br>`/content/output/sites/055612/SampleDita.html`|
 
In addition, you can also use the metadata defined for the DITA map or bookmap file as variables. The metadata can be found under the `/jcr:content/metadata` node of the DITA map or bookmap file. For example, one of the metadata properties define in the `/jcr:content/metadata` node is `dc:title`. You can specify `${dc:title}` and the title value is used in the final output.
**Parent topic:**[Output generation](generate-output.md)
