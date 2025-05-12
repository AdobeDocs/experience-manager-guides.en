---
title: Configuration overrides
description: Learn how to Configuration overrides
exl-id: dc5f81f7-5b0a-4d12-a944-ba66b0239d5c
feature: Installation
role: Admin
level: Experienced
---
# Configuration overrides {#id216IFC003XA}

For making any configuration updates, the following generic approach should be used:

1.  Access your Cloud Manager's Git repository.

1.  Create a new JSON file at the following location:

    src/main/content/jcr\_root/apps/fmditaCustom/config/

1.  Name the file in the following format:

    $\{PID\}.cfg.json

    Here, the PID is the process ID of the configuration.

1.  Add properties in the JSON file using the following format:

    ```
    {
       "aem.adminuname": "updatedUserjson",
       "valid.characters": "[-a-zA-Z0-9_@$]",
       "dita.serialization": true
    }
    ```

1.  Commit the changes and run the Cloud Manager pipeline to deploy the updated configuration.

## Configure the Experience Manager Guides UI  

>[!NOTE]
>
> The Penultimate UI setting, available until the 2504 release of Experience Manager Guides, has been deprecated. Starting from the 2506 release, you can no longer use this setting to switch back to the old UI.

The 2025.02.0 release of Adobe Experience Manager Guides brings a revamped UI and enhanced features to help you work faster and more efficiently than ever before. This includes, an all-new home page, a cleaner and more organized editor toolbar, dedicated map console, and enhanced features. 

To ensure a smooth transition and minimize disruptions, Experience Manager Guides provides a configuration option that allows you to switch back to the old UI ( and vice-versa) as needed. 

>[!IMPORTANT]
>
> This configuration option to switch between the new and old UI will be available until the 2025.4.0 release. After that, the new UI will become the default, and the option to switch back to the previous UI will no longer be supported.

Perform the following steps to configure Experience Manager Guides UI: 

1. Open Adobe Experience Manager and then select your program which contains the environment you want to configure.
2. Switch to the **Environments** tab.
3. Select the environment name which you want to configure. This should navigate you to the **Environment Information** page.
4. Switch to the **Configuration** tab.
5. Select **Add/Update**.
6. Add the UI configuration details. Ensure you are using the same name and configuration as given in the following screenshot.

    ![](assets/enable-penultimate-ui.png){width="800" align="left"}

    Setting the value to **true** retains the old UI, while **false** activates the new UI.

    

**Parent topic:**[Download and install](download-install.md)
