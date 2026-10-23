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
> The branching feature is introduced in the 2026.11.0 release of Experience Manager Guides as a Cloud Service and is disabled by default. To enable the feature for your environment, contact your Customer Success team.

Branching in Adobe Experience Manager Guides allows you to create and manage multiple branches of a DITA map to work on different documentation releases in parallel. Each branch allows authors to manage content changes independently, without affecting the corresponding content in other branches.

With branching, multiple teams can work simultaneously on different releases, features, or fixes associated with the same DITA map. You can merge changes from a branch into its parent or main branch when the updates are ready.

## How branching works

You can create a branch from the **main** or any existing branch of a DITA map. After creating a branch, you can switch to it and start editing the map and its content. You can also publish content from the selected branch or merge changes into its parent branch when ready.

For example, consider a DITA map named `install-the-lift.ditamap` that contains installation instructions for a product. Your documentation team can create two branches of this map:

- **Release 1:** Team A maintains existing installation instructions and addresses fixes.
- **Release 2:** Team B develops installation instructions for new features.

Both teams can work independently on their respective map branches without affecting each other's changes.

>[!NOTE]
>
> Branching in Experience Manager Guides starts with a DITA map, but you can also add and edit topics that are not referenced by the map within the selected branch. For more information, view [Open or edit topics outside the current map](./create-manage-branch.md#open-or-edit-topics-outside-the-current-map).

When you create a branch, the topics referenced by the DITA map do not automatically become part of the new branch. Only the topics you edit become part of the selected branch, while unchanged topics continue to be used from the default branch (`main`).

For example, if a DITA map contains 100 topics and you edit only 10 topics in a new branch, only those 10 topics become part of the new branch. The remaining 90 topics continue to be used from `main`. This avoids unnecessary duplication of content across branches.

## Key benefits

Working with a branch in Experience Manager Guides provides the following benefits:

- **Isolated editing:** Make changes within a selected map branch without affecting the corresponding content in other branches.
- **Parallel authoring:** Enable multiple teams to work simultaneously on different releases, features, or fixes within their respective map branches.
- **Independent publishing:** Publish documentation from individual map branches without waiting for changes in other branches to be completed.
- **Controlled merging:** Merge changes from a map branch into its parent or main branch, with the ability to review and resolve conflicts.

## Branching vs. Baselines

>[!NOTE]
>
> You can use either baselines or branching in Experience Manager Guides based on your documentation requirements. When branching is enabled for an environment, baseline functionality is disabled and is no longer available in the user interface.

Both branching and baselines help manage documentation across versions in Experience Manager Guides, but they serve different purposes.

A **baseline** identifies a specific combination of topic versions for a DITA map, allowing you to generate output using those selected versions.

A **branch** allows authors to develop and manage content changes independently within a selected branch of a DITA map.

| Baselines | Branching |
|---|---|
| Select specific versions of topics in a DITA map. | Create separate branches of a DITA map to manage changes independently. |
| Used to publish specific combinations of topic versions. | Used to develop and publish different releases in parallel. |
| Do not provide isolated editing contexts. | Support isolated editing and merging. |

## Limitations

Branching in Experience Manager Guides currently does not support the following features:

- Search
- Find and replace
- Review workflows
- Translation workflows

