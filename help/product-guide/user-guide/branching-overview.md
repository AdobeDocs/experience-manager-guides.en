---
title: Branching in AEM Guides | Adobe Experience Manager Guides`
description: Learn how to create and manage branches of a DITA map in AEM Guides to support parallel authoring, independent publishing, and merging of documentation changes.
TQID: https://experienceleague.adobe.com/pg9zeEg8m3NeDbN-j945SqPbaMX0GgBmuquAsQcrjOM
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: ec4263d9-bf7c-44c7-b3f1-3e664861c8f2
    internal-label: Generative AI
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
    internal-label: Content reuse
---
# Overview

>[!NOTE]
>
> The branching and merging feature is introduced in the 2026.11.0 release of Experience Manager Guides as a Cloud Service and is disabled by default. To enable the feature for your environment, contact your Customer Success team.

Branching in Adobe Experience Manager Guides allows you to create and manage multiple branches out of the **main** branch for a DITA map to work on different documentation releases in parallel. Each branch allows authors to manage content changes independently, without affecting the corresponding content in other branches.

With branching, multiple teams can work simultaneously on different releases, features, or fixes associated with the same DITA map. You can merge changes from a branch into the default branch (`main`) when the updates are ready.

## How branching works

You can create a branch from the **main** or any existing branch of a DITA map. After creating a branch, you can switch to it and start editing the map and its content. You can also publish content from the selected branch or merge changes into `main` when ready.

For example, consider a DITA map named `install-the-lift.ditamap` that contains installation instructions for a product. Your documentation team can create two branches of this map from `main`:

- **Release 1:** Team A maintains existing installation instructions and addresses fixes.
- **Release 2:** Team B develops installation instructions for new features.

Both teams can work independently on their respective map branches without affecting each other's changes.

>[!NOTE]
>
>A branch is created based on a DITA map. You can also add and edit topics that are not referenced by the map within the selected branch. For more information, view [Open or edit topics outside the current map](./create-manage-branch.md#open-or-edit-topics-outside-the-current-map-context).

When you create a branch of a DITA map, Experience Manager Guides does not automatically copy its referenced topics into the new branch. Unchanged topics are read from the default branch (main). A topic is copied into the selected branch only when you modify its content

For example, A DITA map references 100 topics, and the repository contains 50 additional topics that are not referenced by the map. When you create a new branch (release-1.0), all 100 referenced topics automatically become part of release-1.0, even if none of them are edited. The 50 unreferenced topics do not automatically become part of the new branch. If you edit 10 of them, only those 10 become part of release-1.0. The remaining 40 unchanged topics continue to be used from the default branch (main).

>[!NOTE]
>
> Topic versioning continues to work with branching. You can create and manage versions of topics within a selected branch of a DITA map. Each branch maintains its own version history, independent of other branches.

## Key benefits

Working with a branch in Experience Manager Guides provides the following benefits:

- **Isolated editing:** Make changes within a selected map branch without affecting the corresponding content in other branches.
- **Parallel authoring:** Enable multiple teams to work simultaneously on different releases, features, or fixes within their respective map branches.
- **Independent publishing:** Publish documentation from individual map branches without waiting for changes in other branches to be completed.
- **Controlled merging:** Merge changes from a map branch into the default branch (`main`), with the ability to review and resolve conflicts.

## Branching vs. Baselines

>[!NOTE]
>
> Baselines and branching are mutually exclusive features. When branching is enabled, baseline functionality becomes unavailable. However, existing baselines remain intact and are not deleted. If branching is disabled later, the existing baselines become available for use again.

A **baseline** identifies a specific combination of topic versions for a DITA map, allowing you to generate output using those selected versions.

A **branch** provides a separate editing environment for a DITA map and its content, allowing authors to make changes without affecting other branches of the same map.

| Baselines | Branching |
|---|---|
| Select specific versions of topics in a DITA map. | Create separate branches of a DITA map to manage changes independently. |
| Used to publish specific combinations of topic versions. | Used to develop and publish different releases in parallel. |
| Do not provide isolated editing contexts. | Support isolated editing and merging. |

## Upcoming functionalities

The following functionalities are currently supported only in the default branch (`main`) and are planned to be supported in other branches of a DITA map in future releases of Experience Manager Guides:

- Search
- Find and replace
- Review workflows

