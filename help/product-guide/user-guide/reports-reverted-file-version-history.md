---
title: Reverted files version history report
description: View reverted files version history reports in AEM Guides. Learn how to access revert version logs from the Assets UI, topic preview, and AEMs tools selection.
exl-id: 74bef625-acd6-49a6-b983-881a782f68d6
feature: Report Generation
role: User
---
# Reverted files version history report {#id205BBC00PRK}

When you are working on multiple simultaneous releases along with multiple authors, your content is bound to have multiple versions. There could be some common information across multiple releases, which different authors could use in their project. To handle such work assignments, authors could end up with multiple versions of files. Such versions could simply be a newer version of a file or a revert to an earlier version. It is a complex task to identify when a file was reverted and why.

Adobe Experience Manager Guides allows you to generate a version history report for an individual file or for all files in a folder. This version history gives you a consolidate view of all versions of a file that were reverted and who created those versions and the reason for creating those versions.

You can access this report from the following places:

-   **Assets UI**: by selecting a file and opening the **Version History** from the left rail. The **Version History** view contains the **Revert Version Logs** link at the bottom of the panel. When you select this link, the selected file's history of the reverted versions is displayed.

    ![](images/revert-log-from-assets-ui.png){width="300" align="left"}

-   **Topic preview**: when you are previewing a topic, there also you can bring up the **Version History** panel from the left rail. You will get a panel similar to the Assets UI from where you can select the **Revert Version Logs** link to access the reverted version history of the active document.

-   **Adobe Experience Manager Tools section**: you can also access this report from Experience Manager Tools section. The following procedure explains how you can access the revert version history from the Experience Manager Tools section.


Perform the following steps to access the Revert History report:

1.  Select Adobe Experience Manager logo at the top and choose **Tools**.

1.  Select **Guides** from the list of tools.

1.  Select the **Version Revert History** tile.

    A blank Revert Version History page is displayed wherein you need to browse to and select a file or folder to generate the report.

1.  Select **Show Logs** to generate the report for the selected file or folder.

    ![](images/revert-version-history-report.png){align="left"}

    The report contains the following details:

    - **File Name**: The title of the topic. Selecting the topic's title link opens the topic preview.

    - **Time Stamp**: The date and time when the topic was reverted to an earlier version.

    - **User**: Name of the user who reverted to an earlier version.

    - **Revert From**: The original version number of the file from where it was reverted.

    - **Revert To**: The version to which the file was reverted to.

    - **Comment**: Any comment given by the user who reverted the file.


**Parent topic:**[Introduction to reports](reports-intro.md)
