---
title: Release Notes | Upgrade instructions and fixed issues in Adobe Experience Manager Guides, 2025.04.0 release
description: Learn about the compatibility matrix and how to upgrade to the 2025.04.0 release of Adobe Experience Manager Guides as a Cloud Service.
exl-id: 6e509216-63c9-4ede-988f-26b0df4313e2
---
# Upgrade instructions for the 2025.04.0 release 

This article covers the upgrade instructions and the compatibility matrix for the 2025.04.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2025.04.0 release](whats-new-2025-04-0.md).

For the list of issues fixed in this release, view [Fixed issues in the 2025.04.0 release](fixed-issues-2025-04-0.md).

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by the 2025.04.0 release of Experience Manager Guides as a Cloud Service. 

### FrameMaker and FrameMaker Publishing Server

| Experience Manager Guides as a Cloud Release| FMPS | FrameMaker |
| --- | --- | --- |
| 2025.04.0 | Not compatible | 2022 or higher |


### Oxygen Connector

| Experience Manager Guides as a Cloud Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac | 
| --- | --- | --- | --- | --- |
| 2025.04.0| 3.8 -uuid 1|   3.8 -uuid 1 | 2.3 | 2.3 | 


### Knowledge base template version

|Components package name| Components version | Template version|
|---|---|---|
|Experience Manager Guides Components Content Package for Cloud Service|guides-components.all-1.3.0| aem-site-template-dxml-1.0.17|


### New AEM Site template version

|Components version | Site version|
|---|---|
|guides-components.all-1.3.0| aemg-sites-template-1.2.0|


## Upgrade to 2025.04.0 release

Experience Manager Guides is upgraded automatically upon upgrading the current (latest) release of Experience Manager as a Cloud Service.

>[!NOTE]
>
> Once you start using the current (latest) release, compare any overridden configurations with the latest ones to get the latest features:
>- ui_config.json (may have been set in folder profiles)


Perform the following steps for Experience Manager Guides as a Cloud Service if you haven't done it earlier for your existing release:

### Steps to enable the trigger of a script via a servlet

(Only if you are on a release before the June 2023 release of Experience Manager Guides as a Cloud Service)

After you complete the installation, you can choose to HIT the trigger to start the translation job:

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

In the previous response JSON, the key `lockNodePath` holds the path to the node created in the repository pointing to the job submitted. It is automatically deleted once the job is completed, then you can refer to this node for the status of the job.

Wait till this job is completed before proceeding to the next steps. 

>[!NOTE]
>
> You should check if the node is still present, and the status of the job.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

### Steps to post process the existing content to use the broken link report 

(Only if you are on a release before the June 2023 release of Experience Manager Guides as a Cloud Service)

Perform the following steps for post-processing the existing content and using the new broken link report:

1. (Optional) If there are more than 100,000 DITA files in the system, update the `queryLimitReads` and `queryLimitInMemory` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` to a larger value (any value greater than the number of assets present, for example 200,000) and then redeploy.

    - Use the instructions given in the *Configuration overrides* section in Install and configure Adobe Experience Manager Guides as a Cloud Service, to create the configuration file. 
    - In the configuration file, provide the following (property) details to configure the `queryLimitReads` and `queryLimitInMemory` option:

        |PID|Property Key|Property Value|
        |---|---|---|
        |org.apache.jackrabbit.oak.query.QueryEngineSettingsService|queryLimitReads|Value: 200000 Default Value: 100000|
        |org.apache.jackrabbit.oak.query.QueryEngineSettingsService|queryLimitInMemory|Value: 200000 Default Value: 100000|

1. Run a POST request to the server (with correct authentication) - `http://<server>//bin/guides/reports/upgrade`.

1. The API returns a jobId. To check the status of the job, you can send a GET request with job id to the same end point - `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(For example: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Once the job is completed, the previous GET request responds with success. If the job fails for some reason, then the failure can be seen from server logs.

1. Revert back to the default or previous existing value of `queryLimitReads` if you have changed it in step 1.

### Steps to index the existing content to use the new find and replace and topic list under the Reports tab: 

(Only if you are on a release before the June 2023 release of Experience Manager Guides as a Cloud Service)

Perform the following steps for indexing the existing content and use the new find and replace text at map level and topic list under the reports tab:

1. Run a POST request to the server (with correct authentication) - `http://<server:port>/bin/guides/map-find/indexing`. (Optional: You can pass specific paths of the maps to index them, by default all maps are indexed|| Example : `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. You can also pass a root folder to index the DITA maps of a specific folder (and its subfolders). For example, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Note that if both the paths parameter and root parameter are passed, only the paths parameter is considered.

1. The API returns a jobId. To check the status of the job, you can send a GET request with job id to the same end point - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(For example: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Once the job is completed, the previous GET request responds with success and mention if any maps failed. The successfully indexed maps can be confirmed from server logs.

### Steps to handle the `'fmdita rewriter'` conflict

Experience Manager Guides has a [**custom sling rewriter**](../cs-install-guide/conf-output-generation.md#custom-rewriter) module for handling the links generated in case of cross-maps (links between the topics of two different maps).

If you have another custom sling rewriter in your codebase, use an `'order'` value greater than 50, as Experience Manager Guides sling rewriter uses `'order'` 50. To override this, you need a value >50. For more details, view [Output Rewriting Pipelines](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

During this upgrade, since the `'order'` value is changed from 1000 to 50, you need to merge the existing custom rewriter, if any, with `fmdita-rewriter`.

### Steps to perform B-Tree migration for Content Fragments

If references are not displayed for content fragments, you can choose to HIT the trigger to start the migration job:

POST: 

```
http://localhost:4503/bin/guides/script/start?jobType=cf-reference-store-btree-migration

```


Response:

```
{
"msg": "Job is successfully submitted and lock node is created for future reference",
"lockNodePath": "/var/dxml/executor-locks/cf-reference-store-btree-migration/1683190032886",
"status": "SCHEDULED"
}
```

In the previous response, JSON, the key `lockNodePath` holds the path to the node created in the repository, which points to the job submitted. It will automatically be deleted once the job is completed. You can refer to this node for the status of the job.

Wait till this job is completed before proceeding to the next steps.

>[!NOTE] 
>
>You should check if the node is still present, and the status of the job.

GET: 

```
http://<aem_domain>/var/dxml/executor-locks/cf-reference-store-btree-migration/1683190032886.json
```
