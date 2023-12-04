---
title: Upgrade Adobe Experience Manager Guides
description: Learn how to Upgrade Adobe Experience Manager Guides
exl-id: f058b39f-7408-4874-942b-693e133886cf
---
# Upgrade Adobe Experience Manager Guides {#id224MBE0M0XA}

>[!NOTE]
>
> Follow the upgrade instructions specific to the licensed version of your product.

You can upgrade your current version of Experience Manager Guides to version 4.3.1

- If you are using version 4.3.0, 4.2, or 4.2.1, then you can directly upgrade to version 4.3.1.
- If you are using version 4.1 or 4.1.x then you need to upgrade to version 4.3.0, 4.2 or 4.2.x before upgrading to version 4.3.1.
- If you are using version 4.0 you need to upgrade to version 4.2 before upgrading to version 4.3.1.
- If you are using version 3.8.5, you need to upgrade to version 4.0 before upgrading to version 4.2.
- If you are on a version prior to 3.8.5, refer to the Upgrade Experience Manager Guides section in the product-specific installation guide.


>[!NOTE]
>
> You must install AEM service pack before upgrading Experience Manager Guides version.

For more details, refer to the following procedures:

-   [Upgrade from 3.8.5 to version 4.0](#id2256DK003E1)
-   [Upgrade to version 4.2](#id22A3F500SXA)
-   [Upgrade to version 4.2.1](#upgrade-version-4-2-1)
-   [Upgrade to version 4.3.0](#upgrade-version-4-3)
-   [Upgrade to version 4.3.1](#upgrade-version-4-3-1)


>[!IMPORTANT]
>
> Before you begin to upgrade, take a complete system backup to avoid any loss of data.

## Upgrade from version 3.8.5 to version 4.0 {#id2256DK003E1}

If you are using Experience Manager Guides version 3.8.5, then you can upgrade to version 4.0 of Experience Manager Guides. With the upgrade feature, you don't have to uninstall the previous version of Experience Manager Guides.

Before running the process there are certain tasks that you must complete. The following sub-sections will walk you through the prerequisites, report generation, and migration process. Also, after you install Experience Manager Guides version 4.0 you may customize various configurations, according to the customer settings.

>[!NOTE]
>
> This Upgrade process is applicable only from version 3.8.5 to version 4.0. For the process to upgrade from version 3.4 or higher to 3.8.5, refer to the *Upgrade Experience Manager Guides* section in the product-specific installation guide available in the [Help Archival Page](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html).

****Prerequisites****

Before you start the Experience Manager Guides upgrade process, ensure that you have:

1.  Imported the review comments in topics open for review.
1.  Closed all active reviews.
1.  Closed all translation tasks.
1.  Uninstall any Experience Manager Guides hot fixes installed on the top of the previous version \(major or patch release\) of Experience Manager Guides.

**Before you install version 4.0**

Before you install version 4.0, perform the following steps:

1.  Ensure at this point Experience Manager Guides is on version 3.8.5.
1.  Download the upgrade script package. To do so, search for "XML Documentation solution 4.0 Upgrade Package" on [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html) which will download a zip file.
1.  Upload this package to AEM via Package Manager and install this package.
1.  Once the upgrade package is installed, run the below given scripts in the same order and follow the given instructions:

**Check upgrade compatibility API**

This API is designed to assess the current system status and report if the upgrade is possible or not. To run this script, trigger the below given endpoint:

|End Point|/bin/dxml/upgrade/3xto4x/report|
| --- | --- |
|Request Type|**GET** You can use a web browser, where you are logged in to the AEM instance as an administrator.|
|Expected Response|-   In case all required nodes can be moved, you will get a passed check. <br>-   In case a node is present at the target location, you will get a relevant error. Clean up the repository \(delete node /var/dxml\) and reinstall the upgrade package and then trigger this endpoint again. <br>**Note:** This is not a common error as the target location is not used earlier by 3.x Experience Manager Guides. <br> -   If this script does not succeed, do not proceed and report to your customer success team.|

**System data migration API**

This API is designed to migrate the system data as mentioned in the **Migration Mapping** section.

1.  Do not execute this script if the Check upgrade compatibility API fails \(do not proceed\).
1.  Once the Check upgrade compatibility API returns success, you can run the upgrade script.

|End Point|/bin/dxml/upgrade/3xto4x|
| --- | --- |
|Request Type|**POST** This script is a POST request hence should be executed via agents like Postman.|
|Expected Response|-   Once the migration is successful, you can install XML Documentation solution version 4.0.<br>-   In case there are errors, restore to the last checkpoint and share the error logs along with API output with your customer success team.|

**Migration Mapping**: The above API migrates all the data under the source location to the target location.

|Source|Target|
|------|------|
|/content/fmdita|/var/dxml|
|/content/dxml|/var/dxml|
|/etc/fmdita|/libs/fmdita|

## Install version 4.0 {#id23598G006XA}

1.  Install version 4.0 only if the upgrade steps were successful.
1.  Download 4.0 version package from [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html):

    -   If you are using UUID version of software, search for "4.0 UUID Release for XML Documentation solution for AEM 6.5."
    -   If you are using Non-UUID version of software, search for "4.0 Non-UUID Release for XML Documentation solution for AEM 6.5."
    Upload the package to the existing AEM server instance\(s\) using CRX Package Manager and install it.

    >[!NOTE]
    >
    > Wait for all system components to start.

1.  Clear the browser cache after installing the package.
1.  If a dispatcher is configured on AEM Author instance, perform the following steps:
    -   Ensure the following are handled in dispatcher rules:
    -   The URL pattern /home/users/\*/preferences is whitelisted.
    -   The URL pattern /libs/cq/security/userinfo.json is not cached.
1.  Clear dispatcher cache \(to clear any `clientlibs` cached\).

## Upgrade to version 4.2 {#id22A3F500SXA}

Upgrading to version 4.2 depends on the current version of Experience Manager Guides.

If you are using version 4.0, 4.1 or 4.1.x, then you can directly upgrade to version 4.2.

****Prerequisites****

Before you start the Experience Manager Guides 4.2 upgrade process, ensure that you have:

1.  Upgraded to Experience Manager Guides version 4.0, 4.1 or 4.1.x.
1.  Closed all translation tasks.
1.  Changed the log level to **INFO** for `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` class and append these logs in a new log file, for example, `logs/translation_upgrade.log.`

>[!NOTE]
>
> You should close all active reviews. If the review tasks are not closed while upgrading to 4.2, the older in-progress review tasks keep taking users on the older review pages, and the review tasks created after the upgrade will display the latest updates in the functionality.

## Install version 4.2 {#id2245IK0E0EV}

1.  Download 4.2 version package from [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1.  Install version 4.2 package.
1.  After you complete the package installation, wait for the following message\(s\) in the logs:

    `Completed the post deployment setup script`

    The above message indicates that all the steps of installation are complete.

    In case you encounter any of the following ERROR prefixes, report them to your customer success team:

    -   Error in post deployment setup script
    -   Exception while porting the translation MAP
    -   Unable to port translation map from v1 to v2 for property
1.  Upgrade Oxygen connector plugin released with version 4.2 \(if needed\).
1.  Clear the browser cache after installing the package.
1.  Continue upgrading the customizations as detailed out in the next section.

## After you install version 4.2 {#id2326F02004K}

>[!IMPORTANT]
>
> Hi-tech template is not displayed on upgraded server. To include the hi-tech template on your server you can copy it: Source: /libs/fmdita/pdf/Hi-Tech Destination: /content/dam/dita-templates/pdf

After you install Experience Manager Guides, you may merge the various configurations applicable from the newly installed version to your setup.

>[!NOTE]
>
> The dam-update-asset model may be customized. So, if any customizations have been done, then we need to sync the customizations and Experience Manager Guides into the working copy of the model.

1.  **DAM Update Asset workflow \(Post-processing changes\):**

1.  Open URL:

    ```http
    http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
    ```

1.  Select **DAM Update Asset workflow**.
1.  Click on **Edit**.
1.  If the **DXML Post Process Initiator** component is present, ensure that the customizations are synced.
1.  If the **DXML Post Process Initiator** component is absent, perform the following steps to insert it:

1.  Click **Insert component** \(Responsible for Experience Manager Guides post-processing as the final step in the process\).
1.  Configure the **Process step** with below details:

    **Common tab**

    **Title:** DXML Post Process Initiator

    **Description**: DXML post process initiator step which will trigger a sling job for DXML post-processing of the modified/created asset

    **Process tab**

    - Select **DXML Post Process Initiator**from the **Process** drop down

    - Select **Handler Advance**

    - Select **Done**

1.  Click **Sync** on the top right after completing the changes. You will receive a success notification.

    >[!NOTE]
    >
    > Refresh and verify that customized changes and the Experience Manager Guides post-processing step is present in the final workflow model.

1.  Once **DAM Update Asset workflow**is validated, check corresponding launcher configurations. To do so, go to AEM Workflow interface and open launchers.

    ```http
    http://localhost:4502/libs/cq/workflow/content/console.html
    ```

    Find and make changes \(if necessary\) to the following two launchers \(that should be active\) corresponding to **DAM Update Asset workflow**:

1.  Launcher for "*Node Created*" for **DAM Update Asset workflow**- for condition `"jcr:content/jcr:mimeType!=video"`, the 'Globbing' value should be:

    ```json
    /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
    ```

    -   'excludeList' should have `"event-user-data:changedByWorkflowProcess"`.
    -   Launcher for "*Node Modified*" for **DAM Update Asset workflow -** for condition "`jcr:content/jcr:mimeType!=video`",
    -   the 'Globbing' value should be:

    ```json
    /content/dam(/((?!/subassets|/translation_output).)*/)renditions/original
    ```

    -   'excludeList' should have `"event-user-data:changedByWorkflowProcess"`.
1.  Once the upgrade is complete, ensure any of the customizations/overlays are validated and updated to match the new application code. Some examples are given below:
    -   Any components overlayed from/libs/fmditaor/libsshould be compared with the new product code and updates should be done in overlayed files under/apps.
    -   Any clientlib categories used from product, should be reviewed for changes. Any overridden configurations \(examples below\) should be compared with the latest ones so as to get the latest features:
    -   elementmapping.xml
    -   ui\_config.json\(may have been set in folder profiles\)
    -   amended `com.adobe.fmdita.config.ConfigManager`
    -   Check if any of the custom code was using any old paths \(as mentioned in the [Migration Mapping](#id2244LE040XA) section\) - should be updated to the new paths so that the customizations also work as expected.
1.  Read about any new configurations brought in the current release \(check [Release Notes](../release-info/release-notes-4.3.md)\) and see if any functionality is impacted then take appropriate action. An example could be to make use of "Improved file and version handling" introduced in version 4.0, for which you need to enable a configuration.

## Steps to index the existing content to use the new find and replace: 

Perform the following steps for indexing the existing content and use the new find and replace text at map level:

-   Run a POST request to the server \(with correct authentication\) - `http://<server:port\>/bin/guides/map-find/indexing`. \(Optional: You can pass specific paths of the maps to index them, by default all maps will be indexed \|\| For example : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`\)

-   The API will return a jobId. To check the status of the job, you can send a GET request with job id to the same end point -

 `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(For example: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)

-   Once the job is complete, the above GET request will respond with success and mention if any maps failed. The successfully indexed maps can be confirmed from the server logs.

If the upgrade job fails and the error log shows the following error:

  "The *query* read or traversed more than *100000 nodes*. To avoid affecting other tasks, processing was stopped."

This could happen because the index is not properly set up for the query used in the upgrade. You can try the following workaround:

1. In the damAssetLucene  oak index, add the boolean property `indexNodeName` as `true` in the node.
`/oak:index/damAssetLucene/indexRules/dam:Asset`
1. Add a new node with the name excerpt under the node.

    `/oak:index/damAssetLucene/indexRules/dam:Asset/properties`
and set the following properties in the node:

    ```
    name - rep:excerpt
    propertyIndex - {Boolean}true
    notNullCheckEnabled - {Boolean}true
    ```

    The structure of `damAssetLucene` should look something like:

    ```
    <damAssetLucene compatVersion="{Long}2" async="async, nrt" jcr:primaryType="oak:QueryIndexDefinition" evaluatePathRestrictions="{Boolean}true" type="lucene">
    <indexRules jcr:primaryType="nt:unstructured">
      <dam:Asset indexNodeName="{Boolean}true" jcr:primaryType="nt:unstructured">
        <properties jcr:primaryType="nt:unstructured">
          <excerpt name="rep:excerpt" propertyIndex="{Boolean}true" jcr:primaryType="nt:unstructured" notNullCheckEnabled="{Boolean}true"/>
        </properties>
        </dam:Asset>
      </indexRules>
    </damAssetLucene>    
    ```


    (along with other existing nodes and properties)

1. Reindex the `damAssetLucene` index (by setting the reindex flag as `true` under
and wait for it to be `false` again (this indicates the reindexing is complete). Note that it may take a few hours depending on size of the index.
1. Run the indexing script again by performing the previous steps.


## Upgrade to version 4.2.1 {#upgrade-version-4-2-1}

Upgrading to version 4.2.1 depends on the current version of Experience Manager Guides.

If you are using version 4.1 or 4.1.x, or 4.2 then you can directly upgrade to version 4.2.1.

>[!NOTE]
>
>The post-processing and indexing may take a few hours. We recommend you to start the upgrade process during the off-peak hours.

****Prerequisites****

Before you start the Experience Manager Guides 4.2.1 upgrade process, ensure that you have:

1.  Upgraded to Experience Manager Guides version 4.1, 4.1.x, or 4.2.
1.  Closed all translation tasks.
1.  Changed the log level to **INFO** for `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` class and append these logs in a new log file, for example, `logs/translation_upgrade.log.`

>[!NOTE]
>
> You should close all active reviews. If the review tasks are not closed while upgrading to 4.2, the older in-progress review tasks keep taking users on the older review pages, and the review tasks created after the upgrade will display the latest updates in the functionality.

## Install version 4.2.1 

1.  Download 4.2.1 version package from [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1.  Install version 4.2.1 package.
1. You can choose to HIT the trigger to start the translation map upgrade job. For details, see [Enable trigger of script via a Servlet](#enable-trigger-serverlet).


1.  After you complete the package installation, wait for the following message\(s\) in the logs:

    `Completed the post deployment setup script`

    The above message indicates that all the steps of installation are complete.

    In case you encounter any of the following ERROR prefixes, report them to your customer success team:

    -   Error in post deployment setup script
    -   Exception while porting the translation MAP
    -   Unable to port translation map from v1 to v2 for property
1.  Upgrade Oxygen connector plugin released with version 4.2 \(if needed\).
1.  Clear the browser cache after installing the package.
1.  Continue upgrading the customizations as detailed out in the next section.

### Enable trigger of script via a Servlet{#enable-trigger-serverlet}

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

Sample log:
The following is a sample of logs that will appear in the log file after you trigger the script. 

```
04.05.2023 14:17:12.876 *INFO* [[0:0:0:0:0:0:0:1] [1683190032736] POST /bin/guides/script/start HTTP/1.1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Acquiring lock for job : translation-map-upgrade
04.05.2023 14:17:12.897 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Starting the thread to upgrade translation map from V1 to V2
04.05.2023 14:17:12.899 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Initiating lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.901 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Starting porting of translation map from V1 to V2
04.05.2023 14:17:12.904 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Memory increase is of : 764 kB
04.05.2023 14:17:12.906 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2
04.05.2023 14:17:12.907 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Releasing lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.909 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2
```

Look for `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` and `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` before proceeding to the next steps.



## After you install version 4.2.1 

>[!IMPORTANT]
>
> Hi-tech template is not displayed on upgraded server. To include the hi-tech template on your server you can copy it: Source: /libs/fmdita/pdf/Hi-Tech Destination: /content/dam/dita-templates/pdf

After you install Experience Manager Guides, you may merge the various configurations applicable from the newly installed version to your setup.

>[!NOTE]
>
> The dam-update-asset model may be customized. So, if any customizations have been done, then we need to sync the customizations and Experience Manager Guides into the working copy of the model.

1.  **DAM Update Asset workflow \(Post-processing changes\):**

1.  Open URL:

    ```http
    http://localhost:4502/libs/cq/workflow/admin/console/content/models.html
    ```

1.  Select **DAM Update Asset workflow**.
1.  Click on **Edit**.
1.  If the **DXML Post Process Initiator** component is present, ensure that the customizations are synced.
1.  If the **DXML Post Process Initiator** component is absent, perform the following steps to insert it:

1.  Click **Insert component** \(Responsible for Experience Manager Guides post-processing as the final step in the process\).
1.  Configure the **Process step** with below details:

    **Common tab**

    **Title:** DXML Post Process Initiator

    **Description**: DXML post process initiator step which will trigger a sling job for DXML post-processing of the modified/created asset

    **Process tab**

    - Select **DXML Post Process Initiator**from the **Process** drop down

    - Select **Handler Advance**

    - Select **Done**

1.  Click **Sync** on the top right after completing the changes. You will receive a success notification.

    >[!NOTE]
    >
    > Refresh and verify that customized changes and the Experience Manager Guides post-processing step is present in the final workflow model.

1.  Once **DAM Update Asset workflow**is validated, check corresponding launcher configurations. To do so, go to AEM Workflow interface and open launchers.

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

1.  Once the upgrade is complete, ensure any of the customizations/overlays are validated and updated to match the new application code. Some examples are given below:
    -   Any components overlayed from/libs/fmditaor/libsshould be compared with the new product code and updates should be done in overlayed files under/apps.
    -   Any clientlib categories used from product, should be reviewed for changes. Any overridden configurations \(examples below\) should be compared with the latest ones so as to get the latest features:
    -   elementmapping.xml
    -   ui\_config.json\(may have been set in folder profiles\)
    -   amended `com.adobe.fmdita.config.ConfigManager`
    -   Check if any of the custom code was using any old paths \(as mentioned in the [Migration Mapping](#id2244LE040XA) section\) - should be updated to the new paths so that the customizations also work as expected.
1.  Read about any new configurations brought in the current release \(check [Release Notes](../release-info/release-notes-4.2.1.md)\) and see if any functionality is impacted then take appropriate action. An example could be to make use of "Improved file and version handling" introduced in version 4.0, for which you need to enable a configuration.

## Steps to index the existing content to use the new find and replace: 

Perform the following steps for indexing the existing content and use the new find and replace text at map level:

-   Ensure that the `damAssetLucene` indexing has been completed. It can take upto a few hours, depending on the amount of data present on the server. You can confirm that the reindexing is completed by checking that the reindex field is set as false in 
`http://<server:port>/oak:index/damAssetLucene`.  Also, if you have added any customizations in `damAssetLucene`, you may need to apply them again.

-   Run a POST request to the server \(with correct authentication\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Optional: You can pass specific paths of the maps to index them, by default all maps will be indexed \|\| For example : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

- You can also pass a root folder to index the DITA maps of a specific folder (and its subfolders). For example, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Note that if both the paths parameter and root parameter are passed, only the paths parameter is considered. 

-   The API will return a jobId. To check the status of the job, you can send a GET request with job id to the same end point - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(For example: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


-   Once the job is complete, the above GET request will respond with success and mention if any maps failed. The successfully indexed maps can be confirmed from the server logs.


## Upgrade to version 4.3.0 {#upgrade-version-4-3} 

Upgrading to version 4.3.0 depends on the current version of Experience Manager Guides. If you are using version 4.2 or 4.2.x then you can directly upgrade to version 4.3.0.

>[!NOTE]
>
>The post-processing and indexing may take a few hours. We recommend you to start the upgrade process during the off-peak hours.

****Prerequisites****

Before you start the Experience Manager Guides 4.3.0 upgrade process, ensure that you have:

1.  Upgraded to Experience Manager Guides version 4.2 or 4.2.x and completed their respective installation step.
1.  Closed all translation tasks.



## Install version 4.3.0

1. Download 4.3.0 version package from [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Install version 4.3.0 package.
1. Clear the browser cache after installing the package.
1. Upgrade the `ui_config.json` file from the **XML Editor Configuration** tab in the Folder Profile.


## After you install version 4.3.0

After you install Experience Manager Guides, you may merge the various configurations applicable from the newly installed version to your setup.

## Steps to post process the existing content to use the broken link report 


Perform the following steps for post processing the existing content and using the new broken link report:

1. (Optional) If there are more than 100,000 dita files in the system, update the `queryLimitReads` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` to a larger value (any value greater than the number of assets present, for example 200,000) and then redeploy.

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


4.3.1

## Upgrade to version 4.3.1 {#upgrade-version-4-3-1} 

Upgrading to version 4.3.1 depends on the current version of Experience Manager Guides. If you are using version 4.3.0, 4.2, or 4.2.1 then you can directly upgrade to version 4.3.1.

>[!NOTE]
>
>The post-processing and indexing may take a few hours. We recommend you to start the upgrade process during the off-peak hours.

****Prerequisites****

Before you start the Experience Manager Guides 4.3.1 upgrade process, ensure that you have:

1.  Upgraded to Experience Manager Guides version 4.3.0, 4.2, or 4.2.1 and completed their respective installation step.
1.  Closed all translation tasks.
1. Changed the log level to **INFO** for `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript` class and append these logs in a new log file, for example, `logs/translation_upgrade.log`.


## Install version 4.3.1

1. Download 4.3.1 version package from [Adobe Software Distribution Portal](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
1. Install version 4.3.1 package.
1. You can choose to HIT the trigger to start the translation map upgrade job. For details, see [Enable trigger of script via a Servlet](#enable-trigger-serverlet-4-3-1).


1.  After you complete the package installation, wait for the following message\(s\) in the logs:

    `Completed the post deployment setup script`

    The above message indicates that all the steps of installation are complete.

    In case you encounter any of the following ERROR prefixes, report them to your customer success team:

    -   Error in post deployment setup script
    -   Exception while porting the translation MAP
    -   Unable to port translation map from v1 to v2 for property
1.  Upgrade Oxygen connector plugin released with version 4.2 \(if needed\).
1.  Clear the browser cache after installing the package.
1.  Continue upgrading the customizations as detailed out in the next section.

### Enable trigger of script via a Servlet{#enable-trigger-serverlet-4-3-1}

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

Sample log:
The following is a sample of logs that will appear in the log file after you trigger the script. 

```
04.05.2023 14:17:12.876 *INFO* [[0:0:0:0:0:0:0:1] [1683190032736] POST /bin/guides/script/start HTTP/1.1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Acquiring lock for job : translation-map-upgrade
04.05.2023 14:17:12.897 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Starting the thread to upgrade translation map from V1 to V2
04.05.2023 14:17:12.899 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Initiating lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.901 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Starting porting of translation map from V1 to V2
04.05.2023 14:17:12.904 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Memory increase is of : 764 kB
04.05.2023 14:17:12.906 *INFO* [pool-59-thread-1] com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2
04.05.2023 14:17:12.907 *INFO* [pool-59-thread-1] com.adobe.dxml.common.executor.RunnableSynchronizedOTS Releasing lock for node : /var/dxml/executor-locks/translation-map-upgrade/1683190032886
04.05.2023 14:17:12.909 *INFO* [pool-59-thread-1] com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2
```

Look for `com.adobe.fmdita.translationservices.TranslationMapUpgradeScript Completed porting of translation map from V1 to V2` and `com.adobe.fmdita.xmltranslation.ots.TranslationMapUpgradeOTS Completed the thread to upgrade translation map from V1 to V2` before proceeding to the next steps.

## After you install version 4.3.1 



After you install Experience Manager Guides, you may merge the various configurations applicable from the newly installed version to your setup.

>[!NOTE]
>
> The dam-update-asset model may be customized. So, if any customizations have been done, then we need to sync the customizations and Experience Manager Guides into the working copy of the model.

1.  **DAM Update Asset workflow \(Post-processing changes\):**

1.  Open URL:

    ```
    http://localhost:4502/libs/cq/workflow/admin/console/content/models.html 
    ```

1.  Select **DAM Update Asset workflow**.
1.  Click on **Edit**.
1.  If the **DXML Post Process Initiator** component is present, ensure that the customizations are synced.
1.  If the **DXML Post Process Initiator** component is absent, perform the following steps to insert it:

1.  Click **Insert component** \(Responsible for Experience Manager Guides post-processing as the final step in the process\).
1.  Configure the **Process step** with below details:

    **Common tab**

    **Title:** DXML Post Process Initiator

    **Description**: DXML post process initiator step which will trigger a sling job for DXML post-processing of the modified/created asset

    **Process tab**

    - Select **DXML Post Process Initiator**from the **Process** drop down

    - Select **Handler Advance**

    - Select **Done**

1.  Click **Sync** on the top right after completing the changes. You will receive a success notification.

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

1.  Once the upgrade is complete, ensure any of the customizations/overlays are validated and updated to match the new application code. Some examples are given below:
    -   Any components overlayed from/libs/fmditaor/libsshould be compared with the new product code and updates should be done in overlayed files under/apps.
    -   Any clientlib categories used from product, should be reviewed for changes. Any overridden configurations \(examples below\) should be compared with the latest ones so as to get the latest features:
    -   elementmapping.xml
    -   ui\_config.json\(may have been set in folder profiles\)
    -   amended `com.adobe.fmdita.config.ConfigManager`


## Steps to index the existing content

>[!NOTE]
>
> You need not perform these steps if you upgrade from 4.3.0 or 4.2.1.

Perform the following steps for indexing the existing content and use the new find and replace text at map level:


-   Run a POST request to the server \(with correct authentication\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Optional: You can pass specific paths of the maps to index them, by default all maps will be indexed \|\| For example : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)


-   The API will return a jobId. To check the status of the job, you can send a GET request with job id to the same end point - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(For example: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


-   Once the job is complete, the above GET request will respond with success and mention if any maps failed. The successfully indexed maps can be confirmed from the server logs.
  
## Steps to post process the existing content to use the broken link report 

>[!NOTE]
>
> You need not perform these steps if you upgrade from 4.3.0

Perform the following steps for post processing the existing content and using the new broken link report:

1. (Optional) If there are more than 100,000 dita files in the system, update the `queryLimitReads` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` to a larger value (any value greater than the number of assets present, for example 200,000) and then redeploy.

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



**Parent topic:**[Download and install](download-install.md)
