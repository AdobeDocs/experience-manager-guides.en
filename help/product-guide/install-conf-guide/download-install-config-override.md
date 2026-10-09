---
title: Configuration overrides for Cloud Service
description: Learn how to Configuration overrides
feature: Installation
role: Admin
level: Experienced
exl-id: baf48913-ced7-444f-a125-661c0213d847
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: e88e74c7-6080-446a-8eb0-496f1ac5f7e6
    internal-label: Administration
subfeature_v2:
  - id: e557051c-ff02-4ff8-9421-cf452af0edd5
    internal-label: Installation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
---
# Configuration overrides for Cloud Service {#id216IFC003XA}

For making any configuration updates in Experience Manager Guides as a Cloud Service, the following generic approach should be used:

1.  Access your Cloud Manager's Git repository.

1.  Create a new JSON file at the following location:

    `src/main/content/jcr\_root/apps/fmditaCustom/config/`

1.  Name the file in the following format:

    `$\{PID\}.cfg.json`

    Here, the PID is the process ID of the configuration.

1.  Add properties in the JSON file using the following format:

    ```
    {
       "aem.adminuname": "updatedUserjson",
       "valid.characters": "[-a-zA-Z0-9_@$]",
       "dita.serialization": true
    }
    ```

1.  Commit the changes and run the Cloud Manager pipeline to deploy the updated configuration.
