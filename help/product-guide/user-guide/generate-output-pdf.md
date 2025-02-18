---
title: PDF preset types
description: Learn about the types of PDF preset you can create using AEM Guides. 
exl-id: f12c91fd-3f95-478e-a9cd-68d037206ee8
feature: Publishing
role: User
---
# PDF preset overview {#id205BE600HAH}

With AEM Guides, you can create PDF presets to generate PDFs of individual topics or an entire map file. You can publish your content in a PDF format using one of the three methods below: 

**DITA-OT**  

Use this method to generate a PDF output for a map from the Map console or Map dashboard. You can set publishing properties before generating the PDF by creating an output preset for the map that is open in the Map console or Map dashboard. 

For more information on creating a PDF output preset using the DITA-OT method, view [Create DITA-OT PDF output preset](./generate-output-pdf-dita-ot.md)

**FrameMaker Publishing Server (FMPS)**

>[!NOTE]
>
> FMPS publishing is only available in Adobe Experience Manager Guides as a Cloud Service. You can create a PDF output preset using FMPS, only from the Map dashboard.

Use this method to generate a PDF output from not only the DITA content, but also FrameMaker documents (.book and .fm) available in your AEM repository. The PDF can be created by configuring an output preset and published using FrameMaker Publishing Server (FMPS). You can design and configure the look-and-feel of your output for PDF and other formats and store the same in a setting file (.sts). This setting file is then used by FMPS to generate output for a DITA map or .book file. To create or edit an output preset, see the  *Understanding the output presets* section in the [AEM Guides as a Cloud Service User Guide](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/cs-apr-22/XML-Documentation-for-Adobe-Experience-Manager_CS_User-Guide_EN.pdf).

For more information on configuring FMPS, see [Generate output from FrameMaker documents](https://help.adobe.com/en_US/xml-documentation-for-adobe-experience-manager/index.html#t=DXML-master-map%2Ffm-output-generatation.html). 

**Native PDF** 

Use this method to generate a feature-rich PDF output based on W3C CSS3 and CSS paged media standards. With Native PDF publishing, you can use templates to set the layout and styling for your content and apply various settings to fine-tune your PDF. In addition, you can modify and create your own templates with the template editor. 

 For more information on Native PDF preset creation, view [Create Native PDF output preset](../web-editor/native-pdf-web-editor.md).





**Parent topic:**[Understanding the output presets](generate-output-understand-presets.md)
