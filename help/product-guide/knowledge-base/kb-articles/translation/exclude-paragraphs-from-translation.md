---
title: Exclude paragraphs within a topic from translation
description: How to exclude paragraphs within a topic from translation
feature: Translation
role: User
exl-id: 21e41bb4-52f3-4352-92d9-4a60f636de99
TQID: https://experienceleague.adobe.com/IAY5PLpWlHEpMygjmHI-BqS75-VqAU5x1o9mdiu4Aac
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
# How to exclude paragraphs within a topic from translation

Easiest way is to make use of translation=no attribute.

+ Authors can insert the additional attribute as **translation=no** on the paragraphs that they do not want to translate. The translation vendor needs to be informed and they can do configuration at their end to ignore the text with this attribute.
+ The OOTB machine translation (with trial Microsoft Translation connector) exhibits the same behavior.
+ Testing with Microsoft Translation : if you define **translate=no** attribute at paragraph level then it doesn’t translate the complete paragraph. This attribute can be defined at any element and the content inside that element will not be translated.


Here are a few screenshots that explains this further: 

**Source Content**

![Source Content](assets/source-content.jpg)

**Translated Content in Spanish**

![Translated Content in Spanish](assets/trans-content.jpg)
