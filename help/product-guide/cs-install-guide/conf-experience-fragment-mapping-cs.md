---
title: Configure the JSON-based mapping between a topic and an Experience Fragment template.
description: Learn how to configure the JSON-based mapping between a topic and an Experience Fragment template.
feature: Output Generation
role: Admin
level: Experienced
---
# Create a mapping between a topic and an Experience Fragment

Adobe Experience Manager Guides provides the feature to create a JSON-based mapping between a topic and an Experience Fragment template. You can use this mapping to publish content present in some or all elements within a topic to an Experience Fragment. 

1. To download the *experienceFragmentMapping.json*, log into Adobe Experience Manager as an administrator.
1. Select the Adobe Experience Manager link at the top and choose **Tools**.
1. Select Guides from the list of tools and select the **Folder Profiles**.
1. Select the profile tile that you want to configure. For example, select the **Global Profile** tile.
   >[!NOTE]
   >
   > You can configure the mapping for the global or a   folder-level profile.
1. Select the **XML Editor Configuration** tab and select the **Edit** icon on the top.
1. Select the **Download** icon to download the *experienceFragmentMapping.json*  file on your local system. You can then make changes to the file and then upload the same.

1.  You need to follow the following validations:

    1. It should be a JSON file
    2. It should contain an array containing at least one object, and every object should contain the following:


        `"template": string `

        `"mapping": array`

        Each object of mapping must contain the following:
        
       `"name": string`

        `"class": string`

        `"resourceType": string`

        `"attributeMap": array`

         
1. Save the file and upload it.

Experience Manager Guides converts the complete topic to HTML which can then be mapped to the core components used in the Experience Fragment. For example, the content in a `<p>` tag can be mapped to create a text component in the Experience Fragment.
* `name`: Specify the HTML element. For example, `<div>`, `<img>`
* `class`: Specify the DITA element tag corresponding to the HTML element. For example, `<p>` `<image>`
* `resourceType`: Specify the resource type applicable for the component used in Experience Fragment. For example, `wcm/foundation/components/text` is the resourceType for the wcm `text` component.
* `attributeMap`: Provide additional information to the component, such as whether a text component should be rendered as `RichText` or contains the `fileReference` of an image component.




Sample file:

```
[
  {
    "template": "default",
    "mapping": [
      {
        "name": "#element",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      }
    ]
  },
  {
    "template": "/conf/we-retail/settings/wcm/templates/experience-fragment-web-variation",
    "mapping": [
      {
        "name": "div",
        "class": "title",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "h1, h2, h3, h4, h5, h6",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "div",
        "class": "p",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      },
      {
        "name": "img",
        "class": "image",
        "resourceType": "wcm/foundation/components/image",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "fileReference"
          }
        ]
      },
      {
        "name": "#element",
        "resourceType": "wcm/foundation/components/text",
        "attributeMap": [
          {
            "from": "outerHTML",
            "to": "text"
          },
          {
            "value": true,
            "to": "textIsRich"
          }
        ]
      }
    ]
  }
]
```



While publishing the Experience Fragments from the Web Editor, select the `Template` from the dropdown in the **Generate Experience Fragment** dialog box to view the mapping available for the template in the **Mapping** field. If no custom mapping is present for a template, then the default mapping is listed. You can use the default mapping to publish the whole topic as an Experience Fragment. 

For more details, view [Publish Experience Fragments](../user-guide/publish-experience-fragment.md).  
 