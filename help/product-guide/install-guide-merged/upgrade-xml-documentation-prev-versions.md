---
title: Upgrade Adobe Experience Manager Guides On Premise Previous Versions
description: Learn how to Upgrade Adobe Experience Manager Guides
feature: Installation
role: Admin
level: Experienced
---
# Upgrade Adobe Experience Manager Guides On Premise (Version 4.4.0 and earlier)

This article provides instructions to upgrade **Adobe Experience Manager Guides** versions **prior to 4.6.0** (up to and including **4.4.0**). 

If you are on a version **prior to 3.8.5**, refer to the **Upgrade Experience Manager Guides** section in the product‑specific installation guide available on [Adobe Experience Manager Guides help PDF archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

For upgrade instructions for newer releases, refer to [Upgrade Adobe Experience Manager Guides for version 4.6.0 and above](./upgrade-xml-documentation.md). 

## Before you begin

>[!NOTE]
>
> You must upgrade instructions specific to the licensed version of your product and install AEM service pack before upgrading Experience Manager Guides version.

>[!IMPORTANT]
>
> Before you begin to upgrade, take a **complete system backup** to avoid any loss of data. 

## Upgrade paths covered in this article

This article includes procedures for: 

- [Upgrade to version 4.4.0](#upgrade-to-version-440)
- [Upgrade to version 4.3.1.5](#upgrade-to-version-4315)
- [Upgrade to version 4.3.1](#upgrade-to-version-431)
- [Upgrade to version 4.3.0](#upgrade-to-version-430)
- [Upgrade to version 4.2.1](#upgrade-to-version-421)
- [Upgrade to version 4.2](#upgrade-to-version-42)
- [Upgrade from 3.8.5 to version 4.0](#upgrade-from-version-385-to-version-40)


## Global prerequisites (applies to all upgrades unless a procedure says otherwise)

Before running the upgrade process, complete these tasks: 

1. Import review comments in topics that are open for review. 
2. Close all active reviews. 
3. Close all translation tasks. 
4. Uninstall any Experience Manager Guides hotfixes installed on top of the previous version (major or patch release). 

Some upgrades also require setting log level to `INFO` for a translation upgrade class and logging to a separate file; those requirements are called out in the relevant upgrade procedure(s). 

## Upgrade from version 3.8.5 to version 4.0

>[!NOTE]
>
> This upgrade process is applicable **only** from **3.8.5** to **4.0**. For upgrades from **3.4 or higher** to **3.8.5**, refer to the product‑specific installation guide available on [Adobe Experience Manager Guides help PDF archive](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

If you are using Experience Manager Guides version **3.8.5**, you can upgrade to version **4.0** without uninstalling the previous version. 

### Before you install version 4.0

1. Ensure Experience Manager Guides is on version **3.8.5**. 
2. Download the upgrade script package: search for **"XML Documentation solution 4.0 Upgrade Package"** on the Adobe Software Distribution Portal (downloads a `.zip`). 
3. Upload the package to AEM via **Package Manager** and install it. 
4. After the upgrade package is installed, run the scripts in the order described below. 

**Check upgrade compatibility API**

This API is designed to assess the current system status and report if the upgrade is possible or not. To run this script, trigger the below given endpoint:

|End Point|/bin/dxml/upgrade/3xto4x/report|
| --- | --- |
|Request Type|**GET** You can use a web browser, where you are logged in to the AEM instance as an administrator.|
|Expected Response|-   In case all required nodes can be moved, you will get a passed check. <br>-   In case a node is present at the target location, you will get a relevant error. Clean up the repository \(delete node /var/dxml\) and reinstall the upgrade package and then trigger this endpoint again. <br>**Note:** This is not a common error as the target location is not used earlier by 3.x Experience Manager Guides. <br> -   If this script does not succeed, do not proceed and report to your customer success team.|

**System data migration API**

This API is designed to migrate the system data as mentioned in the **Migration Mapping** section.

1. Do not execute this script if the Check upgrade compatibility API fails \(do not proceed\).
1. Once the Check upgrade compatibility API returns success, you can run the upgrade script.

|End Point|/bin/dxml/upgrade/3xto4x|
| --- | --- |
|Request Type|**POST** This script is a POST request hence should be executed via agents like Postman.|
|Expected Response|-   Once the migration is successful, you can install XML Documentation solution version 4.0.<br>-   In case there are errors, restore to the last checkpoint and share the error logs along with API output with your customer success team.|


**Migration mapping**

This API migrates all the data under the source location to the target location. 

|Source|Target|
|------|------|
|/content/fmdita|/var/dxml|
|/content/dxml|/var/dxml|
|/etc/fmdita|/libs/fmdita|

### Install version 4.0

1. Install version 4.0 only if the upgrade steps were successful.
1. Download 4.0 version package from [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html):

    - If you are using UUID version of software, search for "4.0 UUID Release for XML Documentation solution for AEM 6.5."
    - If you are using Non-UUID version of software, search for "4.0 Non-UUID Release for XML Documentation solution for AEM 6.5."
    Upload the package to the existing AEM server instance\(s\) using CRX Package Manager and install it.

        >[!NOTE]
        >
        > Wait for all system components to start.

1. Clear the browser cache after installing the package.
1. If a dispatcher is configured on AEM Author instance, perform the following steps:
    - Ensure the following are handled in dispatcher rules:
    - The URL pattern /home/users/\*/preferences is whitelisted.
    - The URL pattern /libs/cq/security/userinfo.json is not cached.
1. Clear dispatcher cache \(to clear any `clientlibs` cached\).

## Upgrade to version 4.2

You can upgrade to version **4.2** directly if you are using version **4.0**, **4.1**, or **4.1.x**. 

### Before you install version 4.2

Before you start the Experience Manager Guides 4.2 upgrade process, ensure that you have:

1. Upgraded to Experience Manager Guides **4.0**, **4.1**, or **4.1.x**. 
2. Closed all translation tasks. 
3. Set log level to `INFO` for `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` and log to a new log file (for example, `logs/translation_upgrade.log`). 

    >[!NOTE]
    > 
    > You should close all active reviews. If reviews are not closed while upgrading to 4.2, older in‑progress review tasks can continue to open older review pages; new review tasks created after the upgrade display the latest functionality updates. 

### Install version 4.2

1. Download the **4.2** package from [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html). 
2. Install the 4.2 package. 
3. After installation, wait for the following message in the logs: 

    `Completed the post deployment setup script` 

    The above message indicates that all installation steps are complete.

    If you encounter any of the following errors, report them to Customer Success: 

    - `Error in post deployment setup script` 
    - `Exception while porting the translation MAP` 
    - `Unable to port translation map from v1 to v2 for property` 

4. (Optional) Upgrade Oxygen connector plugin released with version 4.2.
5. Clear the browser cache after installing the package.
6. Continue upgrading the customizations as detailed out in the next section.

### After you install version 4.2

>[!IMPORTANT]
>
> Hi-tech template is not displayed on upgraded server. To include the hi-tech template on your server you can copy it: Source: `/libs/fmdita/pdf/Hi-Tech` Destination: `/content/dam/dita-templates/pdf`.

Then proceed with the shared post‑upgrade tasks in [Common post upgrade tasks (all versions)](#common-postupgrade-tasks-all-versions). 

## Upgrade to version 4.2.1

>[!TIP]
>
> It is recommended to install **Hotfix 4.2.1.3** on top of version **4.2.1**. 

You can upgrade to version **4.2.1** directly if you are using **4.1**, **4.1.x**, or **4.2**. 

>[!NOTE]
>
> Post‑processing and indexing may take a few hours. Start the upgrade during off‑peak hours. 

### Before you install version 4.2.1

1. Upgrade to Experience Manager Guides **4.1**, **4.1.x**, or **4.2**. 
2. Close all translation tasks. 
3. Set log level to `INFO` for `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` and log to a new file (for example, `logs/translation_upgrade.log`). 

>[!NOTE]
>
> You should close all active reviews (same behavior as 4.2). 

### Install version 4.2.1

1. Download the **4.2.1** package from [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html). 
2. Install the 4.2.1 package. 
3. Optionally trigger the translation map upgrade job. For details, see [Enable trigger of script via a Servlet](#enable-trigger-of-script-via-a-servlet).

4. After installation, wait for: `Completed the post deployment setup script` in logs. 
    
    Report these errors to Customer Success:  
        
    - `Error in post deployment setup script`
    - `Exception while porting the translation MAP`
    - `Unable to port translation map from v1 to v2 for property` 
5. (Optional) Upgrade Oxygen connector plugin released with version **4.2** 
6.  Clear browser cache. 
7.  Continue with [Common post upgrade tasks (all versions)](#common-postupgrade-tasks-all-versions). 

### After you install version 4.2.1

>[!IMPORTANT]
>
> Hi-tech template is not displayed on upgraded server. To include the hi-tech template on your server you can copy it: Source: `/libs/fmdita/pdf/Hi-Tech` Destination: `/content/dam/dita-templates/pdf`.

Proceed with [Common post upgrade tasks (all versions)](#common-postupgrade-tasks-all-versions)  and (if required) [Index existing content for map find and replace](#index-existing-content-for-map-find-and-replace).


## Upgrade to version 4.3.0 

Upgrading to version 4.3.0 depends on the current version of Experience Manager Guides. If you are using version 4.2 or 4.2.x then you can directly upgrade to version 4.3.0.

>[!NOTE]
>
>The post-processing and indexing may take a few hours. We recommend you to start the upgrade process during the off-peak hours.

### Before you install version 4.3.0

Before you start the Experience Manager Guides 4.3.0 upgrade process, ensure that you have:

1. Upgraded to Experience Manager Guides version 4.2 or 4.2.x and completed their respective installation step.
1. Closed all translation tasks.

### Install version 4.3.0

1. Download 4.3.0 version package from [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Install version 4.3.0 package.
1. Clear the browser cache after installing the package.
1. Upgrade the `ui_config.json` file from the **XML Editor Configuration** tab in the Folder Profile.

### After you install version 4.3.0

Proceed with:

- [Common post upgrade tasks (all versions)](#common-postupgrade-tasks-all-versions) 
- If applicable: [Post process existing content for broken link report](#post-process-existing-content-for-broken-link-report)

## Upgrade to version 4.3.1

Upgrading to version 4.3.1 depends on the current version of Experience Manager Guides. If you are using version 4.3.0, 4.2, or 4.2.1 then you can directly upgrade to version 4.3.1.

>[!NOTE]
>
>The post-processing and indexing may take a few hours. We recommend you to start the upgrade process during the off-peak hours.

### Before you install version 4.3.1

Before you start the Experience Manager Guides 4.3.1 upgrade process, ensure that you have:

1. Upgraded to Experience Manager Guides version 4.3.0, 4.2, or 4.2.1 and completed their respective installation step.
1. (Optional) Closed all translation tasks.
1. Changed the log level to **INFO** for `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` class and append these logs in a new log file, for example, `logs/translation_upgrade.log`.

### Install version 4.3.1

1. Download 4.3.1 version package from [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Install version 4.3.1 package.
1. Optionally trigger the translation map upgrade job. For details, see [Enable trigger of script via a Servlet](#enable-trigger-of-script-via-a-servlet). 
1. After installation, wait for: `Completed the post deployment setup script` in logs. 
    Report these errors to Customer Success:  
        `Error in post deployment setup script`, `Exception while porting the translation MAP`, `Unable to port translation map from v1 to v2 for property` 
1. (Optional) Upgrade Oxygen connector plugin released with version **4.2**. 
1. Clear browser cache. 

### After you install version 4.3.1

Proceed with:

- [Common post upgrade tasks (all versions)](#common-postupgrade-tasks-all-versions) 
- If applicable: [Index existing content for map find and replace](#index-existing-content-for-map-find-and-replace)
- If applicable: [Post process existing content for broken link report](#post-process-existing-content-for-broken-link-report)


## Upgrade to version 4.3.1.5

You can upgrade to **4.3.1.5** directly if you are using version **4.3.1**. 

### Install version 4.3.1.5

1.  Download the **4.3.1.5** package from [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html). 
2.  Install the 4.3.1.5 package. 
3.  Wait for the installation process to complete successfully. 
4.  Continue upgrading the customizations as detailed out in the next section.. 

## After you install version 4.3.1.5

>[!NOTE]
>
>If you want to use org.apache.velocity bundle, perform the following  steps before uploading the bundle:
> 1. Go to `<server>:<port>/system/console/bundles`
> 1. Search for org.apache.velocity.
> 1. Uninstall the searched bundle.
> 1. Install the required velocity bundle.

1.  Once the upgrade is complete, ensure any of the customizations/overlays are validated and updated to match the new application code. Some examples are given below:
    -   Any components overlayed from `/libs/fmdita` or` /libs` should be compared with the new product code and updates should be done in overlayed files under `/apps` .
    -   Any clientlib categories used from product, should be reviewed for changes. Any overridden configurations \(examples below\) should be compared with the latest ones so as to get the latest features:
    -   `elementmapping.xml`
    -   `ui\_config.json\` (may have been set in folder profiles\)
    -   amended `com.adobe.fmdita.config.ConfigManager`


## Upgrade to version 4.4.0

You can upgrade to **4.4.0** directly if you are using: **4.3.1**, **4.3.0**, **4.2**, or **4.2.1 (Hotfix 4.2.1.3)**. 

>[!NOTE]
>
>The post-processing and indexing may take a few hours. We recommend you to start the upgrade process during the off-peak hours.

### Before you install version 4.4.0

Before you start the Experience Manager Guides 4.4.0 upgrade process, ensure that you have:

1. Upgraded to Experience Manager Guides version 4.3.1, 4.3.0, or 4.2.1 (Hotfix 4.2.1.3) and completed their respective installation step.
1. (Optional) Closed all translation tasks.
1. Changed the log level to **INFO** for `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` class and append these logs in a new log file, for example, `logs/translation_upgrade.log`.

### Install version 4.4.0

1. Download 4.4.0 version package from [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
2. Install the 4.4.0 package. 
3. Optionally trigger the translation map upgrade job. For details, see [Enable trigger of script via a Servlet](#enable-trigger-of-script-via-a-servlet). 
4. After you complete the package installation, wait for the following message in the logs:

    `Completed the post deployment setup script`

    The above message indicates that all the steps of installation are complete.

    In case you encounter any of the following ERROR prefixes, report them to your customer success team:

    - `Error in post deployment setup script`
    - `Exception while porting the translation MAP`
    - `Unable to port translation map from v1 to v2 for property`
5. (Optional) Upgrade Oxygen connector plugin released with version **4.4.0**. 
6. Clear browser cache. 
7. Continue with:

    - [Common post‑upgrade tasks (all versions)](#common-ppostupgrade-tasks-all-versions)
    - [Index existing content for map find and replace](#index-existing-content-for-map-find-and-replace) (Only if applicable)
    - [Post-process existing content for broken link report](#post-process-existing-content-for-broken-link-report) (Only if applicable)
    - [Translation map upgrade (servlet trigger)](#translation-map-upgrade-servlet-trigger) (Only if applicable)


## Common post‑upgrade tasks (all versions)

After you install Experience Manager Guides, you may need to merge configurations applicable from the newly installed version to your setup. 

>[!NOTE]
>
> The **DAM Update Asset** workflow model may be customized. If you have customizations, sync them with Experience Manager Guides changes in the working copy of the model. 

### Validate DAM Update Asset workflow (post‑processing changes)

1.  Open the AEM Workflow Models UI (example shown in source):  
    `http://<host>:4502/libs/cq/workflow/admin/console/content/models.html` 
2.  Select **DAM Update Asset workflow**. 
3.  Select **Edit**. 
4.  If the **DXML Post Process Initiator** component is present, ensure customizations are synced. 
5.  If the component is absent, insert it: 
    1.  Click **Insert component** (responsible for Guides post‑processing as the final step). 
    2.  Configure the **Process step**: 
        **Common tab**
            - Title: `DXML Post Process Initiator` 
            - Description: `DXML post process initiator step which will trigger a sling job for DXML post-processing of the modified/created asset` 
        **Process tab**
            - Process: select `DXML Post Process Initiator` 
            - Select `Handler Advance` 
            - Select `Done` 
    3.  Click **Sync** on the top right after completing the changes. You will receive a success notification.

>[!NOTE]
>
> Refresh and verify that customized changes and the Experience Manager Guides post-processing step is present in the final workflow model.

### Validate launcher configurations

1. Go to the AEM Workflow interface and open **Launchers**. 

```http
    http://localhost:4502/libs/cq/workflow/content/console.html
```

1. Find and make changes \(if necessary\) to the following two launchers \(that should be active\) corresponding to **DAM Update Asset workflow**:

1. Launcher for "*Node Created*" for **DAM Update Asset workflow**- for condition `"jcr:content/jcr:mimeType!=video"`, the 'Globbing' value should be:

    ```json
    /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
    ```

    - `excludeList` should have `"event-user-data:changedByWorkflowProcess"`.
    -  Launcher for *Node Modified* for **DAM Update Asset workflow -** for condition "`jcr:content/jcr:mimeType!=video`", the 'Globbing' value should be:

    ```json
    /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
    ```
    
    - `excludeList` should have `"event-user-data:changedByWorkflowProcess"`.

### Validate overlays and customizations

After the upgrade completes: 

1.  Once the upgrade is complete, ensure any of the customizations/overlays are validated and updated to match the new application code. Some examples are given below:
    -   Any components overlayed from/libs/fmditaor/libsshould be compared with the new product code and updates should be done in overlayed files under/apps.
    -   Any clientlib categories used from product, should be reviewed for changes. Any overridden configurations \(examples below\) should be compared with the latest ones so as to get the latest features:
    -   elementmapping.xml
    -   ui\_config.json\(may have been set in folder profiles\)
    -   amended `com.adobe.fmdita.config.ConfigManager`

1. If you have added any customizations in damAssetLucene, you may need to apply them again. After making those changes, set reindex as true. This will reindex all the existing nodes with the customizations. Once completed, the reindex flag will be set to false again. This may take a few hours depending on number of assets in the system.

## Index existing content for map find and replace

This section consolidates the repeated **indexing** procedure used to enable the new **map-level find and replace** capabilities. 

**When you can skip indexing**

The source includes "skip" notes depending on your upgrade path (for example, "You need not perform these steps if you upgrade from 4.3.0 or 4.3.1," and similar notes). Follow the skip note stated in your upgrade section. 

Perform the following steps for indexing the existing content and use the new find and replace text at map level:

1. Run a POST request (with authentication):   

```http
POST http://<server:port>/bin/guides/map-find/indexing
```

Optional parameters supported in the source: 

- Index specific map paths (defaults to indexing all maps): 

    ```http
    POST http://<server:port>/bin/guides/map-find/indexing?paths=<map_path_in_repository>
    ```

- Index DITA maps under a root folder (and its subfolders): 

    ```http
    POST http://<server:port>/bin/guides/map-find/indexing?root=/content/dam/test
    ```

    >[!NOTE]
    >
    > If both `paths` and `root` are passed, only `paths` is considered. 

1. The API returns a `jobId`. To check status, send a GET request: 

    ```http
    GET http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}
    ```

    Expected completion behavior: 

    - On completion, GET responds with success and indicates if any maps failed. 
    - Confirm successfully indexed maps in server logs. 

### Ensure damAssetLucene indexing is complete (where applicable)

The source notes that damAssetLucene indexing can take hours depending on the data size, and you can confirm completion when `reindex` is `false` under: 

`http://<server:port>/oak:index/damAssetLucene` 

If you added customizations in `damAssetLucene`, you may need to apply them again after reindex completes. 

### Workaround for "query read or traversed more than 100000 nodes" (if the job fails)

If the indexing job fails and the error shows: 

"The query read or traversed more than 100000 nodes. To avoid affecting other tasks, processing was stopped." 

Try this workaround from the source:

1. In the `damAssetLucene` oak index, add boolean property `indexNodeName=true` in `/oak:index/damAssetLucene/indexRules/dam:Asset`.
2. Add a new node named `excerpt` under `/oak:index/damAssetLucene/indexRules/dam:Asset/properties` and set properties as shown in the source: 
    - `name=rep:excerpt` 
    - `propertyIndex=true` 
    - `notNullCheckEnabled=true` 
3.  Reindex `damAssetLucene` by setting `reindex=true` and wait until it becomes `false` again (may take hours). 
4.  Re‑run the indexing script again (repeat the POST and job tracking). 

## Post-process existing content for broken link report

This section consolidates the repeated **post‑processing** procedure used to enable the **broken link report**.

**When you can skip post-processing**

The source includes "skip" notes depending on your upgrade path (for example, "You need not perform these steps if you upgrade from 4.3.0," or "from 4.3.0 or 4.3.1"). Follow the skip note stated in your upgrade section. 

Perform the following steps to enable the broken link report:

1. (Optional) Increase Oak queryLimitReads for large repositories

    If there are more than **100,000 DITA files**, update `queryLimitReads` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` to a value greater than the number of assets (example: `200000`), redeploy, and proceed. 

    |PID|Property Key|Property Value|
    |---|---|---|
    |org.apache.jackrabbit.oak.query.QueryEngineSettingsService|queryLimitReads|Value: 200000 <br> Default Value: 100000|

1. Execute the following APIs to run post-processing on all the files:

    |End Point| /bin/guides/reports/upgrade|
    |---|---|
    |Request Type| **POST**  This script is a POST request hence should be executed via agents like Postman. |
    | Expected Response | The API will return a jobId. To check the status of the job, you can send a GET request with job id to the same end point.<br> Sample URL: `http://<server:port>/bin/guides/reports/upgrade`|

    |End Point| /bin/guides/reports/upgrade|
    |---|---|
    |Request Type| **GET** |
    |Param| jobId: Pass the jobId received from the previous post request.|
    |Expected Response | - Once the job is complete, the GET request responds with success. <br> - In case there are errors,  share the error logs along with API output with your customer success team.  <br>Sample URL: `http://<server:port>/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678` |

1. Revert back to the default or previous existing value of `queryLimitReads` if you have changed it in step 1.

## Enable trigger of script via a Servlet 

Several versions include an optional step to trigger a translation map upgrade job via a servlet. This section consolidates that repeated procedure and includes all details provided in the source. 


>[!NOTE]
>
> You need not perform these steps if you upgrade from 4.3.0 or 4.3.1.

POST:

```
http://localhost:4503/bin/guides/script/start?jobType=translation-map-upgrade
```

Response: 

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/translation-map-upgrade/1683190032886",
"status": "SCHEDULED"
}
```

In the above response JSON, the key `lockNodePath` holds the path to the node created in the repository pointing to the job submitted. It will automatically be deleted once the job is completed, till then, you can refer to this node for the current status of the job.

Look for `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` and `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` before proceeding to the next steps.

>[!NOTE]
>
> You should check if the node is still present and the status of the job.

**GET**: `http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json`


### Steps to handle the 'fmdita rewriter' conflict

Experience Manager Guides includes a custom Sling rewriter module (`fmditarewriter`) for handling links generated for cross‑map linking. 

If you have another custom Sling rewriter in your codebase: 

- Use an `order` value **greater than 50** because Guides uses `order=50`.
- During this upgrade, the `order` value changes from `1000` to `50`, so you must merge your existing custom rewriter (if any) with `fmditarewriter`. 

