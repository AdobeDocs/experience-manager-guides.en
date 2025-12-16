---
title: Configure document state filters
description: Learn how to configure document state filters
feature: Web Editor Configuration
role: Admin
level: Experienced
---
# Configure document state filters {#id21BPD0FK0XA}

Adobe Experience Manager Guides provides the feature to search a file based on its current document state. You can use filter search to search files from the repository interface to browse files. 

Perform the following steps to configure the document state filters:

1.  Log into Adobe Experience Manager as an Administrator.
1.  Select the Adobe Experience Manager link at the top and choose **Tools**.
1.  Select **Guides** from the list of tools and then select **Folder Profiles**.
1.  Open the **Global Profile** tile. You can also select a specific Folder profile tile if you want these changes to apply only to that folder instead of globally.
1.  Navigate to **XML Editor Configuration**.
1.  Select the **Edit** icon on the top.
1.  Select the **Download** icon to download the `ui\_config.json` file on your local system. 
    In the downloaded `ui\_config.json` file, refer to the following section:
             
        ```
        "repositoryFilters": [
            {
            "title": "Document state",
            "property": "jcr:content/metadata/docstate",
            "children": [
                {
                "title": "Draft",
                "value": "Draft"
                },
                {
                "title": "Edit",
                "value": "Edit"
                },
                {
                "title": "In-Review",
                "value": "In-Review"
                },
                {
                "title": "Approved",
                "value": "Approved"
                },
                {
                "title": "Reviewed",
                "value": "Reviewed"
                },
                {
                "title": "Done",
                "value": "Done"
                }
            ]
            }
        ]
        ```
    This snippet represents the default document state filters available in Experience Manager Guides.

1. You can customize the filter values based on your organization's workflow. For example, to add a custom document state **Pending**, insert the following entry under `children`:


        {
                "title": "Pending",
                "value": "Pending"
        },
    
1.  Once updated, save the file and upload it.

The configured filters are displayed in the **Filters** panel in Repository on Home page.

**Parent topic:**[Customize Web Editor](conf-web-editor.md)
