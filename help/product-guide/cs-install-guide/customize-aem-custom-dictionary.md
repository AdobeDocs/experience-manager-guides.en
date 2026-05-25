---
title: Customize AEM's default dictionary
description: Learn how to Customize AEM's default dictionary
exl-id: ecffcd14-6728-4938-a209-5c4b12af6fbb
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/omWGECpXvtuNBUH8dcOnggOHmG8z1PevjBmZ-ZcYWjY
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Customize AEM's default dictionary {#id209SD8000WU}

The Web Editor can be configured to use AEM's spell checker or the browser's spell checker. If you choose to work with AEM's spell checker, then you get the flexibility to define your custom words list. These custom words are then added to the AEM's dictionary and these words are not flagged \(as incorrect\) in the Web Editor.

Perform the following steps to create your custom words list, which are added in AEM's dictionary:

1.  Create user\_dictionary.txt file with a list of words that you want to define in your custom dictionary.

    >[!NOTE]
    >
    > Each custom word must be defined on a new line.

1.  Save the file at the following location in your Cloud Manager's Git repository:

    /apps/fmdita/config

1.  Save the file.

    Commit the changes and run the Cloud Manager \(CI/CD\) pipeline to deploy configuration changes.


Authors would need to restart their Web Editor session to get the custom words list updated in AEM dictionary.

**Parent topic:**[Customize Web Editor](conf-web-editor.md)
