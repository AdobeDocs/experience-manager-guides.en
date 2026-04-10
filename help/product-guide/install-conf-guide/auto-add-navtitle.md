---
title: Include @navtitle attribute by default
description: Learn how to Include @navtitle attribute by default
feature: Web Editor Configuration
role: Admin
level: Experienced
---
# Include @navtitle attribute by default {#id2115BC0J0XA}

You can add different types of reference files in a map, for example topic, reference, task, \(sub\) maps, and so on. Most of these files support the `@navtitle` attribute. However, not many authors use it consistently. If you want to enforce usage of the `@navtitle` attribute in all referenced files in a map, then you can do so with a simple configuration.

Once enabled, every reference file that you add in a map will automatically get the `@navtitle` attribute added to its properties. The `@navtitle` will also get the value of the `title` element of the referenced content.

The following tabs provide instructions to include `@navtitle` attribute by default in reference files' properties based on your Experience Manager Guides setup: Cloud Service or On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service]

1.  To download the UI configuration file log into Adobe Experience Manager as an administrator.
1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.
1.  Select **Guides** from the list of tools and click the **Folder Profiles**.
1.  Click on the **Global Profile** tile.
1.  Select the **XML Editor Configuration** tab and click **Edit** icon on the top
1.  Click the **Download** icon to download the ui\_config.json file on your local system.
1.  You can make this change at the Global level or at a folder level profile. Depending on where you want to make this change, you need to download the respective ui\_config.json file. For more information about downloading ui\_config.json file, see [Configure and customize the XML Web Editor](conf-profiles.md#id2065G300O5Z).

1.  Search for the `ditaAttributes` definition.

    The default definition of `ditaAttributes` is:

    ```
    "ditaAttributes": {
                            "attributes": [],
                            "constraint": false,
                            "required": {}
                            },
    ```

1.  Change the `required` parameter as shown below:

    ```
    "required": {"navtitle": true}
    ```

    When set to `true`, the **Refresh navigation title attribute** button is enabled to show up in the Editor toolbar. When set to `false` or left empty, the button remains hidden in the Editor. 
1. Save the file.

1. Upload the file in the corresponding profile \(Global or Folder\).


With this configuration, every reference file that you add to a map will contain the `@navtitle` attribute by default. 

>[!TAB On-Premise]

1.  Download the ui\_config.json file.

    You can make this change at the Global level or at a folder level profile. Depending on where you want to make this change, you need to download the respective ui\_config.json file. For more information about downloading ui\_config.json file, see [Configure and customize the XML Web Editor](conf-profiles.md#id2065G300O5Z).

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

>[!ENDTABS]

**Parent topic:**[Customize Web Editor](customize-overview.md)
