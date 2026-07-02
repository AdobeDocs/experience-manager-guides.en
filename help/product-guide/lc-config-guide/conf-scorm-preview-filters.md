---
title: Configure SCORM preview filters
description: Learn how to configure SCORM preview filters
feature: Configuration
role: Admin
level: Experienced
---
# Configure SCORM preview

This article explains how to configure the Experience Manager Guides SCORM preview to manage which external domains are permitted to serve stylesheets, images, fonts, media, and embedded content in the SCORM preview output. The following steps explain how to configure various filters for SCORM preview depending on the setup you are using:

>[!BEGINTABS]

>[!TAB Cloud Service]

1. Use the instructions given in [Configuration overrides](../install-conf-guide/download-install-config-override.md) to create the configuration file.

1. In the configuration file, provide the following property details:

   | PID | Property Key | Default Value |
   |---|---|---|
   | `com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter` | `additional.style.src` | `https://fonts.googleapis.com` |
   | `com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter` | `additional.img.src` | - |
   | `com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter` | `additional.font.src` | `https://fonts.gstatic.com` |
   | `com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter` | `additional.media.src` | - |
   | `com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter` | `additional.frame.src` | `https://www.youtube-nocookie.com`, `https://www.youtube.com` |


1. Save the configuration file and deploy it to your Cloud Service environment. 

Once saved, the SCORM preview begins applying the updated domain allowlist. External resources from domains that have not been added to this configuration will not be available in the preview. 

>[!NOTE]
>
> This applies only to the preview environment; the downloadable SCORM package continues to deliver all authored content as intended.


>[!TAB On-Premise]

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1.  Search for and select the **Guides SCORM Preview Filter (com.adobe.fmdita.publishworkflow.ScormPreviewResponseFilter)** bundle.

    ![](assets/scorm-preview-filters.png){width="600"}


1. In the bundle configuration, add the permitted domain URLs for each resource type as required:

   | Field | Description |
   |---|---|
   | **Additional style-src host** | Domains from which external CSS stylesheets are authorized to load (by default, `https://fonts.googleapis.com`). |
   | **Additional image-src host** | Domains from which external images are authorized to load. |
   | **Additional font-src host** | Domains from which external font files (OTF, WOFF, and so on) are authorized to load (by default, `https://fonts.gstatic.com`).|
   | **Additional media-src host** | Domains from which external media files are authorized to load. |
   | **Additional frame-src host** | Domains from which iframe content is authorized to be embedded (by default, `https://www.youtube.com` to allow YouTube video embeds). |

1. Select **Save**.

Once saved, the SCORM preview begins applying the updated domain allowlist. External resources from domains that have not been added to this configuration will not be available in the preview. 

>[!NOTE]
>
> This applies only to the preview environment; the downloadable SCORM package continues to deliver all authored content as intended.

>[!ENDTABS]