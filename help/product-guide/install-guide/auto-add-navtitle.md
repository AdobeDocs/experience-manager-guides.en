---
title: Include @navtitle attribute by default
description: Learn how to Include @navtitle attribute by default
exl-id: 3def20dc-dd24-4526-ae36-45708249d34a
feature: Web Editor Configuration
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/bwVOZrkVrn6QPq7BoUttFvnFAzdLIL6--JGCoHYkA0o
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
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
    internal-label: Profiles
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Include @navtitle attribute by default {#id2115BC0J0XA}

You can add different types of reference files in a map, for example topic, reference, task, \(sub\) maps, and so on. Most of these files support the `@navtitle` attribute. However, not many authors use it consistently. If you want to enforce usage of the `@navtitle` attribute in all referenced files in a map, then you can do so with a simple configuration.

Once enabled, every reference file that you add in a map will automatically get the `@navtitle` attribute added to its properties. The `@navtitle` will also get the value of the `title` element of the referenced content.

To include `@navtitle` attribute by default in reference files' properties, perform the following steps:

1.  Download the ui\_config.json file.

    You can make this change at the Global level or at a folder level profile. Depending on where you want to make this change, you need to download the respective ui\_config.json file. For more information about downloading ui\_config.json file, see [Configure and customize the XML Editor](conf-folder-level.md#id2065G300O5Z).

1.  Search for the `ditaAttributes` definition.

    The default definition of `ditaAttributes` is:

    ```json
    "ditaAttributes": {
    "attributes": [],
    "constraint": false,
    "required": {}
    },
    ```

1.  Change the `required` parameter as:

    ```json
    "required": {"navtitle": true}
    ```

1.  Save the file.

1.  Upload the file in the corresponding profile \(Global or Folder\).


With this configuration, every reference file that you add to a map will contain the `@navtitle` attribute by default.
