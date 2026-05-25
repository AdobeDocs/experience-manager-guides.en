---
title: Auto-generate element IDs
description: Learn how to Auto-generate element IDs
exl-id: a651db7f-228e-4de5-b569-3f1b4f86c418
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/xnUjt33qyeXgxwIH3L2t08FShHaicDSVVvXQQNGytI4
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Auto-generate element IDs {#id20CIL40016I}

AEM Guides generates a document ID for any new document that you create. For example, when you create a DITA map, an ID like `map.ditamap_random_digits` is assigned to the map's ID. You can also define elements on which an ID is automatically generated and assigned.

AEM Guides provides easy configuration settings wherein you need to define the elements on which an ID is auto-generated and a pattern for the ID. By default, some elements like `section`, `table`, `ul`, `ol`, are configured for auto-generation of ID. You can add other elements to this list so that whenever these elements are inserted in a document, AEM Guides generates and assigns an ID based on the given pattern

Use the instructions given in [Configuration overrides](download-install-additional-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to configure auto-generated element IDs:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`xmleditor.classes`|Specify a comma separated list of elements. <br> **Default value**: `"topic, section, table, simpletable, fig, image, ul, ol"`|

To configure a pattern for auto-generated ID create a configuration file with the following properties:

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.xmleditor.config.XmlEditorConfig`|`xmleditor.pattern`|The default value for this field is set to `${elementName}_${id}`. The `${elementName}` value is replaced with the name of the element. The `${id}` variable generates sequential number for the element. For example, if you assign the paragraph element to have auto-generated IDs, then the first paragraph in the topic or document will get an ID like p\_1, the next paragraph will get p\_2, and so on. However, in a different document, the ID generation process restarts. This means that in a different document, IDs like p\_1 and p\_2 can be assigned to paragraph elements. **Default value**: ``${elementName}_${id}``|

**Parent topic:**[Customize Web Editor](conf-web-editor.md)
