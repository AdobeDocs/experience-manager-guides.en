---
title: Translate modified topics
description: Learn how to re-translate a modified topic in AEM Guides.
exl-id: b3228ea9-24a8-44aa-8ba4-e8f44754ffe4
feature: Translation
role: User
---
# Translate modified topics {#id16A5A0B6072}

If you make changes in some of the topics, then those topics require re-translation. You can keep track of modified topics from DITA map. From the source language copy folder, select the DITA map file from the Map Console and select the Translation tab. You can view the status of each topic whether it requires re-translation or not.

Perform the following steps to send a modified topic for re-translation:

1.  Select the DITA map file from the source language copy folder from the **Map Console** in the Editor.

1.  Select the **Translation** tab.

1.  In the **Translation** panel on the left, select the **Available Languages** that you want to check the status for and select **Apply**.

    You can view the translation status for each topic. The topics that have another revision of topic available than what was sent for translation, show an **Out of Sync** status.

    >[!NOTE]
    >
    > The translation workflow compares the last saved revision of the topic file in the source language folder with the translated version.

    If you select the arrow to view further details, you can view the particular language copy that is out of sync.

    ![](images/out-of-sync-uuid-new.png){width="800" align="left"}

1.  Select the check box to select the topics that you want to send for re-translation.

    When you select an out of sync topic,  **Mark in Sync** button appears  above the title bar.

    You can use the **Mark in Sync** button to override the Out of Sync status for the topics in the DITA map.  For example, if you have made some very minor changes which really don't need a translation you can mark their status to In Sync.

    >[!NOTE]
    >
    > If you select the **Mark in Sync** button, it sets the topic status to In Sync for the selected Out of Sync topics.

1. You can select the **Send for Translation button**.     

1.  You can choose to create a new translation project or add topics to an existing translation project. Provide the required details to configure the translation project.

1.  Select **Submit**.

    A confirmation message is displayed showing that the topic has been sent for translation.

1.  Navigate to the translation project in the Project console. A new translation job card is created in the folder. Select the ellipsis to view the assets of the folder.

    ![](images/incremental-job-new.png){width="300" align="left"}

1.  To start the translation, select the arrow on the translation job card and select **Start** from the list. A message notifies that the job has started.

    You can also view the status of the topic being translated when you select the ellipsis at the bottom of the translation job card.

    >[!NOTE]
    >
    > If you are using Human translation service, then you need to export the content for translation. Once you have the translated content, then you need to import it back into the translation project.

1. After the translation completes, the status changes to **Ready to Review**. Select the ellipsis to view topic details and do one of the following from the toolbar:

    -   Select **Reveal in Assets** to view and verify the translation.

    -   Select **Accept Translation** if you think that the changes have been translated correctly. A confirmation message is displayed.

    -   Select **Reject Translation** if you think that the job needs to be re-done. A rejection message is displayed.

    >[!NOTE]
    >
    > It is important to Accept or Reject the translated asset, else the file stays in the temporary location and does not get copied to DAM.

1. Navigate back to the DITA map file in the source language folder in Assets UI. The re-translated topics are now In sync.


**Parent topic:**[Translate content](translation.md)
