---
title: Manage tags for DITA files in AEM Guides
description: Brief article to tell on managing cq:tags in AEM Guides
exl-id: 2d805c26-df9b-405a-81ca-7aa84c6f86c8
feature: Metadata Management
author: Pulkit Nagpal(punagpal)
role: User, Admin
TQID: https://experienceleague.adobe.com/u3MZ3fUZIp-FYQE895I7kDRkF3l96KhwYMRMJ-rG2RE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
    internal-label: Reports
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
---
# How to Add , Remove and Manage  tags  in your  DITA  content 

Tags come useful to categorize your content. If content is properly tagged, then it can help you in locating  exact topics in your ditamap  and end user finds the appropriate content more quickly on your published output 

> **_NOTE:_**  Following article is for AEM Guides Build 4.2 (on-prem) /Feb 2023 (cloud version ) or higher versions


## Create Tags 

Tagging is native AEM feature and your AEM  administrator can help in initial creation and configuration of these tags.


## Add, Remove, and Manage tags in your DITA content 

**Any tags created in AEM cq: tags can be added, removed, and managed for your DITA contents**

There are various ways to add tags into your DITA content but this article will concentrate to AEM Guides web-editor UI.

### Steps:

1. Go to repository view in Guides UI
2. Double-click ditamap and open in map view
3. Go to Manage Tab
4. In Manage tab , Go to Metadata option
5. All your direct and indirect ditamap files list loads here. 
6. Select one or more files and click the 'manage' icon. Here you can add tags to selected files.
You can also remove existing tags which are common in selected files.

<img title="Manage tags in AEM Guides " alt="Manage Tags in DITA " src="ManageTags.jpg">

## Troubleshooting and FAQ

### List in manage->metadata is empty or incomplete 

`If list is empty or  incomplete then you may need to run the indexing on your ditamap, You can refer` [Upgrade instructions(Index your content)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/install-guide/on-prem-ig/download-install-upgrade-aemg/upgrade-xml-documentation.html?lang=en#steps-to-index-the-existing-content-to-use-the-new-find-and-replace%3A)

### Custom metadata is not coming up in list 

`Only Tags present in cq:tags can be managed from here and custom metadata is not supported`




## Other helpful resources

- [Bulk Tagging using Map Dashboard(Assets UI)](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/manaege-metadata/map-editor-bulk-tagging.html?lang=en)
- [Ditamap Reports in web-editor](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/user-guide/reports-aem-guide/reports-web-editor.html?lang=en)
- [Tagging in AEM](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/configuring/tagging.html?lang=en)


**Contact your respective CSM for any other queries**
