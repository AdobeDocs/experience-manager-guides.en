---
title: Import DITA Content from Git with Git Connector (Beta) in Experience Manager Guides
description: Learn how Git Connector (Beta) in Experience Manager Guides allows you to import DITA content from Git repositories, re-fetch updates, preserve GUIDs, and manage conflicts.
feature: Authoring, Features of Web Editor
role: User
TQID: https://experienceleague.adobe.com/DDAXW8cUFjvHUeJIbtL6FaHYSU7NW5fkzTai-7n90ms
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
# Import DITA content from Git repositories using Git Connector

>[!IMPORTANT]
>
> Git connector is currently available as a Beta feature, and remains disabled by default. Please contact the Customer Success team to enable the feature. 

Git Connector allows you to import content from Git repositories into Experience Manager Guides. After the content is imported, teams can continue using Experience Manager Guides for authoring, review, translation, and publishing workflows.

## Prerequisites

Before you start using this feature, ensure that:

- Git Connector is enabled for your environment.
- You have access to the Git repository that contains the DITA content you want to import.
- You know which repository branch and source folder you want to use.
- You know the target folder in Experience Manager Guides where the imported content should be stored.
- Your Administrator has created and configured the Git connector in your environment. For details, view [Create and configure Git Connector from the user interface](../install-conf-guide/conf-git-connector.md). 


## Import content from the connected Git repoistory

After your administrator configures the GitHub connector, you can use it from the Editor to start importing content from a Git repository.Perform the following steps to import content from a Git repository:

1. In the Editor, open the left panel.
1. Select **Data sources**.

    The connected data sources are displayed. 

1. Select the GitHub connector that your Administrator configured. 

1. Select the + icon and then select **Bulk importer**.  

    The Bulk importer dialog is displayed. 

    ![](images/git-bulk-importer-dialog.png)

1. In the Bulk importer dialog, provide a name to the import, select a sub folder from your configured Git repository, and select **Save and Fetch**.  The list of files available for import is displayed in the dialog. Review the list and validate the content before you continue.

    ![](images/git-bulk-importer-import-all.png)

1. After reviewing the files, select **Import all** to import the content into Experience Manager Guides. If you select **Auto sync**, the files are imported automatically after you select **Save and Fetch**.

## Operations you can perform on the impoerted data

After you import content by using the GitHub connector, you can perform the following operations on the imported content:

![](images/git-connector-imported-content-options.png){width="600"}

1. **Preview**: Preview imported content. If the source repository contains updates, review the differences and choose **Refetch** to import the latest changes. 
1. **Delete**: Remove imported content that is no longer required.
1. **Rename**: Rename imported content for easier identification.
1. **View log**: View the import log to review details of the import operation.
1. **View reports**: View and download the **Bulk import report**, which includes details such as:

  - total number of imported files
  - number of successful imports
  - number of failed imports 

  You can also download the detailed report. If some files fail to import, use **Retry failed imports** to try importing them again.

## Review and resolve content conflicts

When you re-fetch content from a Git repository, differences in the content between the repository version and the corresponding content available in Experience Manager Guides are displayed as conflicts. You must resolve and merge such conflicts before importing the data into Experience Manager Guides. 

Perform the following steps to resolve and merge conflicts:  

1. Open the Bulk importer dialog and select **Refetch**.
1. If conflicts are detected, all the files containing the conflicts are listed. From the list, select a file that require review.
1. Review the content in the following panes:

    ![](images/git-connector-resolve-conflicts.png){width="600"}


  - AEM displays the current version in AEM Guides.
  - Git displays the latest version from the repository.
  - Merge displays the merged result.

1. Review the differences highlighted in the editor and perform one of the following actions:

  - Select Accept changes from Git to apply the repository changes to the merged version.
  - Review the merged content and select Mark as merged if no additional changes are required.

After all files containing the conflicts are marked as merged, the **Import all** button is enabled. Select **Import all** to complete the synchronization.

If the repository contains entirely new content, such as a new topic, paragraph, or line that does not conflict with existing content, it is displayed under **Clean updates**. These updates do not require conflict resolution and can be imported directly.

  ![](images/git-connector-clean-updates.png){width="600"}


