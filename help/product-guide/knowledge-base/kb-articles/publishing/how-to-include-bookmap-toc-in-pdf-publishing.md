---
title: TOC (Table of Contents) publishing using NativePDF
description: Publishing TOC and other booklist for your dita bookmap using NativePDF
feature: Native PDF Output
author: Pulkit Nagpal(punagpal)
role: User, Admin
exl-id: c551f0a8-f973-4c5a-bd34-f52890a91342
TQID: https://experienceleague.adobe.com/GyB4TpCF64rEGNgHVPKq4fUCBQsJjqh4jWA0CJC4A-0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
---
# Generate Bookmap's TOC in PDF publishing 

## Set-up your Bookmap

Include the `<toc>`  element:
Within your bookmap's `<frontmatter>`element, locate the `<booklists>` element.  Nest a `<toc>` element inside `<booklists>` like this:

```

<frontmatter>
  <booklists>
    <toc/>  <figurelist/>
    <tablelist/>
  </booklists>
</frontmatter>

```

DITA specification allows placing the TOC and booklists  within the `<backmatter>` section as well.


```

<backmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <indexlist/>
    </booklists>
  </backmatter>

```

Sample structure of bookmap with TOC , figure-list and table-list in frontmatter and index-list in backmatter. 

```

<bookmap>
  <title>My Bookmap Title </title>
  <frontmatter>
    <booklists>
      <toc/>
      <figurelist/>
      <tablelist/>
    </booklists>
  </frontmatter>

  <chapter href="chapter1.ditamap">
  <chapter href="chapter2.ditamap">
  </chapter>

  <backmatter>
    <booklists>
      <indexlist/>
    </booklists>
  </backmatter>
</bookmap>

```

The TOC and booklists are automatically generated based on the structure defined in your bookmap.

Once your bookmap is set up, use  Native PDF to generate the PDF output. It processes the bookmap structure and references, including the TOC and booklists.

## TOC design and its order in PDF

Native PDF functionality provides a convenient method for tailoring the layout and design of your table of contents.

You can control design via seprate page-layout for TOC and styles via layout.css. 

TOC and other Booklists order in PDF are based on bookmap's structure only.

![toc](../assets/publishing/toc.png)


## FAQ

### How to Include a Ditamap's TOC in a PDF

Ditamaps themselves don't directly have  a table of contents (TOC) like a bookmap does. However, ditamaps play a crucial role in defining the structure for your content and indirectly contribute to the TOC generation process.

If you are publishing Ditamap, then Native PDF gives functionality to generate TOC and booklist automatically , You can enable/disable generation of TOC at ditamap from Native PDF settings.

![Enable Disable TOC](../assets/publishing/pageorder.png)

## Additional Resources :

- [Native PDF design page layout documentation](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/install-guide/on-prem-ig/output-gen-config/config-native-pdf-publish/design-page-layout)
- [Native PDF essentials pre-recorded Expert session](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/expert-session/native-pdf-publishing-essentials-feb23)

<br>
<br>

 Post on the AEM Guides Community [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) for any queries.

 

