---
title: Configure custom DITA topic template
description: Learn how to Configure custom DITA topic template
feature: Template Configuration
role: Admin
level: Experienced
exl-id: aaf24a83-3a94-4f77-aa37-7b0398f6ae71
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: df6fa66f-4542-4a6d-90ca-9f146eb5d494
    internal-label: Template configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
---
# Configure custom DITA topic template {#id16A7G0O02TD}

The AEM Guides comes with the following DITA topic templates:

-   Topic

-   Task

-   Concept

-   Reference

-   Glossary

-   Troubleshooting

-   Blank


You can use any of these templates to create topics templates as per your authoring requirements. The Blank DITA template does not contain any structure or elements like the other templates. You can use the Blank template as the base, if your template is highly customized and is not based on any regular DITA topic templates.

To customize DITA topic template and use it for authoring, you need to perform the following three main tasks:

1.  *\(Optional\)* [Configure custom DITA template folder path](#id191LCF0095Z)

1.  [Create custom authoring template](conf-profiles.md#id1917D0EG0HJ)

1.  Add a custom template into the global or folder-level profile as explained in the [Configure authoring templates](conf-profiles.md#id1889D0IL0Y4) section


## Configure custom DITA template folder path {#id191LCF0095Z}

AEM Guides allows you to configure a folder to store your customized DITA map and templates. By default, the template files are stored in the following folder in DAM:

`/content/dam/dita-templates/`

To manage topic and map template files, there are dedicated folders to store the topic and map templates. By default, all topic templates are stored under the `/content/dam/dita-templates/topics`

folder. All map templates are stored under the `/content/dam/dita-templates/maps` folder.

As an administrator, you can choose to create custom map or topic templates in the default folder or create your own folder to store custom templates. If you plan to use the default folder, then you can skip this process.

The following tabs provide instructions to configure custom DITA template folder path based on your Experience Manager Guides setup: Cloud Service or On-Premise.


>[!BEGINTABS]

>[!TAB Cloud Service]

Use the instructions given in [Configuration overrides](download-install-config-override.md#) to create the configuration file. In the configuration file, provide the following \(property\) details to configure a folder for your custom DITA topic templates:

>[!IMPORTANT]
>
> You can skip this process if you want to use the default folder to store custom templates.

|PID|Property Key|Property Value|
|---|------------|--------------|
|`com.adobe.fmdita.config.ConfigManager`|`topic.templates`|Specify a location to store custom templates.<br> If the specified location exists in DAM, then all default map and topic templates are copied into that folder. If the location does not exist, then the folder is created with all default map and topic templates.|

>[!TAB On-Premise]

To configure a folder for your custom DITA topic templates, perform the following steps:

>[!IMPORTANT]
>
> You can skip this process if you want to use the default folder to store custom templates.

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and click on the *com.adobe.fmdita.config.ConfigManager* bundle.

1.  In the **Templates Location** property, specify a location to store custom templates.

1.  Click **Save**.


If the specified location exists in DAM, then all default map and topic templates are copied into that folder. If the location does not exist, then the folder is created with all default map and topic templates.


>[!ENDTABS]


**Parent topic:**[Configure topic and map templates](conf-template-tags.md)
