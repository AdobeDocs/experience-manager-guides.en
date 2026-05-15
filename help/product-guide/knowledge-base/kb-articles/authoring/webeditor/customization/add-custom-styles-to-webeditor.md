---
title: Add custom styles to Guides webeditor
description: Learn how add custom styles to change look and feel of the Guides webeditor.
exl-id: 03143fb2-d05d-4103-b172-8b91880b7f9e
feature: Web Editor
role: User, Admin
TQID: https://experienceleague.adobe.com/uQc8TTz7dHxbN6-zbin-esQevLoJR-IMR1hchrwEs8M
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
# Add custom styles to Guides webeditor 

In this article we will learn how add custom styles to change the webeditor default look and feel. 

This will involve following steps:
- Adding the custom styles via Folder profile XML Editor Configuration
- Choosing the respective folder profile in webeditor and testing the changes


## Implementing by taking an example

Let us understand this with an example where we want to show the short description and title as separate block with some style aspects in editor.

![Previewing the webeditor with custom styles](../../../assets/authoring/webeditor-customstyles-preview.png)


## Implementing this


### Adding the custom CSS to the folder profile

Use the folder profiles to check the *css_layout.css* under the "XML Editor Configuration" tab and add the CSS having custom styles

[use this link to learn more about Folder profile and configuring CSS template layout](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=en#customize-the-css-template-layout)

Use the following to setup above style in your webeditor:
- Use [css_layout.css](../../../assets/authoring/webeditor-customstyles-css_layout.css) and upload it to the folder profile of your choice
- Install the attached package [webeditor-styles-resources.zip](../../../assets/authoring/webeditor-styles-resources.zip) using AEM package manager to install the resources used in the above CSS file 

```
This will install the resources at path "/content/dam/resources" which will include sub-folders "fonts" and "images"
```


### Testing

- Open web-editor
- From user preferences choose the folder profile in which you added the custom styles. If you added it to the Global Profile then you are probably already using that.
- Open a topic, you will notice the editing area should have custom UI

```
Please note this is compatible to AEM Guides version 4.2 and AEM Guides cloud version 2303 (March)
```


## References

You may also be interested in the expert session around webeditor configurations and customization covered in [Expert session on webeditor](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/knowledge-base/expert-session/webbased-authoring-jan2023.html?lang=en)
