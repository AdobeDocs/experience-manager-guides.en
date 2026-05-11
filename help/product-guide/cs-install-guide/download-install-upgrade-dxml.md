---
title: Upgrade AEM Guides
description: Learn how to Upgrade AEM Guides
exl-id: 57ae906f-69e3-4319-89f6-0fa9ddb7a3ff
feature: Installation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/jGMljbRp60Wst7hVLeanMTLHY79Yhqo7yeUCCsLXx3k
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Upgrade AEM Guides {#id213BD050YPH}

1.  Access your Cloud Manager's Git repository.

1.  Update the dox/dox.installer/pom.xml file.

1.  Update the value of dox.version variable to the version details provided by Adobe.

1.  Commit the changes and run the Cloud Manager pipeline to deploy the upgraded package.


>[!NOTE]
>
> For more details about using CI/CD pipeline, see [Use the CI/CD Pipeline in Adobe Cloud Manager](https://experienceleague.adobe.com/docs/experience-manager-learn/foundation/cloud-manager/use-the-cicd-pipeline-in-cloud-manager-for-aem.html).

## Clear browser cache 

After completing the upgrade process, all users must clear the browser cache before using the upgraded version of AEM Guides.

**Parent topic:**[Download and install](download-install.md)
