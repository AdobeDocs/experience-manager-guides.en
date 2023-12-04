---
title: Release Notes | Upgrade instructions and fixed issues in Adobe Experience Manager Guides, June 2023 release
description: Learn about the bug fixes and how to upgrade to  June 2023 release of Adobe Experience Manager Guides as a Cloud Service
exl-id: df17ee33-9f50-4223-ab9f-a57a31097d22
---
# June 2023 release of Adobe Experience Manager Guides as a Cloud Service 

This release note covers the upgrade instructions, compatibility matrix, and issues fixed in version June 2023 of Adobe Experience Manager Guides (later referred as *AEM Guides as a Cloud Service*).

For more information about the new features and enhancements, see [What's new in June 2023 release of AEM Guides as a Cloud Service](whats-new-2023.6.0.md).

## Upgrade to June 2023 release

Upgrade your current AEM Guides as a Cloud Service setup by performing the following steps:

1. Check out the Cloud Services' Git code and switch to the branch configured in the Cloud Services pipeline corresponding to the environment that you want to upgrade.
2. Update `<dox.version>` property in `/dox/dox.installer/pom.xml` file of your Cloud Services Git code to 2023.6.297.
3. Commit the changes and run the Cloud Services pipeline to upgrade to the June 2023 release of AEM Guides as a Cloud Service.

## Steps to enable the trigger of a script via a servlet

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

In the previous response JSON, the key `lockNodePath` holds the path to the node created in the repository pointing to the job submitted. It will automatically be deleted once the job is completed, till then, you can refer to this node for the current status of the job.

Wait till this job is completed before proceeding to the next steps. 

>[!NOTE]
>
> You should check if the node is still present, and the status of the job.

```
GET
http://<aem_domain>/var/dxml/executor-locks/translation-map-upgrade/1683190032886.json
```

## Steps to post process the existing content to use the broken link report 

(Only if you are on a version prior to June 2023 release of AEM Guides as a Cloud Service)

Perform the following steps for post processing the existing content and using the new broken link report:

1. (Optional) If there are more than 100,000 dita files in the system, update the `queryLimitReads` under `org.apache.jackrabbit.oak.query.QueryEngineSettingsService` to a larger value (any value greater than the number of assets present, for example 200,000) and then redeploy.

    - Use the instructions given in *Configuration overrides* section in Install and configure Adobe Experience Manager Guides
as a Cloud Service, to create the configuration file. 
    - In the configuration file, provide the following (property) details to configure the queryLimitReads option:

        |PID|Property Key|Property Value|
        |---|---|---|
        |org.apache.jackrabbit.oak.query.QueryEngineSettingsService|queryLimitReads|Value: 200000 Default Value: 100000|

1.  Run a POST request to the server (with correct authentication) - `http://<server:port>//bin/guides/reports/upgrade`.

1.  The API will return a jobId. To check the status of the job, you can send a GET request with job id to the same end point - `http://<server:port>/bin/guides/reports/upgrade?jobId= {jobId}`
(For example: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42_678`)

1.  Once the job is complete, the previous GET request will respond with success. If job fails for some reason then failure can be seen from server logs.

1. Revert back to the default or previous existing value of `queryLimitReads` if you have changed it in step 1.

## Steps to index the existing content to use the new find and replace and topic list under the Reports tab: 

(Only if you are on a version prior to September 2022 release of AEM Guides as a Cloud Service)

Perform the following steps for indexing the existing content and use the new find and replace text at map level and topic list under the reports tab:

1.   Run a POST request to the server \(with correct authentication\) - `http://<server:port\>/bin/guides/map-find/indexing`. (Optional: You can pass specific paths of the maps to index them, by default all maps will be indexed \|\| For example : `https://<Server:port\>/bin/guides/map-find/indexing?paths=<map\_path\_in\_repository\>`)

1. You can also pass a root folder to index the DITA maps of a specific folder (and its subfolders). For example, `http://<server:port\>/bin/guides/map-find/indexing?root=/content/dam/test`. Note that if both the paths parameter and root parameter are passed, only the paths parameter is considered. 

1.   The API will return a jobId. To check the status of the job, you can send a GET request with job id to the same end point - `http://<server:port\>/bin/guides/map-find/indexing?jobId=\{jobId\}`\(For example: `http://localhost:8080/bin/guides/map-find/indexing?jobId=2022/9/15/7/27/7dfa1271-981e-4617-b5a4-c18379f11c42`\)


1.   Once the job is complete, the previous GET request will respond with success and mention if any maps failed. The successfully indexed maps can be confirmed from the server logs.

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by AEM Guides as a Cloud Service June 2023 release. 

### FrameMaker and FrameMaker Publishing Server

| AEM Guides as a Cloud Release| FMPS | FrameMaker |
| --- | --- | --- |
| 2023.06.0 | Not compatible | 2022 or higher |
| | | |


### Oxygen Connector

| AEM Guides as a Cloud Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac | 
| --- | --- | --- | --- | --- |
| 2023.06.0| 2.9-uuid-2 | 2.9-uuid-2 | 2.3 | 2.3 | 
|  |  |  |  |


## Fixed issues

The bugs fixed in various areas are listed below:

### Authoring

- Navtitle is removed from the content33 on switching from the layout view to the author or source view. (12174)
- Sometimes application error occurs on clicking a DITA map. (11842)
- Web Editor | Non-breaking space is added in XML Editor while editing a topic. (11786)
- Asset UI | In the List view, the overlayed available columns are not mergeable. (11528)
- Keyref is not resolved in the map view. (11490)
- Top menu does not appear when navigating through XML editor. (10868)
- `conref` in ph tag | The browse dialog shown is incorrect. (9481)
- Local links to other elements are not resolved in Web Editor. (8790)
- Matches() function do not work in schematron feature. (11224)


### Management

- Reports tab in the Web Editor UI doesn't display the topic list of old DITA maps created before the 4.2 upgrade. (11708)

- The Upload files button functionality in the Assets UI break in 4.2 release. (11633)

### Publishing

- Publishing to AEM site fails when reading temp files from pod that may have refreshed or restarted. (12113)
- Native PDF | Publishing content that has an output class with brackets() leads to a publishing freeze. (11936)
- JSON output | Map metadata having property value as `"value in spaces and double quotes"` leads to a publishing error. (11933)
- Web Editor | Output path and template cannot be selected in the AEM Preset. (11530) 
- Native PDF | Custom attributes are not propagated to temporary HTML or PDF engine. (DXML-12005)
- Native PDF |  Java OutOfMemoryError occurs on publishing large content. (11789)
- JSON output | The `fmUuid` property on the jcr:content node of JSON is different from the "id" inside the JSON. (11564)
- JSON Output | If the map and topic with same filename are present, JSON for the map is removed. (11524)
- Native PDF | Xref is printing the contents of href topic title instead of the Xref label. (11322)
- Native PDF | Unable to save the PDF template settings. (10751)
- Native PDF | The text extends beyond the column width on including multiple xrefs. (10876)
- Native PDF | `<note>``</note>` element does not generate extra span title of its type. (10549)
- Native PDF | The language metadata cannot be set in the generated PDF to comply with WCAG 2.0. (12296)



### Translation

- Post February cloud release (2302), all the translation content shows Out of Sync or Missing Copy. (11834)

### Review

- New Review UI | The conditions highlight, and show hide work differently than how they work in Web Editor. (11628)
