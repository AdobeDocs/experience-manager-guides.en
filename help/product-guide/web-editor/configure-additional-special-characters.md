---
title: Configure additional special characters in Editor toolbar
description: Learn how to configure additional special characters in the editor of AEM Guides.
feature: Web Editor
role: User
exl-id: 0fbc05a5-a6b0-4f6b-bbc4-8fca03581d90
TQID: https://experienceleague.adobe.com/7InE1R4lpkq7cQ6xptqVIyjG4b-2i9klObtxf2y7Cw8
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# How to configure additional special characters in Editor toolbar for On-Premise

There is a shortcut option in the web-editor toolbar to let author insert the special characters already. 
The same can be seen in screenshot below:

![Special Characters](assets/special-chars.png)


These list of characters is configurable here. If you need to add more characters to this then follow the below steps:

+ Log into AEM and open the CRXDE Lite mode.

+ Create symbols.json file at the following location: '/apps/fmdita/xmleditor/' (You can copy the default from - '/libs/fmdita/clientlibs/clientlibs/xmleditor/symbols.json' location)

+ Add the special character definition in the symbols.json file as:

``` 

{
      "label": "Logical Symbols",
      "items": [
        {
          "name": "≥",
          "title": "Greater-Than or Equal To"
        },
        {
          "name": "≤",
          "title": "Smaller-Than or Equal To"
        }
      ]
}

``` 

The structure of the symbols.json file is explained below:

+ "label": "Logical Symbols": This specifies the category for the special characters. In the snippet, a category with the name "Logical Symbol" is defined.

+ "items": This defines the collection of special characters in the category.

+ "name": "≥", "title": "Greater-Than or Equal To": This is the definition of the special character. It starts off with the "name" label, which must not be changed. The name is followed by the special character. The "title" is the name or title of the special character that appears as the tooltip for that special character.

You can define multiple definitions of special characters within a category.

This will add another category in special characters dialog:

![Special Symbol Category](assets/special-char-category.png)

![Insert Special Character](assets/insert-special-char.png)

>[!MORELIKETHIS]
>
>+ [Installation and Configuration Guide](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/3-6/XML-Documentation-for-Adobe-Experience-Manager_Installation-Configuration-Guide_EN.pdf)
