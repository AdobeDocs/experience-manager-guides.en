---
title: Add new custom actionable button in webeditor toolbar
description: Learn how add a new custom button in webeditor toolbar and call javascript to custom operate it.
exl-id: 34999db6-027a-4d93-944f-b285b4a44288
feature: Web Editor
role: User, Admin
TQID: https://experienceleague.adobe.com/7NqswCerJdfej5j4XqnPhHzvvAkhlThHAUY3iQYL3t0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
    internal-label: Profiles
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
    internal-label: Web Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Add new custom actionable button in webeditor toolbar

In this article we will learn how add a new custom button in webeditor toolbar and call javascript to perform desired custom operation.

Adding a actionable button to webeditor involves following steps:
- Adding the button in the *ui_config.json* at the position where it is needed
- Registering the button on-click event in the webeditor for user to perform an action when they click it


## Implementing by taking an example

Let us understand this with an example where a author wants to add a jira reference to a topic prolog section. The prolog section with embedded jira reference-id may look like below:

![Prolog section with JIRA ID reference](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-sample.png)

The "change-request-id" element that contains the JIRA ID should be retrieved from the API (lets say based on a specific JIRA query which is depicted by application). When the user is authoring the prolog section, user should be able to click a button and insert a jira reference id from web-editor toolbar, something like:

![Prolog section - add JIRA reference](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-insertjirareference.png)

And when the user clicks the button, it should show a dialog which should pull the possible options and allow the user to select the desired JIRA ID, something like:

![Prolog section add JIRA ID dialog](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-insertjirareference-dialog.png)

which should then add the "change-request-id" to the prolog:

![Prolog section with JIRA ID reference](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-sample.png)



## Implementing this


### Add the button in webeditor by configuring it in *ui_config.json*

Use the folder profiles to check the *ui_config.json* under the "XML Editor Configuration" tab and add the button configuration JSON into the desired section of the "toolbar" group

```
{
    "on-click":"insertJIRARef",
    "icon":"linkCheck",
    "variant":"quiet",
    "type":"button",
    "title":"Insert JIRA Reference"
}
```

[use this link to learn more about Folder profile and configuring ui_config.json](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=en)


### Handle the on-click event for the new button

NOTE: Steps mentioned below are available as package attached in this post


- After saving the folder profile create a "cq:ClientLibraryFolder" under a project directory (could be under */apps*) and add properties as shown in the screenshot below:
![Client library settings for webeditor](../../../assets/authoring/webeditor-add-customtoolbarbutton-clientlibrarysettings.png)

```
This example uses "coralui3" library to show a dialog as it is used in the Javascript sample we presented.
You may use different library of your choice.
```

- Under this client library folder create two files as mentioned below:
    - *overrides.js*: which will have the javascript code to handle the on-click event for "insertJIRARef" (use attached package to get the content of this javascript)
    - *js.txt*: which will include the "overrides.js" to enable this javascript

- Save the changes and you should be ready to test.


### Testing

- Open web-editor
- From user preferences choose the folder profile in which you added the custom *ui_config.json*. If you added it to the Global profile then you are probably already using that.
- Open a topic, you will notice the toolbar having a new button "Insert Jira Reference"
- You can then add prolog section as given below to the topic and try clicking in "Insert Jira Reference" button inside the prolog element "change-request-reference"

```
<prolog>
    <change-historylist>
        <change-item>
            <change-request-reference>
            </change-request-reference>
            <change-completed></change-completed>
            <change-summary></change-summary>
        </change-item>
    </change-historylist>
</prolog>
```

Refer screenshot below to know how it will look like:

![Test new button](../../../assets/authoring/webeditor-add-customtoolbarbutton-testing.png)


### Attachments

- Sample clientlibs package which will install the webeditor client library having javascript code for toolbar button action: [download using this link](../../../assets/authoring/webeditor-addbuttonontoolbar-insertjira-clientlib.zip)
- Sample *ui_config.json* that you can upload to a folder profile: [download sample ui_config.json](../../../assets/authoring/sample_ui_config_Guides4.2-InsertJiraReference.json) 

```
Please note this is compatible to AEM 6.5 and AEM Guides version 4.2.
If you are using a different version please add the toolbar button to the ui_config.json manually.
```
