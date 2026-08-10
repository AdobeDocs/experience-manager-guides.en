---
title: Configure XML parsing entity for Cloud service and On-Premise
description: Learn how to configure XML parsing entity for Cloud service and On-Premise 
feature: Output Generation
role: Admin
level: Experienced
---
# Configure XML parser entity size limit 

Experience Manager Guides lets you configure a limit on the total entity size that the XML parser accepts during publishing. This helps prevent issues such as XML entity expansion attacks and processing of oversized payloads.

>[!NOTE]
>
>You can configure a limit on the total entity size accepted by the XML parser during publishing, mitigating risks such as XML entity expansion attacks and processing of oversized payloads. Please note that entity size limit handling differs between Java 21 and Java 25; accordingly, environments upgrading to Java 25 are advised to review and validate their configuration to ensure publishing workflows continue to operate without error.

This configuration involves two related properties:

* **Apply XML Parser Total Entity Size Limit** (`dxml.publish.xml.apply.total.entity.size.limit`): Enables or disables the total entity size limit check.
* **XML Parser Total Entity Size Limit** (`dxml.publish.xml.total.entity.size.limit`): Specifies the JAXP `totalEntitySizeLimit` value, in bytes, that is applied to secure XML parsers when the apply flag is enabled.

The following tabs provide instructions to configure these properties based on your Experience Manager Guides setup: Cloud Service or On-Premise.

>[!BEGINTABS]

>[!TAB Cloud Service] 

1. Use the instructions given in [Configuration overrides](download-install-config-override.md) to create the configuration file.

1. In the configuration file, provide the following (property) details:

    |PID|Property Key|Property Value|
    |---|---|---|
    |`com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService`|`dxml.publish.xml.apply.total.entity.size.limit`| **Default value:** "true"|
    |`com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService`|`dxml.publish.xml.total.entity.size.limit`| **Default value:** "50000000"|

>[!TAB On-Premise]

1. Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ```http
    http://<server name>:<port>/system/console/configMgr
    ```

1. Search for and select the *com.adobe.fmdita.publishworkflow.PublishWorkflowConfigurationService* bundle.

1. Configure the following settings as per your requirement:

    * **Apply XML Parser Total Entity Size Limit** (`dxml.publish.xml.apply.total.entity.size.limit`) — By default, this setting is disabled.
    * **XML Parser Total Entity Size Limit** (`dxml.publish.xml.total.entity.size.limit`) — By default, this value is set to `50000000` bytes. This setting takes effect only when the **Apply XML Parser Total Entity Size Limit** setting is enabled.

1. Select **Save**.

>[!ENDTABS]



