---
title: Configure the smart suggestions for authoring
description: Learn how to configure the smart suggestions for authoring
---
# Configure the smart suggestions for authoring

As an administrator, you can configure the Smart Suggestions feature for the authors. As the smart suggestion service is secured by Adobe IMS auth-based authentication integrate your environments with Adobe’s secure token-based authentication workflows and start using the new smart suggestion solution. The following configuration helps you to add AI configuration tab to folder profile. Once added, you can use the smart suggestions feature in the Web Editor.

## Create IMS configurations in Adobe Developer Console

Perform the following steps to create IMS configurations in Adobe Developer Console:
1. Launch [Adobe Developer Console](https://developer.adobe.com/console). 
1. After successfully logging in to Developer Console, you'll view the **Home** screen. The **Home** screen is where you can easily find information and quick links, including top-navigation links to Projects and Downloads.
1. To create a new empty project, select  **Create new project** from the  **Quick start** links.
![Quick start links](assets/conf-ss-quick-start.png) {width="550" align="left"}
*Create a new project.*

1. Select  **Add API**  from the  **Projects** screen.  The **Add an API** screen displays. This screen displays all available APIs, Events, and services for Adobe products and technologies with which you can develop applications.

1. Select the **IO Management API** to add it to your project.
![IO Management API](assets/confi-ss-io-management.png)
*Add IO Management API to your project.*

1. Create a new **OAuth credential** and save it.
![OAuth credential tile in configure API](assets/conf-ss-OAuth-credential.png) {width="3000" align="left"}
*Configure OAuth credential to your API.*

1. In the  **Projects** tab, select the newly created credentials.

1. Select the **OAuth Server-to-Server** link to view the credential details of your project.  

![connected credentials](assets/conf-ss-connected-credentials.png) {width="800" align="left"}
*Connect to the project to view the credential details.*
1. Copy the CLIENT_ID and CLIENT_SECRET keys.

You have now configured the OAuth authentication details. Keep these two keys handy as these are required in the next section.

### Add IMS configuration to the environment

Perform the following steps to add IMS configuration to the environment:

1. Open Experience Manager and then select your program  which contains the environment  you want to configure.
1. Switch to **Environments** tab.
1. Select the environment name which you want to configure. This should navigate you to the Environment Information page.
1. Switch to **Configuration** tab.
1. Add the CLIENT_ID and CLIENT_SECRET keys as shown in  the following screenshot. Make sure you are using the same names and configuration as highlighted below.
![Environment configuration](assets/conf-ss-environment.png) {width="800" align="left"}
*Add the environment configuration details.*




Once you have added the IMS configuration to the environment, perform the following steps to link these properties with AEM Guides using OSGi: 

1. In you cloud manager Git project code, add the below given two files (For file contents, view [Appendix](#appendix).

    * `com.adobe.fmdita.ims.service.ImsOauthUserAccountHeadersImpl.cfg.json`
    * `com.adobe.fmdita.smartsuggest.service.SmartSuggestConfigurationConsumer.cfg.json`
1. Ensure that the newly added files are getting covered by your `filter.xml`.
1. Commit and push your Git changes.
1. Run the pipeline to apply the changes on the environment.

Once this is done, you should be able to use the new microservice-based cloud publishing.



## Appendix {#appendix}

**File**: 
`com.adobe.fmdita.ims.service.ImsOauthUserAccountHeadersImpl.cfg.json`

**Content**:

```
{
  "client.id": "$[secret:CLIENT_ID]",
  "client.secret": "$[secret:CLIENT_SECRET]",
  "ims.url": "https://ims-na1.adobelogin.com"
}

```

**File**: `com.adobe.fmdita.smartsuggest.service.SmartSuggestConfigurationConsumer.cfg.json`

**Content**:

```
{
  "smart.suggestion.flag":true,
  "conref.inline.threshold":0.6,
  "conref.block.threshold":0.7,
  "emerald.url":"https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1",
  "instance.type":"prod"
}
```

## Smart Suggestion Configuration Details

|Key|Description|Allowed Values|
|---|---|---|
|smart.suggestion.flag|Controls whether smart suggestions is enabled or not|true/false|
|conref.inline.threshold|Threshold that controls precision/recall of suggestions fetched for the tag that the user is typing in currently.|-1.0 <= x <= 1.0|
|conref.block.threshold|Threshold that controls precision/recall of suggestions fetched for tags across the entire file.|-1.0 <= x <= 1.0|
|emerald.url|Endpoint for the Emerald vector database|[https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1](https://adobeioruntime.net/apis/543112-smartsuggest/emerald/v1)|
|instance.type|Type of the AEM instance. Make sure this is unique for each AEM instance smart suggestions is configured on. An use case would be to test the feature on stage environment with "instance.type" = "stage" while at the same time, the feature is also configured on "prod".|Any unique key identifying the environment "dev"/"stage"/"prod"/"test1"/"stage2"|

Once you have configured,  the smart suggesstions icon is displayed in the right panel of the Web Editor. You can view the list of smart suggestions when you edit your topics. For more details, view [AI based smart suggestions for authoring](../user-guide/web-editor-content-snippet.md).
