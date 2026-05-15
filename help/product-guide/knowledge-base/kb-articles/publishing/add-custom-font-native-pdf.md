---
title: Add custom fonts to your DITA PDF
description: Achieve custom font integration to reinforce brand identity and visual consistency across all your content in Native DITA PDFs.
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: 151e3b1c-6340-4ff2-84d4-246bc4b68065
TQID: https://experienceleague.adobe.com/xqr9eYA2XTcyXL8X4aS-Wu2-FmU8-aCWDpb-L2BBFqI
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
    internal-label: Native PDF publishing
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Add custom Fonts to your DITA Native PDF

## This article covers: 

Adding the custom font to reinforce brand identity and visual consistency across all your content.

This process involves 3 steps: 

- [Upload the custom font ](#step-1--upload-the-custom-font-to-the-resource-folder-of-your-template)
- [Make necessary changes in the PDF templates's stylesheet](#step-2--make-necessary-changes-in-pdf-templatess-stylesheet)

- [Embed used fonts (Optional)](#step-3-optional--embed-used-font-in-pdf)

## Step 1 : Upload the custom font to the resource folder of your template 

![Custom font upload and import ](../assets/publishing/custom-font1.png)

## Step 2 : Make necessary changes in PDF templates's stylesheet

![Font face in PDF's template's stylesheet ](../assets/publishing/custom-font2.png)

## Step 3 (Optional) : Embed used font in PDF

![Custom font embedding into DITA PDF  ](../assets/publishing/custom-font3.png)

## FAQ

### Can I use Adobe Fonts?

> Yes, Go to fonts.adobe.com and click "Add to web project."
> 
> Copy import code like `" @import url("https://use.typekit.net/xxxx.css")`;
>
> Paste in your content CSS and do desired changes in your CSS file.

![Use adobe font in DITA PDF](../assets/publishing/custom-font4.png)


### My font is not showing in PDF

> Double check font name spelling (most common mistake)
>
> Make sure you are embedding font if fonts are not available on the system where PDF is opened

## For any other queries contact your respective CSMs


## Other Resources:

- [How to include DITA Bookmap's TOC in PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [How to include TOC in PDF publishing](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Expert-Session Video on Native PDF](../../expert-sessions/native-pdf-publishing-eamples-part1-june2023.md)
