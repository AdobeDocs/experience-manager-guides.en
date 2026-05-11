---
title: Other features in the map editors
description: Discover some common features in the Basic and Advanced Map Editors. Learn how to resolve key references in the Map editor.
feature: Authoring, Map Editor
role: User
hide: true
exl-id: d6e00884-e17c-499e-9568-0807a75051ad
TQID: https://experienceleague.adobe.com/tAzYI5Pxc6SkzgksjL3mFAQHY01YtejwTrU6vHW5vMc
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Other features in the map editors {#id1942D0T0HUI}

Some common features in the Basic and Advanced Map Editors are:

## Resolve key references {#id176GD01H05Z}

A DITA content key reference, or `conkeyref` is a mechanism for inserting a part of content from one topic into another. This mechanism uses key to locate the content to reuse rather than the direct content referencing mechanism. For more information about direct and indirect referencing in DITA, see *DITA addressing* in OASIS DITA Language Specification.

If the DITA topic has associated key references, then they need to be resolved before previewing, editing or reviewing a topic.

The key references are resolved on the basis of the root map set in the following order of priority:

1.  User Preferences
1.  Map View panel
1.  Folder Profile

The root map selected in the User Preferences takes the highest precedence to resolve key references followed by Map View panel and the Folder Profile root map. So, if no map is set in the User Preferences, then the map opened in the Map View panel is used. If no map is opened in the Map View panel then the map set in the Folder Profiles is used to resolve the key references.

The key references can be stored within a DITA map file or a separate DITA file. In AEM Guides, you can specify key references either at the project level or a session level. If a root map is already defined for the user session, then it is used for resolving the keys. Else, the default root map for that folder is used. In case a default root map is not configured, then the missing key references are highlighted to the user.

There are several ways to resolve key references in a DITA topic by defining the DITA map to be used at the following locations:

**Project properties** - You can define a root map for resolving key references while creating a Project in the Project Properties section.

This root map will be applicable for all assets \(folders and sub-folders\) associated with that project. For content that is referenced in multiple projects, an alphabetical list of projects is maintained and the default root map associated with the first project is used. You can also choose the DITA map to be used from the list for resolving key references.

**Topic preview** - In the topic preview mode, click on the Key Resolution icon in the toolbar and select the DITA file to be used for key references.

**Topic edit view** - Click on Key Resolution icon while editing a DITA topic and select the DITA file to use for resolving the key references.

**Parent topic:**[Work with the Map Editor](map-editor.md)
