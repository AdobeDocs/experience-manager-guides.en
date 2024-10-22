---
title: Add custom fonts to your DITA PDF
description: Achieve custom font integration to reinforce brand identity and visual consistency across all your content in Native DITA PDFs. 
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
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

- ### Can I use Adobe Fonts?

> Yes, Go to fonts.adobe.com and click "Add to web project."
> 
> Copy import code like `" @import url("https://use.typekit.net/xxxx.css")`;
>
> Paste in your content CSS and do desired changes in your CSS file.

![Use adobe font in DITA PDF](../assets/publishing/custom-font4.png)


- ### My font is not showing in PDF

> Double check font name spelling (most common mistake)
>
> Make sure you are embedding font if fonts are not available on the system where PDF is opened

- ## For any other queries contact your respective CSMs


## Other Resources:

- [How to include DITA Bookmap's TOC in PDF](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [How to include TOC in PDF publishing](./how-to-include-bookmap-toc-in-pdf-publishing.md)
- [Expert-Session Video on Native PDF](../../expert-sessions/native-pdf-publishing-eamples-part1-june2023.md)