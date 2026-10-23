---
title: Merge branches of a DITA map | Experience Manager Guides
description: Learn how to merge changes from a branch of a DITA map into the main branch and resolve merge conflicts in Experience Manager Guides.
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
# Merge branches of a DITA map into main

In Experience Manager Guides, you can merge changes from a branch of a DITA map into the `main` branch. Merging allows you to incorporate completed documentation updates into `main` without manually updating the corresponding content.

For example, consider a DITA map named `install-the-lift.ditamap` with a branch named `Release 2`. Authors can update the installation instructions in this branch while the existing documentation remains unchanged in `main`.

Once the updates are ready, authors can merge the changes from `Release 2` into `main`.

## Understand branch merging

Merging brings changes from a selected branch of a DITA map into the `main` branch.

- **Source branch:** The branch containing the changes you want to merge.
- **Main branch:** The default branch (`main`) into which the changes are merged.

If the same content has been modified in both branches, merge conflicts may occur and require resolution.

## Merge a branch

You can merge changes from a selected branch of a DITA map into `main`.

To merge a branch, perform the following steps:

1. Open the required DITA map in the Map console.
2. Navigate to the **Branches** tab.
3. Locate the branch containing the changes you want to merge.
4. Open the branch's **Options** menu and select **Merge into main**.

    ![](./images/merge-into-main.png)

   The merge workflow is executed and a merge request is created once the workflow is completed.
  
    ![](./images/merge-request-created.png)

5. Select the merge request to review the changes and resolve any conflicts, if required.
6. Complete the merge.

   The changes are merged into the `main` branch.

## Resolve merge conflicts

A merge conflict occurs when the same content has been modified in both `main` and the branch being merged. You must resolve all conflicts before merging the changes into `main`.

When you open a merge request, the **Merge branch** view displays the following sections:

![](./images/merge-branch-view.png)

- **Conflicts:** Lists files that require conflict resolution.
- **Clean updates:** Lists files that can be merged without resolving conflicts.

For files with conflicts, a three-way merge view is displayed.

![](./images/merge-conflicts.png)

The three-way merge view contains the following panes:

- **Left pane (main):** Displays the content from the default branch (`main`).
- **Middle pane (Merged):** Displays the merged content, where you can accept changes from either branch or edit the content directly.
- **Right pane (selected branch):** Displays the content from the branch being merged into `main`.

The differences are highlighted in the left and right panes based on the content in the **Merged** pane:

- **Red (-):** Indicates content present in the **Merged** pane that differs from the content in the corresponding left or right pane.
- **Green (+):** Indicates content present in the left or right pane that is not included in the **Merged** pane.

Initially, the **Merged** pane contains the same content as `main`, so differences are highlighted in the right pane. As you accept changes into the **Merged** pane, differences may also appear in the left pane.

To resolve merge conflicts, perform the following steps:

1. In the **Conflicts** section, select the file containing conflicts.

2. Review the highlighted differences in the three-way merge view.

3. To resolve individual changes, use the merge controls:

   - **Replace:** Keep the checkbox selected and select the corresponding arrow to replace the existing content in the **Merged** pane with the selected change.
   - **Keep both:** Clear the checkbox and select the arrow to add the selected content to the **Merged** pane without removing the existing content.
   - To retain content from `main`, select the corresponding arrow in the left pane.

   The checkbox applies only to the selected change, not the entire file. It appears for applicable changes in the right pane and is selected by default.

   >[!TIP]
   >
   > Hover over an arrow to see how accepting the selected change will affect the **Merged** pane.

4. Alternatively, to accept all content from either branch, select one of the following options:

   - **Accept main:** Replaces the content in the **Merged** pane with the version from `main`.
   - **Accept [branch name]:** Replaces the content in the **Merged** pane with the version from the selected branch.

5. Review the content in the **Merged** pane and select **Mark resolved**.

   The file is marked as resolved.

6. Repeat the steps for all files listed under **Conflicts**.

   Once all conflicts are resolved, the **Merge all** option becomes available.

7. Select **Merge all** to complete the merge.

   The resolved changes are merged into `main`.

>[!NOTE]
>
> The **Merge all** option remains disabled until all conflicts are resolved.

## Manage a merge request

You can manage existing merge requests using the context menu.

To manage a merge request, open its context menu and select one of the following options:

- **Preview:** Preview the merge request.
- **View log:** View the log associated with the merge request.
- **Delete:** Delete the merge request.
- **View report:** View the merge report after the branch has been merged into `main`.