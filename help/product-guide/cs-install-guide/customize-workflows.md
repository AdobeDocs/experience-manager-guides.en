---
title: Configure and customize workflows
description: Learn how to Configure and customize workflows
exl-id: a5742082-cc0b-49d9-9921-d0da1b272ea5
feature: Workflow Configuration
role: Admin
level: Experienced
---
# Configure and customize workflows {#id181AI0OJ0RO}

Workflows enable you to automate Adobe Experience Manager \(AEM\) activities. A workflow consists of a series of steps that are executed in a specific order. You can define a distinct activity to execute on each step. For example, you can send an email notification to all reviewers in a group when a topic review is created. Or, send a notification to the publisher when an output generation task completes.

For more information about workflows in AEM, see:

-   [Administering Workflow Instances](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/workflows-administering.html)

-   Applying and participating in workflows: [Working with Project Workflows](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/authoring/projects/workflows.html).


The sections in this topic will walk you through various customizations that you can make in the default workflows shipped in the AEM Guides.

## Customize review workflow {#id176NE0C00HS}

Every organization's content authoring team works in a specific way to meet their business requirements. In some organizations there is a dedicated editor, whereas some other organization could have automated editorial review system in place. For example, in an organization a typical authoring and publishing workflow could include tasks like - whenever an author is done with authoring content, it automatically goes to the reviewers, and when the review is complete it goes to the publisher for generating the final output. In AEM, activities that you do on your content and assets can be combined in the form of a process and mapped to an AEM workflow. For more information about workflows in AEM, see [Administering Workflows](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/workflows-administering.html) in AEM documentation.

AEM Guides allows you to customize the default review workflow. You can use the following four custom review-related processes with your other authoring or publishing workflows.

-   **Create Review**: This process prepares the metadata required to create a review task. For example, it will assign review permission to the reviewers, set the status of the topics to under review, set the review timelines, and more. Out of the four processes, this is the only mandatory process that must be included in your custom workflow. In your workflow, you may choose to include or exclude the other three processes.

-   **Assign Review Task**: This process creates the review task and sends the task notification to the initiator and reviewers.

-   **Send Review Email**: This process sends the review email to the initiator and reviewers.

-   **Schedule Job to Close Review**: This process ensures that the review process completes on reaching the deadline.


When you are creating a custom review workflow, the first task is to set the required metadata needed by the Create Review process. To do so, you can create an ECMA script. A sample of the ECMA script that assigns the metadata is given below for both topic as well as map.

**For Topic**

```javascript
var workflowdata=workItem.getWorkflowData();
workflowdata.getMetaDataMap().put("initiator","admin");
workflowdata.getMetaDataMap().put("operation","AEM_REVIEW");
workflowdata.getMetaDataMap().put("orgTopics","/content/dam/xml-solution/review.xml");
workflowdata.getMetaDataMap().put("payloadJson","{\"base\":\"/content/dam/xml-solution\",\"asset\":[\"/content/dam/xml-solution/review.xml\"],\"referrer\":\""}");
workflowdata.getMetaDataMap().put("deadline","2017-06-27T13:19:00.000+05:30");
workflowdata.getMetaDataMap().put("title","Review through custom workflow");
workflowdata.getMetaDataMap().put("description","Initiate this review process using the AEM workflow");
workflowdata.getMetaDataMap().put("assignee","user-one", "user-two");
workflowdata.getMetaDataMap().put("status","1");
workflowdata.getMetaDataMap().put("projectPath","/content/projects/review");
workflowdata.getMetaDataMap().put("startTime", System.currentTimeMillis());
workflowdata.getMetaDataMap().put("reviewType", "AEM");
workflowdata.getMetaDataMap().put("versionJson", "[{\"path\":\"GUID-ca6ae229-889a-4d98-a1c6-60b08a820bb3.dita\",\"review\":true,\"version\":\"1.0\",\"reviewers\":[\"projects-samplereviewproject-owner\"]}]");
workflowdata.getMetaDataMap().put("isDitamap","false");
workflowdata.getMetaDataMap().put("review_version","3.0");
```

**For Map**

```javascript
var workflowdata = workItem.getWorkflowData();
workflowdata.getMetaDataMap().put("initiator", "admin");
workflowdata.getMetaDataMap().put("operation", "AEM_REVIEW");
workflowdata.getMetaDataMap().put("orgTopics", "GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita|GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita|GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita|");
var payloadJson = "{\"referrer\":\"\",\"rootMap\":\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\",\"asset\":[\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\"],\"base\":\"/content/dam\"}";
workflowdata.getMetaDataMap().put("payloadJson", payloadJson);
workflowdata.getMetaDataMap().put("deadline", "2047-06-27T13:19:00.000+05:30");
workflowdata.getMetaDataMap().put("title", "Review task via workflow with map");
workflowdata.getMetaDataMap().put("description", "Review task via workflow with map Description");
workflowdata.getMetaDataMap().put("assignee", "user-one");
workflowdata.getMetaDataMap().put("status", "1");
workflowdata.getMetaDataMap().put("projectPath", "/content/projects/review_project_via_workflow");
workflowdata.getMetaDataMap().put("startTime", new Date().getTime());
var versionJson = "[{\"path\":\"GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]},{\"path\":\"GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]},{\"path\":\"GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita\",\"version\":\"1.0\",\"review\":true,\"reviewers\":[\"starling-regression-user\"]}]";
workflowdata.getMetaDataMap().put("versionJson", versionJson);
workflowdata.getMetaDataMap().put("notifyViaEmail", "true");
workflowdata.getMetaDataMap().put("allowAllReviewers", "false");
workflowdata.getMetaDataMap().put("isDitamap", "true");
workflowdata.getMetaDataMap().put("ditamap", "GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap");
var ditamapHierarchy = "[{\"path\":\"GUID-17feb385-acf3-4113-b838-77b11fd6988d.ditamap\",\"items\":[{\"path\":\"GUID-db5787bb-5467-4dc3-b3e5-cfde562ee745.ditamap\",\"items\":[{\"path\":\"GUID-ae42f13c-7201-4453-9a3a-c87675a5868e.dita\",\"items\":[],\"title\":\"\"},{\"path\":\"GUID-28a6517b-1b62-4d3a-b7dc-0e823225b6a5.dita\",\"items\":[],\"title\":\"\"}],\"title\":\"\"},{\"path\":\"GUID-dd699e10-118d-4f1b-bf19-7f1973092227.dita\",\"items\":[],\"title\":\"\"}]}]";
workflowdata.getMetaDataMap().put("ditamapHierarchy", ditamapHierarchy);
workflowdata.getMetaDataMap().put("review_version","3.0");
```

You can create these script in the `/etc/workflows/scripts` node. The following table describes the properties being assigned by both of the aforementioned ECMA script.

|Property|Type|Description|
|--------|----|-----------|
|`initiator`|String|User ID of the user initiating the review task.|
|`operation`|String|A static value set as `AEM_REVIEW`.|
|`orgTopics`|String|Path of the topics being shared for review. Specify multiple topics separated by comma.|
|`payloadJson`|JSON object|Specify the following values: -   `base`: path of the parent folder containing the topic sent for review. <br> -   `asset`: path of the topic sent for review. <br> -   `referrer`: leave it blank.|
|`deadline`|String|Specify the time in `yyyy-MM-dd'T'HH:mm:ss.SSSXXX` format.|
|`title`|String|Enter a title for the review task.|
|`description`|String|Enter a description for the review task.|
|`assignee`|String|User ID of the users to whom you want to send the topic\(s\) for review.|
|`status`|Integer|A static value set as 1.|
|`startTime`|Long|Use the `System.currentTimeMillis()` function to get the current system time.|
|`projectPath`|String|Path of the review project to which the review task will be assigned e.g.: /content/projects/samplereviewproject.|
|`reviewType`|String|Static value "AEM".|
|`versionJson`|JSON object|versionJson is list of topics going in the review where each topic object has following structure { "path": "/content/dam/1-topic.dita", "version": "1.1", "review": true, "reviewers": [ "projects-we_retail-editor" ] }|
|`isDitamap`|Boolean|false/true|
|`ditamapHierarchy`|JSON Object|In case the map is sent for review then the value here should be like:[ { "path": "GUID-f0df1513-fe07-473f-9960-477d4df29c87.ditamap", "items": [ { "path": "GUID-9747e8ab-8cf1-45dd-9e20-d47d482f667d.dita", "title": "", "items": [] } ] } ].|
|`ditamap`|String|Specify the path of the ditamap of the review task|
|`allowAllReviewers`|Boolean|false/true|
|`notifyViaEmail`|Boolean|false/true|
|`review_version`|String|Specifies the current version of the Review workflow. The default value is set to `3.0` .<br> To enable the new review workflow features for [Authors](../user-guide/review-close-review-task.md) and [Reviewers](../user-guide/review-complete-review-tasks.md), ensure that the `review_version` is set to `3.0`.|


Once you have created the script, call it before calling the Create Review process in your workflow. Then, depending on your requirements, you can call the other review workflow processes.

### Remove review workflow from the purge configuration 

To improve the workflow engine performance, you can regularly purge completed workflow instances from the AEM repository. If you are using the default AEM configurations, then all completed workflow instances are cleaned up after a specific period of time. This also results in all review workflows to get purged from the AEM repository.

You can prevent review workflows from auto-purging by removing the review workflow model \(information\) from the auto-purge configuration. You need to use the **Adobe Granite Workflow Purge Configuration** to remove the review workflow models from auto-purging list.

In the **Adobe Granite Workflow Purge Configuration**, ensure that you list at least one workflow that you can safely purge. For example, you can use any of the following workflows created by AEM Guides:

-   /etc/workflow/models/publishditamap/jcr:content/model
-   /etc/workflow/models/post-dita-project-creation-tasks/ jcr:content/model

Adding a workflow in the **Adobe Granite Workflow Purge Configuration** ensures that AEM purges only those workflows that are listed in the configuration. This prevents AEM from purging the review workflow information.

For more details about configuring the **Adobe Granite Workflow Purge Configuration**, see *Administering Workflow Instances* in AEM documentation.

### Customize email and AEM notification

A number of the AEM Guides workflows make use of email notifications. For example, if you initiate a review task, an email notification is sent to the reviewers. However, to ensure that the email notification is sent, you have to enable this functionality in AEM. To enable email notification in AEM, see the article [Sending Email](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/implementing/developing/development-guidelines.html#sending-email) in AEM documentation.

The AEM Guides contains a set of email and AEM notifications used in review workflow that you can customize. Perform the following steps to customize these notifications:

1.  Use the Package Manager to download `/libs/fmdita/mail/review` file.

    >[!NOTE]
    >
    > Do not make any customizations in the default configuration files available in the ``libs`` node. You must create an overlay of the ``libs`` node in the ``apps`` node and update the required files in the ``apps`` node only.

1.  The `review` folder contains the following sub-folders:

    - `aem-notification`
    - `CSS`
    - `email-notification`

    The detailed description of these sub-folders is explained below:

    |Review sub-folders|Description|
    |-----------------|-----------|
    |`aem-notification`|Contains different AEM notification types available for customization. <br> `closed` <br> `content-updated` <br> `feedback-addressed` <br> `feedback-provided` <br> `requested` <br> `reviewer-removed` <br> `tag-mention` <br> Within these sub-folders, `primary.vm` and `secondary.vm` files are located that allow you to customize the AEM notification title and description, respectively.| 
    |`CSS`|Contains the `email-notification.css` file for customizing the styling of email notifications.|
    |`email-notification`|Contains different email notification types available for customization. <br> `closed` <br> `content-updated` <br> `feedback-addressed` <br> `feedback-provided` <br> `requested` <br> `reviewer-removed` <br> `tag-mention` <br> Within these sub-folders, `primary.vm` and `secondary.vm` files are located that allow you to customize the email notification subject and body, respectively.|

While customizing an email or AEM notification, ensure that you only use the following predefined set of variables. 


| **Variable name**       | **Description**                                               | **Data type** | **Used in notification type(s)**                                      |
|-------------------------|---------------------------------------------------------------|---------------|------------------------------------------------------------------------|
| `contentPath`           | Path to the content being reviewed                            | String        | A quick link to the task                                                   |
| `projectPath`           | Path to the project containing the review task                | String        |      A quick link to the project location                                                  |
| `reviewTitle`           | Title of the review task                                      | String        | Notification title, email subject                                     |
| `projectName`           | Name of the project                                           | String        | Email body                                                             |
| `commentator`           | Name of the user who added a comment                         | String        | Mention notifications                                                  |
| `commentExcerpt`        | Snippet of the comment added                                 | String        | Email body, notification text                                         |
| `taskLink`              | Direct link to the review task                               | URL           | Email body, notification text                                         |
| `authorName`            | Name of the author who created or updated the review task    | String        | Email body, notification text                                         |
| `dueDate`               | Due date of the review task                                  | Date          | Email body                                                             |
| `reviewerName`          | Name of the reviewer assigned to the task                    | String        | Email body, notification text                                         |
| `user`                  | Generic placeholder for the user receiving the notification  | String        | Generic templates                                                      |
| `recipient`             | Specific user receiving the notification                     | String        | Email header                                                           |
| `closed`                | Indicates that the review task has been closed               | String        | Review closed                                                          |
| `reviewer-removed`      | Indicates that a reviewer has been removed from the task     | String        | Reviewer removed                                                       |
| `requested`             | Indicates that a re-review has been requested                | String        | Re-review requested                                                    |
| `feedback-provided`     | Indicates that feedback has been submitted by a reviewer     | String        | Feedback submitted                                                     |
| `feedback-addressed`    | Indicates that feedback has been addressed by the author     | String        | Re-review requested                                                    |
| `content-updated`       | Indicates that content was updated during the review process | String        | Content updated by author while reviewers are reviewing               |
| `tag-mention`           | Indicates that a user was mentioned in a comment             | String        | Tag mention                                                            |

## Customize post-output generation workflow {#id17A6GI004Y4}

AEM Guides gives you the flexibility to specify a post-output generation workflow. You can perform some post-processing tasks on the output that gets generated using the AEM Guides. For example, you might want to apply some CQ tags on the generated AEM Site output, or set certain properties on the PDF output, or you might want to send an email to a set of users once the output is generated.

You can create a new workflow model to use as a post-output generation workflow. When a post-output generation workflow is triggered, the output generation workflow shares contextual information through the workflow metadata map, which you can use to perform processing on the generated output. The following table describes the contextual information shared as metadata:

|Property|Type|Description|
|--------|----|-----------|
|``outputName``|String|Name of the output preset used to generate the output.|
|`generatedPath`|String|Path in DAM where the generated output is stored.|
|`outputType`|com.adobe.fmdita.output.OutputType|Type of the output preset.|
|`outputTitle`|String|Title of the output preset.|
|`outputHistoryPath`|String|Repository path of the history node.|
|`isSuccess`|Boolean|A flag depicting the final status of the output generation process - success or failure.|
|`logPath`|String|Path in DAM where the output generation logs are saved.|
|`generatedTime`|Long|Time at which the output generation process was triggered.|
|`initiator`|String|The user ID of the user who triggered the output generation workflow.|

To make use of the output generation metadata, you can create an ECMA script or an OSGi bundle. A sample of the ECMA script that uses the metadata is given below:

>[!NOTE]
>
> You can create this script in the ``/etc/workflows/scripts`` node.

```javascript
var session = workflowSession.getSession(); // Obtain session object to read/write the repository.
var payload = workItem.getWorkflowData().getPayload().toString(); // Get the workflow payload (the ditamap file on which the generation was triggered)
var metadata = workItem.getWorkflowData().getMetaDataMap(); // Get the workflow metadata object
var generatedPath = metadata.get("generatedPath"); // supplied by AEM Guides
var username = metadata.get("initiator"); // supplied by AEM Guides
var successful = metadata.get("isSuccess"); // supplied by AEM Guides
var title = metadata.get("outputTitle"); // supplied by AEM Guides
var subject = "Output Generation Finished";
var message = "Generation of output " + title + " just finished " + 
(successful ? "successfully. " : "unsuccessfully. ");
    message += "It was triggered by " + username;    
if (successful) {
    message += "<br/><br/>The path to the generated output is " + 
generatedPath;
}
/*
    MailerAPI.sendMail("dl-docs-authors", subject, message);
*/
```

Once you have created the script, call the custom script in your workflow. Then, depending on your requirements, you can call the other workflow processes. Once you have designed your custom workflow, call the *Finalize Post Generation* as the last step in your workflow process. The *Finalize Post Generation* step ensures that the status of the output generation task gets updated to *Finished* on completion of the output generation process. After creating a custom post-output generation workflow, you can configure it with any of your output generation presets. Select the required workflow in the *Run Post Generation Workflow* property of the required preset. When you run an output generation task using the configured output preset, the task status \(in the Output tab\) changes to *Post-Processing*.
