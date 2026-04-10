---
title: Customize AEM's default dictionary
description: Learn how to Customize AEM's default dictionary
feature: Web Editor Configuration
role: Admin
level: Experienced
exl-id: 51099b42-706f-42b4-993e-7d9577b5a4f0
---
# Customize AEM's default dictionary {#id209SD8000WU}

The Web Editor can be configured to use AEM's spell checker or the browser's spell checker. If you choose to work with AEM's spell checker, then you get the flexibility to define your custom words list. These custom words are then added to the AEM's dictionary and these words are not flagged \(as incorrect\) in the Web Editor.

The following tabs provide instructions to create your custom words list, which are added in AEM's dictionary based on your Experience Manager Guides setup: Cloud Service or On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1.  Create user\_dictionary.txt file with a list of words that you want to define in your custom dictionary.

    >[!NOTE]
    >
    > Each custom word must be defined on a new line.

1.  Save the file at the following location in your Cloud Manager's Git repository:

    /apps/fmdita/config

1.  Save the file.

    Commit the changes and run the Cloud Manager \(CI/CD\) pipeline to deploy configuration changes.


Authors would need to restart their Web Editor session to get the custom words list updated in AEM dictionary.

>[!TAB On-Premise]

1.  Log into AEM and open the CRXDE Lite mode.

1.  Navigate to the following node:

    /apps/fmdita/config

1.  Create a new file named user\_dictionary.txt.

1.  Open the file and add a list of words that you want to define in your custom dictionary.

    The following screenshot shows custom words list added to the user\_dictionary.txt file:

    ![](assets/custom-words-list-dictionary.png){width="650" align="left"}

1.  Save and close the file.


Authors would need to restart their Web Editor session to get the custom words list updated in AEM dictionary.

>[!ENDTABS]

**Parent topic:**[Customize Web Editor](customize-overview.md)
