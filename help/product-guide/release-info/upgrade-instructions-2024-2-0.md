---
title: Release Notes | Upgrade instructions and fixed issues in Adobe Experience Manager Guides, February 2024 release
description: Learn about the compatibility matrix and how to upgrade to the February 2024 release of Adobe Experience Manager Guides as a Cloud Service.

---
# Upgrade instructions and compatibility matrix for the February 2024 release 

This article covers the upgrade instructions and the  compatibility matrix for February 2024 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the February 2024 release](whats-new-2024-2-0.md).

For the list of issues that have been fixed in this release, 
view [Fixed issues in the February 2024 release](fixed-issues-2024-2-0.md).



## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by February 2024 release of Experience Manager Guides as a Cloud Service. 

### FrameMaker and FrameMaker Publishing Server

| Experience Manager Guides as a Cloud Release| FMPS | FrameMaker |
| --- | --- | --- |
| 2024.02.0 | Not compatible | 2022 or higher |
| | | |


### Oxygen Connector

| Experience Manager Guides as a Cloud Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac | 
| --- | --- | --- | --- | --- |
| 2024.02.0|   3.1-uuid.17|   3.1-uuid.17 | 2.3 | 2.3 | 
|  |  |  |  |


### Knowledge base template version

|Components package name| Components version | Template version|
|---|---|---|
|Experience Manager Guides Components Content Package for Cloud Service|dxml-components.all-1.2.2| aem-site-template-dxml.all-1.0.15|

## Upgrade to February 2024 release

Upgrade your current Experience Manager Guides as a Cloud Service setup by performing the following steps:

1. Check out the Cloud Services' Git code and switch to the branch configured in the Cloud Services pipeline corresponding to the environment that you want to upgrade.
2. Update `<dox.version>` property in `/dox/dox.installer/pom.xml` file of your Cloud Services Git code to 2024.02.0.15.
3. Commit the changes and run the Cloud Services pipeline to upgrade to the February 2024 release of Experience Manager Guides as a Cloud Service.

## Steps to enable the trigger of a script via a servlet

(Only if you are on a version prior to the June 2023 release of Experience Manager Guides as a Cloud Service)

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

In the previous response JSON, the key `lockNodePath` holds the path to the node created in the repository pointing to the job submitted. It will automatically be deleted once the job is completed, then you can refer to this node for the status of the job.

Wait till this job is completed before proceeding to the next steps. 

>[!NOTE]
>
> You should check if the node is still present, and the status of the job.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Steps to post process the existing content to use the broken link report 

(Only if you are on a version prior to the June 2023 release of Experience Manager Guides as a Cloud Service)

Perform the following steps for post-processing the existing content and using the new broken link report:

1. (Optional) If there are more than 100,000 DITA files in the system, update the `queryLimitReads` and `queryLimitInMemory` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` to a larger value (any value greater than the number of assets present, for example 200,000) and then redeploy.

    - Use the instructions given in the *Configuration overrides* section in Install and configure Adobe Experience Manager Guides as a Cloud Service, to create the configuration file. 
    - In the configuration file, provide the following (property) details to configure the `queryLimitReads` and `queryLimitInMemory` option:

        |PID|Property Key|Property Value|
        |---|---|---|
        |org.apache.jackrabbit.oak.query.QueryEngineSettingsService|queryLimitReads|Value: 200000 Default Value: 100000|
        |org.apache.jackrabbit.oak.query.QueryEngineSettingsService|queryLimitInMemory|Value: 200000 Default Value: 100000|

1.  Run a POST request to the server (with correct authentication) - `http://<server>//bin/guides/reports/upgrade`.

1.  The API returns a jobId. To check the status of the job, you can send a GET request with job id to the same end point - `http://<server>/bin/guides/reports/upgrade?jobId= {jobId}`
(For example: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1.  Once the job is completed, the previous GET request responds with success. If the job fails for some reason, then failure can be seen from server logs.

1. Revert back to the default or previous existing value of `queryLimitReads` if you have changed it in step 1.

## Steps to index the existing content to use the new find and replace and topic list under the Reports tab: 

(Only if you are on a version prior to the June 2023 release of Experience Manager Guides as a Cloud Service)

Perform the following steps for indexing the existing content and use the new find and replace text at map level and topic list under the reports tab:

1. Run a POST request to the server (with correct authentication) - `http://<server:port>/bin/guides/map-find/indexing`. (Optional: You can pass specific paths of the maps to index them, by default all maps will be indexed|| For example : `https://<Server:port>/bin/guides/map-find/indexing?paths=<path of the MAP in repository>`)

1. The API will returns a jobId. To check the status of the job, you can send a GET request with job id to the same end point - `http://<server:port>/bin/guides/map-find/indexing?jobId={jobId}`(For example: `http://localhost:8080/bin/guides/reports/upgrade?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1. Once the job is completed, the previous GET request responds with success. If job fails for some reason then failure can be seen from server logs.

1. Revert back to default or previous existing value of queryLimitReads if you have changed it in step 1.

## Steps to handle the `'fmdita rewriter'` conflict

Experience Manager Guides has a [**custom sling rewriter**](../cs-install-guide/conf-output-generation.md#custom-rewriter) module for handling the links generated in case of cross-maps (links between the topics of two different maps).

If you have another custom sling rewriter in your codebase,  use an `'order'` value greater than 50, as Experience Manager Guides sling rewriter uses `'order'` 50.  To override this, you need a value >50. For more details, view [Output Rewriting Pipelines](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html).

During this upgrade, since the `'order'` value is changed from 1000 to 50, you need to merge the existing custom rewriter, if any, with `'fmdita-rewriter'`.



