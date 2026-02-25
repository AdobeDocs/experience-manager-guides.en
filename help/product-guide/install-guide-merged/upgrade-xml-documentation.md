---
title: Upgrade Adobe Experience Manager Guides
description: Learn how to Upgrade Adobe Experience Manager Guides
feature: Installation
role: Admin
level: Experienced
---
# Upgrade Adobe Experience Manager Guides for version 4.6.0 and above 

This article provides instructions to upgrade your Experience Manager Guides versions for  4.6.0 and above.

>[!NOTE]
>
> Follow the upgrade instructions specific to the licensed version of your product.

You can upgrade your current version of Experience Manager Guides to version 5.1.0 Service Pack 3:

- If you are using version 5.1.0, or 5.1.x , then you can directly upgrade to version 5.1.0 Service Pack 3. 
- If you are using version 4.6.0, 4.6.x, 5.0.0, or 5.0.x, then you need to upgrade to version 5.1.0.
- If you are on a version prior to 4.6.0, refer to [Upgrade Adobe Experience Manager Guides for version 4.4.0 and earlier](./upgrade-xml-documentation-prev-versions.md) for detailed upgrade instructions. 

>[!NOTE]
>
> You must install AEM service pack before upgrading Experience Manager Guides version.

For more details, refer to the following procedures:

- [Upgrade to version 5.1.0](#upgrade-to-version-510)
- [Upgrade to version 5.0.0](#upgrade-to-version-500)
- [Upgrade to version 4.6.0](#upgrade-to-version-460)

>[!IMPORTANT]
>
> Before you begin to upgrade, take a complete system backup to avoid any loss of data.


## Upgrade to version 5.1.0 


>[!IMPORTANT]
>
> If you are currently on AEM 6.5 and plan to move to AEM 6.5 LTS, make sure to complete the AEM upgrade first before proceeding with the Experience Manager Guides 5.1.0 upgrade. For details, view [Upgrading to Adobe Experience Manager (AEM) 6.5 LTS](https://experienceleague.adobe.com/en/docs/experience-manager-65-lts/content/implementing/deploying/upgrading/upgrade). 

**Prerequisites**

>[!NOTE]
>
>If you are upgrading to 5.1.0 Service Pack 3, then you need to be on the version 5.1.0 or 5.1.x of Experience Manager Guides. The upgrade process for the 5.1.0 Service Pack 3 release follows the same steps as the 5.1.0 release.

Before you start the Experience Manager Guides 5.1.0 upgrade process, ensure that you have:

1. Upgraded to Experience Manager Guides version 4.6.3, 4.6.4, 5.0.0, or 5.0.0 Service Pack 1.
1. (Optional) Closed all translation tasks.
1. Changed the log level to **INFO** for `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` class and append these logs in a new log file, for example, `logs/translation_upgrade.log`.

>[!NOTE]
>
> The post-processing and indexing may take a few hours. We recommend you to start the upgrade process during the off-peak hours.

**Install version 5.1.0**

Download the 5.1.0 version package from [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) and follow the instructions provided in [Installation and post-installation upgrade workflow](#installation-and-post-installation-upgrade-workflow) to complete the upgrade process.


## Upgrade to version 5.0.0

>[!TIP]
>
> Upgrading to version 5.0.0 Service Pack 3 depends on the current version of Experience Manager Guides. If you are using version 5.0.0 Service Pack 2, 5.0.0 Service Pack 1 or 5.0.0, then you can directly upgrade to version 5.0.0 Service Pack 3. The upgrade steps are the same as those for version 5.0.0.

>[!NOTE]
>
> The post-processing and indexing may take a few hours. We recommend you to start the upgrade process during the off-peak hours.

**Prerequisites**

Before you start the Experience Manager Guides 5.0.0 upgrade process, ensure that you have:

1.  Upgraded to Experience Manager Guides version 4.6.3, 4.6.1, 4.6.0, or 4.4.
1.   (Optional) Closed all translation tasks.
1. Changed the log level to **INFO** for `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` class and append these logs in a new log file, for example, `logs/translation_upgrade.log`.


**Install version 5.0.0**

Download the 5.0.0 version package from [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) and follow the instructions provided in [Installation and post-installation upgrade workflow](#installation-and-post-installation-upgrade-workflow) to complete the upgrade process.

## Upgrade to version 4.6.0

>[!TIP]
>
> It is recommended to install 4.6.0 Service Pack 4 on top of version 4.6.0 ,4.6.0 Service Pack 1 or 4.6.0 Service Pack 3. The upgrade process for the 4.6.0 Service Pack 4 release follows the same steps as the 4.6.0 release. 

Upgrading to version 4.6.0 depends on the current version of Experience Manager Guides. If you are using version 4.4.0, 4.3.1, 4.3.0, 4.2, or 4.2.1 (Hotfix 4.2.1.3) then you can directly upgrade to version 4.6.0.

>[!NOTE]
>
> The post-processing and indexing may take a few hours. We recommend you to start the upgrade process during the off-peak hours.

**Prerequisites**

Before you start the Experience Manager Guides 4.6.0 upgrade process, ensure that you have:

1. Upgraded to Experience Manager Guides version 4.3.1, 4.3.0, or 4.2.1 (Hotfix 4.2.1.3).
1. (Optional) Closed all translation tasks.
1. Changed the log level to **INFO** for `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` class and append these logs in a new log file, for example, `logs/translation_upgrade.log`.

**Install version 4.6.0**

Download the 4.6.0 version package from [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) and follow the instructions provided in [Installation and post-installation upgrade workflow](#installation-and-post-installation-upgrade-workflow) to complete the upgrade process. 

## Installation and post-installation upgrade workflow

### Install the version package 

Peform the following steps to install the version package: 

1. Install the version package on which you want to upgrade.
1. You can choose to hit the trigger to start the translation map upgrade job. For details, see [Enable trigger of script via a Servlet](#enable-trigger-of-script-via-a-servlet).

1. After you complete the package installation, wait for the following message in the logs:

    `Completed the post deployment setup script`

    The above message indicates that all the steps of installation are complete.

    In case you encounter any of the following errors, report them to your customer success team:

    - Error in post deployment setup script
    - Exception while porting the translation MAP
    - Unable to port translation map from v1 to v2 for property
1. (Optional) Upgrade Oxygen connector plugin released with version you are upgrading to.
1. Clear the browser cache after installing the package.

### Post installation process

After you install Experience Manager Guides, you may merge the various configurations applicable from the newly installed version to your setup.

>[!NOTE]
>
> The dam-update-asset model may be customized. So, if any customizations have been done, then we need to sync the customizations and Experience Manager Guides into the working copy of the model.

**DAM Update Asset workflow \(Post-processing changes\):**

1.  Open URL:

    ```
    http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
    ```

1.  Select **DAM Update Asset workflow**.
1.  Select **Edit**.
1.  If the **DXML Post Process Initiator** component is present, ensure that the customizations are synced.
1.  If the **DXML Post Process Initiator** component is absent, perform the following steps to insert it:

    - Select **Insert component** \(Responsible for Experience Manager Guides post-processing as the final step in the process\).
    - Configure the **Process step** with below details:

        **Common tab:**

        - **Title:** DXML Post Process Initiator

        - **Description**: DXML post process initiator step which will trigger a sling job for DXML post-processing of the modified/created asset

        **Process tab**

        - Select **DXML Post Process Initiator** from the **Process** drop down
        - Select **Handler Advance**
        - Select **Done**

1.  Select **Sync** on the top right after completing the changes. You will receive a success notification.

    >[!NOTE]
    >
    > Refresh and verify that customized changes and the Experience Manager Guides post-processing step is present in the final workflow model.

1.  Once **DAM Update Asset workflow** is validated, check corresponding launcher configurations. To do so, go to AEM Workflow interface and open launchers.

    ```http
    http://localhost:4502/libs/cq/workflow/content/console.html
    ```

    Find and make changes \(if necessary\) to the following two launchers \(that should be active\) corresponding to **DAM Update Asset workflow**:

1.  Launcher for "*Node Created*" for **DAM Update Asset workflow**- for condition `"jcr:content/jcr:mimeType!=video"`, the 'Globbing' value should be:

    ```json
    /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
    ```

    -   'excludeList' should have `"event-user-data:changedByWorkflowProcess"`.
    -   Launcher for "*Node Modified*" for **DAM Update Asset workflow -** for condition "`jcr:content/jcr:mimeType!=video`", the 'Globbing' value should be:

    ```json
    /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
    ```
    
    - `excludeList` should have `"event-user-data:changedByWorkflowProcess"`.

1. Once the upgrade is complete, ensure any of the customizations/overlays are validated and updated to match the new application code. Some examples are given below:
    - Any components overlayed from `/libs/fmditaor/libsshould` be compared with the new product code and updates should be done in overlayed files under/apps.
    - Any `clientlib` categories used from product, should be reviewed for changes. Any overridden configurations `\(examples below\)` should be compared with the latest ones so as to get the latest features:
    - elementmapping.xml
    - `ui\_config.json\(may have been set in folder profiles\)`
    - amended `com.adobe.fmdita.config.ConfigManager`

1. If you have added any customizations in damAssetLucene, you may need to apply them again. After making those changes, set reindex as true. This will reindex all the existing nodes with the customizations. Once completed, the reindex flag will be set to false again. This may take a few hours depending on number of assets in the system.

### Steps to reindex the Experience Manager Guides indexes

1. Open `crx/de` and navigate to the index path:  `/oak:index/guidesAssetProperties`
2. Set the reindex property as `true` (`false` by default) and click **Save All**.
3. Once the reindex is complete, the reindex property is set to `false` again, and the reindex count is incremented by 1. 

    >[!NOTE]
    >
    > This may take a few minutes, depending on the amount of data present.
4. Follow the same steps for other added or modified indices: `guidesBulkActivation`, `guidesPeerLinkIndex`,  and `guidesKonnectTemplateIndex`. 

### Steps to index the existing content

Perform the following steps for indexing the existing content:

- Run a POST request to the server \(with correct authentication\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Optional: You can pass specific paths of the maps to index them, by default all maps will be indexed || Example : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

-   The API will return a `jobId`. To check the status of the job, you can send a GET request with job id to the same end point - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(for example: ` http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

-   Once the job is complete, the above GET request will respond with success and mention if any maps failed. The successfully indexed maps can be confirmed from the server logs.


>[!NOTE]
>
> If you are using the custom schema, you must define the path of the custom DTD and XSD catalog.xml files in the AEM repository in the **Integrate Catalogs** option.

### Steps to handle the `'fmdita rewriter'` conflict

Experience Manager Guides has a [**custom sling rewriter**](../cs-install-guide/conf-output-generation.md#custom-rewriter) module for handling the links generated in case of cross-maps (links between the topics of two different maps).

If you have another custom sling rewriter in your codebase,  use an `'order'` value greater than 50, as Experience Manager Guides sling rewriter uses `'order'` 50.  To override this, you need a value >50. For more details, view [Output Rewriting Pipelines](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

During this upgrade, since the `'order'` value is changed from 1000 to 50, you need to merge the existing custom rewriter, if any, with `'fmdita-rewriter'`.


### Steps to reindex the damAssetLucene

Index definition is updated for damAssetLucene with AEM Guides. After upgrading to the required version, refer to [this article](https://experienceleague.adobe.com/en/docs/experience-cloud-kcs/kbarticles/ka-16460) for reindexing the damAssetLucene.

>[!NOTE]
>
> While following the documentation, make sure both properties (`reindex=true` and `reindex-async=true` for `/oak:index/damAssetLucene`) are updated simultaneously via Save operation.

