---
title: PDF
description: Generate and configure PDF output for FrameMaker documents in AEM Guides.
exl-id: df3d3cd8-2aa1-4d82-8756-c3f5555cb904
feature: Publishing FrameMaker Documents
role: User
TQID: https://experienceleague.adobe.com/O6dJF9YPsK7quGU1k6QDzxqGcxSD9RC1Rgrw3GxhkXo
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: bf79f6d3-0ad0-4d82-99e4-42ce98324d60
    internal-label: Publishing FrameMaker documents
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# PDF {#id205BB0T20RH}

The following options are available for the PDF Output:

>[!NOTE]
>
> To open output presets for PDF, select a FrameMaker \(`.fm` or `.book`\) file, then select the Output Presets, and choose the PDF Output option.

|PDF options|Description|
|-----------|-----------|
|Output Type|The type of output you want to generate. To generate PDF output, choose the PDF option.|
|Setting Name|Give a descriptive name for the PDF output settings you are creating. For example, you can specify *Internal customers output* or *end-users output*.|
|**Job Settings**||
|Options|Choose the PDF preset that you want to use for generating PDF output.|
|Generate Tagged PDF|Select this option to generate tagged PDFs that will contain information on document's content and structure. This information is used by the on-screen readers.|
|Generate PDF for Each File in Book|If you are generating output for a book file, select this option to generate a separate PDF for each file in the book.|
|Generate PDF for review Only|Select this option to generate PDF with commenting feature enabled.|
|Create Named Destination for all Elements and Paragraphs|Select this option to create named destinations based on elements and paragraphs.|
|**Display Settings**||
|Open Document on Page|Specify the page number that should be displayed on opening the PDF.|
|Initial Zoom Level|Choose the document zoom level.|
|Registration Mark|To print a document with crop marks and registration marks, choose an option from the Registration Marks drop-down list.|
|Page Width and Page Height|Specify the width and height of the page.|
|Page Range|Choose whether you want to publish all pages in the book or a range of pages. If you choose Range, then you must specify the From and To page range.|
|Convert CYMK to RGB|Select this option to convert CYMK colors to RGB in the generated PDF.|
|Generate PDF Bookmarks|Create accessible PDF that contains bookmarks.|
|Destination Path|The path within your AEM repository where the PDF output is stored.|
|Run Post Generation Workflow|When you choose this option, a new Post Generation Workflow drop-down list is displayed containing all workflows configured in AEM. You must select a workflow that you want to execute after completion of the output generation workflow.|

**Parent topic:**[Generate output of FrameMaker documents](fm-output-generatation.md)
