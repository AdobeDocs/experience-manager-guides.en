---
title: DITA content reuse in AEM Guides
description: This brief article tells how AEM Guides and DITA help you save time and effort when using content reusability
role: User, Admin
author: Pulkit Nagpal(punagpal)
exl-id: 1522ebf5-2aea-4d8f-ade7-367227b31dd9
TQID: https://experienceleague.adobe.com/zCktDt9h2K-lCluedb39M5cc40j34GATjIvm04kU-nc
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
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
    internal-label: Content reuse
---
# Content reusability in AEM Guides 

Adobe AEM Guides leverage DITA's strengths to provide a user-friendly interface for content reuse.

This article will discuss:

1. [Reusability using topic reference (`topicrefs`)](#reusability-using-topic-referencestopicref)
2. [Reusability using content reference (`conref` and `conkeyref`)](#reusability-using-content-reference-conref--conkeyref)
3. [Bonus tip to reuse content with drag and drop in AEM Guides](#reuse-content-with-a-single-click-in-aem-guides)

## Reusability using topic references(topicref)



Let's suppose you are a Manufacturing company and have generic topics for safety precautions or troubleshooting techniques.

These can be referenced and adapted in specific user manuals for each machine model, reducing redundancy and ensuring core safety information remains consistent.

```
<map id="user_manual_model 100" title="ABC Model 100 User Manual ">


<topicref href="Safety_Information.dita" format="dita">
</topicref>
.
.
.
.
.
</map>

```


Similarly for Model 200

```
<map id="user_manual_model 200" title="ABC Model 200 User Manual ">

<topicref href="Safety_Information.dita" format="dita">
</topicref>
.
.
.
.
.
  
</map>

```

## Reusability using content reference (conref & conkeyref)

The content reference (conref) attribute allows you to link to other parts of your content. This promotes reusability and reduces redundancy.

For example:

Let's suppose you are a financial enterprise and have a generic topic for KYC which contains KYC procedures for individuals, corporate, and so forth.

You want to reuse individual KYC fragment for your "Saving account" and "Demat account" topics.

```
<section id="kyc_requirements_saving_account">
  <title>Know Your Customer (KYC) Requirements</title>
  <p>To comply with regulations and ensure customer identification, all individual applicants for savings  accounts must fulfill the KYC requirements as outlined below</p>
  <p conref=kyc_procedures.dita#individual_kyc></p>
</section>

```

Here `conref=kyc_procedures.dita#indvidual_kyc` kyc_procedures.dita is the file identifier and #individual_kyc is the fragment identifier.

Kyc_procedure.dita continues to be the only single source of information. If regulatory changes require updates to the KYC process, update the topic path with the new one. The changes will automatically reflect in all topics that reference it.

Using AEM Guides, Its two clicks

Step 1: Click Insert Reusable content 
![toolbar](../../assets/publishing/content-reusability_image1.png)

<br>

Step 2: Select your file and fragment which needs to be reused.
![conref](../../assets/publishing/content-reusability_image2.png)

Similar to 'conref,' you can use 'conkeyref' as well where instead of giving a content path, you refer to content via key

Code example :

```
<section conkeyref="kyc_procedure/individual_kyc_procedure" id="individual_kyc_procedure"></section>

```

The key definition looks like this :

```
<map id="ABC_manual">
  <title>ABC_Manual</title>
  <topicref href="kyc_procedure_2020.dita" keys="kyc_procedure" processing-role="resource-only" type="concept">
  </topicref>
  <topicref href="savings_account.dita" type="concept">
  </topicref>
</map>
```

Key - 'Kyc_procedure' continues to be the single source of information. If there are any changes to the KYC process as required by regulations, you simply need to update one topic path with a new topic path, and those changes are automatically reflected in all topics that are referring to it. 

```
<map id="ABC_manual">
  <title>ABC_Manual</title>
  <topicref href="kyc_procedure_2024.dita" keys="kyc_procedure" processing-role="resource-only" type="concept">
  </topicref>
  <topicref href="savings_account.dita" type="concept">
  </topicref>
</map>

```

Here the topic path is changed from "kyc_procedure_2020.dita" to "kyc_procedure_2024.dita" due to recent regulation changes.

Using AEM Guides, Its two clicks

Step 1: Click Insert Reusable content 
![toolbar](../../assets/publishing/content-reusability_image1.png)

Step 2: Select your root map (optional), key, and fragment that needs to be reused.
![conkeyref](../../assets/publishing/content-reusability_image3.png)

Here the root map was auto-selected since it was already open in the map view.


## Reuse content with a single click in AEM Guides 

AEM Guides offers a "Reusable contents" capability to add content references at a single click.

Step 1: Add a generic topic to Reusable contents 

![Add Reusable content](../../assets/publishing/content-reusability_image4.png)

Step 2: Once added, Drag, and drop the fragment that you want to reuse in any of your destination topics.

![Add Reusable content gif](../../assets/publishing/content-reusability_image5.gif)

    

## FAQ

### All content is not showing up after selection of file/key in the Reuse content dialog

Assign IDs to fragments (Dita elements) that you would like to reuse in other topics 

## Keys are not showing up in the Reuse content dialog

Make sure you have opened the root map/parent map in map-view, which has a key definition or add the root map path manually in the same dialog.


<br>
<br>
<br>


Post on the AEM Guides Community [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) for any queries.
