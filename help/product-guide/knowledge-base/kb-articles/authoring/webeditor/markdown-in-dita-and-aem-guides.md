---
title: Use Markdown in DITA AEM Guides
description: Migrate and use markdown in DITA AEM Guides
author: Pulkit Nagpal(punagpal)
exl-id: a94c0129-df40-4b61-ac60-679b2ffe7e86
TQID: https://experienceleague.adobe.com/z41KjrBkAeDaH-iKXOFLH44qOQElziip1FqcRhnKaUI
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Use Markdown in AEM Guides

## Available Options

There are 2 options for using markdown files in AEM Guides :

- Option 1 : Import existing markdown in AEM Guides and use them directly inside ditamap to publish

- Option 2 : Convert existing markdown files into DITA 

Lets talk about each options :

### Option 1: Import existing markdown in AEM Guides and use them directly inside ditamap to publish 

It has Simpler setup and faster implementation. But, Limited functionality utilization of AEM Guides feature like content re-usability.

User need to add attribute `format="markdown" ` or `format="mdita"` so that publishing engines understands the type of file and publish accordingly. 

Sample file : [Markdown Ditamap](https://acrobat.adobe.com/id/urn:aaid:sc:AP:da31137e-be84-44fb-8974-d038eeff0283)

![screenshot for reference](../../assets/authoring/markdown_map.png)


#### Publish to PDF and Web output 

AEM Guides gives both Web (Html5/AEM Site) and PDF (Native-PDF/DITA-OT) option to publish ditamap with Markdown content 

### Option 2 : Convert Markdown to DITA format

Full utilization of AEM Guides functionality which content re-usability, conditional processing translation, baseline etc. But, It would need upfront efforts to convert `.md` to `.dita` format.

Markdown to DITA can be converted using external tools like Adobe FrameMaker and DITA-OT.


For Adobe FrameMaker, refer : [Import markdown](https://www.adobe.com/in/products/framemaker/features.html#import-markdown)

For DITA-OT, refer : [Markdown as Input](https://www.dita-ot.org/dev/topics/markdown-input.html)

Sample file converted using Adobe FrameMaker : [Markdown to DITA sample](https://acrobat.adobe.com/id/urn:aaid:sc:AP:874881f3-ba43-410c-abc6-2df899536d79)

#### Publish to PDF and Web output 

Once markdown files are converted into DITA, User can seamlessly publish output to any formats available in AEM Guides.

Available formats in AEM Guides : [Output formats](../../../../user-guide/generate-output-understand-presets.md)
