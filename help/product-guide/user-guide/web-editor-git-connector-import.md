---
title: Import content using Git Connector in Experience Manager Guides 
description: Learn how to import content from a connected Git repository into Experience Manager Guides using the Bulk importer, and manage imported content.
feature: Authoring, Features of Web Editor
role: User
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
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
  - id: d4f22c6d-7923-41e5-9da3-527ff8df4bc8
    internal-label: Document state
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
    internal-label: Web Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
---

# Import content using Git Connector

After your Administrator configures the [Git Connector in Experience Manager Guides](./web-editor-git-connector.md), you can use it from the Editor to import content from a Git repository.

## Prerequisites

Before you start using this feature, ensure that:

- Git Connector feature must be enabled for your environment. 
- (*If enabled*) Your Administrator has configured the Git Connector in your environment. For details, view [Create and configure Git Connector from the user interface](../install-conf-guide/conf-git-connector.md). 
- You have *Read* access to the Git repository that contains the content you want to import.
- You know which repository branch and source folder you want to import.
- You know the target folder in Experience Manager Guides where the imported content will be stored.

## Import content from the connected Git repository

Perform the following steps to import content from a Git repository:

1. In the Editor, open the left panel.
1. Select **Data sources**.

    The connected data sources are displayed. 

1. Select the **Git Connector** tile. 

1. Select the + icon and then select **Bulk importer**.  

    The **Bulk importer** dialog is displayed. 

    ![](images/git-bulk-importer-dialog.png)

1. In the **Bulk importer** dialog, provide a name for the import, select a subfolder from your configured Git repository, and select **Save & Fetch**.  The list of files available for import is displayed in the dialog. Review the list and validate the content before you continue.

    ![](images/git-bulk-importer-import-all.png)

1. After reviewing the files, select **Import all** to import the content into Experience Manager Guides. 

    >[!NOTE]
    >
    > You can enable **Auto Sync** to automatically synchronize and import content from your Git repository into Experience Manager Guides. If any errors are detected, Auto Sync is not triggered and the Author must manually import the content by selecting **Import all**. Once enabled, Auto Sync cannot be disabled for the importer.

After the content is imported, it is stored under the configured **Target AEM root path** when setting up the Git Connector.

## Manage Git-imported content

Once content is imported into Experience Manager Guides, you can use the available actions to manage the content and keep it synchronized with changes in the source repository.

![](images/git-connector-imported-content-options.png){width="600"}

- **Preview**: Preview imported content. If the source repository contains updates, review the differences and use the **Refetch** option to import the latest changes. If the differences require merging, view [Resolve Git Connector conflicts](#review-and-resolve-content-conflicts).
- **Delete**: Remove imported content that is no longer required.
- **Rename**: Rename imported content for easier identification.
- **View log**: View the import log to review details of the import operation.
- **View Report**: View and download the **Bulk import report**, which includes details such as:

    - total number of imported files
    - number of successful imports
    - number of failed imports 

    ![](images/git-connector-view-report.png){width="600"}

  You can also download the detailed report. If some files fail to import, use **Retry failed imports** to try importing them again.

## Review and resolve content conflicts

When you re-fetch content from a Git repository, differences in the content between the repository version and the corresponding content available in Experience Manager Guides are displayed as conflicts. You must resolve and merge such conflicts before importing the data into Experience Manager Guides. 

Perform the following steps to resolve and merge conflicts:  

1. Open the Bulk importer dialog and select **Refetch**.
1. If conflicts are detected, the **Merge required** tab appears and lists the files that contain conflicts. Select the **Merge required** tab, and then select a file from the list to review and resolve the conflicts.
1. Review the content in the following sections:

    ![](images/git-connector-resolve-conflicts.png)

    - In the **AEM** section, the current version of the content present in Experience Manager Guides is displayed. 
    - In the **GIT** section, the latest version of the content from the repository is displayed.
    - In the **Result** section, the merged content is displayed.

1. Review the differences highlighted in the editor and resolve the conflicts using the merge controls:

    - If you want to use the latest changes from the Git repository, ensure that the checkbox for the conflict in the **GIT** section is selected, and then select the corresponding `<<<` control. The selected Git content replaces the conflicting content in the **Result** section.
  
      ![](images/git-connector-replace-with-git.png)

    - If you want to keep content from both versions, clear the checkbox for the conflict and then use the `<<<` control to add the required content to the **Result** section without replacing the existing content.

      ![](images/git-connector-keep-both-versions.png)

    - Similarly, you can use the `>>>` control in the AEM section to keep the version currently available in Experience Manager Guides.
      

1. After reviewing the merged content, perform one of the following actions:

    - Use **Accept AEM** to replace the content in the **Result** section entirely with the version from the **AEM** section, keeping your local changes.
    - Use **Accept GIT** to replace the content in the **Result** section entirely with the version from the **GIT** section, keeping the repository changes.    
    
**Complete merge** is required regardless of which option you use above. Selecting it locks in the current content of **Result** as the resolved version for that file and marks the file as merged.

After all files containing the conflicts are marked as merged, the **Import all** button is enabled. Select **Import all** to complete the process of resolving conflicts.

If the repository contains entirely new content, such as a new topic, paragraph, or line that does not conflict with existing content, it is displayed under **Clean updates**. These updates do not require conflict resolution and can be imported directly.

  ![](images/git-connector-clean-updates.png){width="600"}