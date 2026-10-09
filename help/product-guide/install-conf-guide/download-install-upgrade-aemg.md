---
title: Upgrade AEM Guides for Cloud Service
description: Learn how to Upgrade AEM Guides
feature: Installation
role: Admin
level: Experienced
exl-id: 9d48a7c4-384d-4ad4-a1d3-4c50d97e5d5b
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
# Upgrade AEM Guides for Cloud Service {#id213BD050YPH}

Perform the following steps for upgrading AEM Guides:

1.  Access your Cloud Manager's Git repository.

1.  Update the `dox/dox.installer/pom.xml` file.

1.  Update the value of `dox.version` variable to the version details provided by Adobe.

1.  Commit the changes and run the Cloud Manager pipeline to deploy the upgraded package.


>[!NOTE]
>
> For more details about using CI/CD pipeline, see [Use the CI/CD Pipeline in Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html).

## Clear browser cache 

After completing the upgrade process, all users must clear the browser cache before using the upgraded version of AEM Guides.
