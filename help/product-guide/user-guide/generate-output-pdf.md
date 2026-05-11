---
title: PDF preset types
description: Learn about the types of PDF preset you can create using Adobe Experience Manager Guides.
exl-id: f12c91fd-3f95-478e-a9cd-68d037206ee8
feature: Publishing
role: User
TQID: https://experienceleague.adobe.com/RN5CYho8TpklBivMgK6ifb--eTwlBQgD-1jNU8HvF7E
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3
    internal-label: FrameMaker Publishing Server
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
    internal-label: Native PDF publishing
  - id: f9dbea21-a714-40dd-bc90-080d8046c93f
    internal-label: Map console
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# PDF output preset overview {#id205BE600HAH}

With Experience Manager Guides, you can create PDF presets to generate PDFs of individual topics or an entire map file. You can publish your content in a PDF format using one of the three methods below: 

**DITA-OT**  

Use this method to generate a PDF output for a map from the Map console or Map dashboard. You can set publishing properties before generating the PDF by creating an output preset for the map that is open in the Map console or Map dashboard. 

For more information on creating a PDF output preset using the DITA-OT method, view [Create DITA-OT PDF output preset](./generate-output-pdf-dita-ot.md)

**FrameMaker Publishing Server (FMPS)**

>[!NOTE]
>
> FMPS publishing option is only available in Map dashboard.

Use this method to generate a PDF output from not only the DITA content, but also FrameMaker documents (.book and .fm) available in your AEM repository. The PDF can be created by configuring an output preset and published using FrameMaker Publishing Server (FMPS). You can design and configure the look-and-feel of your output for PDF and other formats and store the same in a setting file (.sts). This setting file is then used by FMPS to generate output for a DITA map or .book file. To create or edit an output preset, view [Understanding the output presets](../user-guide/generate-output-understand-presets.md).

For more information on configuring FMPS, view [Generate output from FrameMaker documents](../user-guide/fm-output-generatation.md). 

**Native PDF** 

Use this method to generate a feature-rich PDF output based on W3C CSS3 and CSS paged media standards. With Native PDF publishing, you can use templates to set the layout and styling for your content and apply various settings to fine-tune your PDF. In addition, you can modify and create your own templates with the template editor. 

 For more information on Native PDF preset creation, view [Create Native PDF output preset](../web-editor/native-pdf-web-editor.md).





**Parent topic:**[Understanding the output presets](generate-output-understand-presets.md)
