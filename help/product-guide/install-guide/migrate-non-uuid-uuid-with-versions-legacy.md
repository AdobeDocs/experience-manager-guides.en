---
title: Convert non-UUID content with versions to UUID content
description: Learn how to migrate non-UUID content with versions to UUID content.
feature: Migration
role: Admin
level: Experienced
exl-id: 8f3a89fc-7d18-453d-909d-6dff5e275cab
---
# Migrate versioned content

>[!NOTE]
>
> You can migrate your non-UUID content to UUID content in Experience Manager Guides. This article will be archived in November 2024.
>View [**Non-UUID to UUID content migration**](./migrate-non-uuid-uuid.md) for the latest and detailed documentation.

Perform these steps to migrate your non-UUID versioned content to UUID content. 

>[!NOTE]
>
>Follow the [upgrade instructions](./upgrade-xml-documentation.md) specific to the licensed version of your product. 

## Compatibility matrix

|Current Experience Manager Guides version (non-UUID)|Required Version to migrate to UUID| Supported Upgrade path| 
|---|---|---|
| 3.8.5, 4.0.x, or 4.1.x  |  4.1 non-UUID|Install 4.1 (UUID) and run the migration|
|4.2, 4.2.x, or 4.3|   4.3.0 non-UUID |Install 4.3.1 (UUID) and run the migration|
|4.3.1|   NA |NA |

## Package installation

Download the required packages from Adobe Software Distribution Portal, based on your version:
<details>
<summary>  Packages for version 4.1 upgrade path</summary>

1. **Pre-migration**: [com.adobe.guides.pre-uuid-migration-1.0.9.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F1-0%2Fcom.adobe.guides.pre-uuid-migration-1.0.9.zip)
1. **Migration**: [com.adobe.guides.uuid-upgrade-1.0.19.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2F1-0%2Fcom.adobe.guides.uuid-upgrade-1.0.19.zip)
</details>


<details>
<summary> Packages for version 4.3.1 upgrade path</summary>

1. **Pre-migration**: [com.adobe.guides.pre-uuid-migration-1.1.3.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2Fcom.adobe.guides.pre-uuid-migration-1.1.3.zip)
1. **Migration**: [com.adobe.guides.uuid-upgrade-1.1.15.zip](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Faemdox%2Fother-packages%2Fuuid-migration%2Fcom.adobe.guides.uuid-upgrade-1.1.15.zip)

</details>

## Pre-migration

Perform the following checks on the non-UUID version (4.1 non-UUID or 4.3.0 non-UUID):

1. Install the pre-migration package according to your version.

   >[!NOTE]
   >
   >* You need administrator permission to execute the migration. 
   >* Fixing the files with errors before proceeding with the migration is recommended. 

1. (Optional) Perform version purging on the content to remove unnecessary versions and speed up the migration process. To perform version purging, select the option **Version Purge** from the migration screen and go to the user interface using the URL `http://<server- name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`. 
   >[!NOTE]
   >
   >This utility does not remove any versions used in baselines or reviews or has any labels.   

1. Launch `http://<server-name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`. 
1. Select **Compatibility Assessment**  from the left panel and browse a folder path.
1. Check the compatibility to list the following information:
    * Total files
    * Total versions
    * Estimated time for migration
    * Number of files with errors 

    ![compatibility assessment tab in migration](assets/migration-compatibility-assessment.png){width="800" align="left"}


1. Select **Configure Validations** from the left panel. Then, **Select map** and **Select preset** of the map to configure them. The current output validation list displays the output files present before migration and can be validated against the output files generated post-migration later. 

    ![Configure Validations tab in migration](assets/migration-configure-validation.png){width="800" align="left"}




## Migration 

### Step 1: Update configuration

1. Ensure that the free space available is at least ten times the space taken by AEM (crx-quickstart directory) during migration. Once you complete the migration, you can reclaim most of the disk space by running compaction (refer to [Revision Cleanup](https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en)).

1. Enable *Enable Post Processing Workflow Launchers* in `com.adobe.fmdita.config.ConfigManager` and *Enable Version Postprocessing* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation.`

1. Install the UUID version of the supported release over the non-UUID version. For example, if you're using 4.1 non-UUID build, you need to install UUID version 4.1 and run the migration.

1. Install the new package for uuid migration.

1. Disable the following workflows and any other workflow that runs on `/content/dam` using launchers in `http://<server-name>/libs/cq/workflow/content/console.html`.

    * DAM Update Asset workflow
    * DAM Metadata Writeback workflow

1. Disable *Enable Post Processing Workflow Launchers* in `com.adobe.fmdita.config.ConfigManager` and disable *Enable Version Postprocessing* in `com.adobe.fmdita.postprocess.version.PostProcessVersionObservation`. 

1. Disable the property Enable validation (`validation.enabled`) in Day CQ Tagging Service.

1. Ensure that `uuid.regex` property folder is set properly in `com.adobe.fmdita.config.ConfigManager`. If it's blank, set it to the default value - `^GUID-(?<id>.*)`.
1. Add a separate logger for `com.adobe.fmdita.uuid` The browser response is also available at `/content/uuid-upgrade/logs`.

### Step 2: Run the migration and validate

#### Install the migration package

1. Launch `http://<server-name>/libs/fmdita/clientlibs/xmleditor_uuid_upgrade/page.html`.

    ![System upgrade tab in migration](assets/migration-system-upgrade.png){width="800" align="left"}

1. Select **System upgrade** from the left panel to run the migration. Start on a folder with smaller data before running it on `/content/dam`.

1. Select **Download Report** while the migration is running to check whether all files in the folder are upgraded correctly and whether all features work only for that folder.


>[!NOTE]
>
> Content migration can be run on a folder level, the complete `/content/dam`, or the same folder (rerun migration).

Also, it's important to make sure that the content migration is done for all the media assets, such as images and graphics you have used in the DITA content.

#### Baseline and Review migration

Select **Baseline/Review Upgrade** from the left panel to migrate the baselines and review at the folder level.  

![Baseline and review tab in migration](assets/migration-baseline-review-upgrade.png){width="800" align="left"}


### Step 3: Restore the configuration

After migrating the server successfully, enable post-processing, tagging, and the following workflows (including all the other workflows that were disabled initially during the migration) to continue working on the server.

* DAM Update Asset workflow
* DAM Metadata workflow

>[!NOTE]
>
>If some files are not processed or corrupted before migration, they will be corrupted before migration and remain corrupted even after migration.

## Migration validation

1. Once the migration is completed, select **Validate system upgrade** from the left panel and validate the output files before and after the migration to ensure that the migration is successful. 

    ![Validate system upgrade tab in migration](assets/migration-validate-system-upgrade.png){width="800" align="left"}


1. After the validation is done, most of the disk space can be reclaimed by running compaction (refer to `https://experienceleague.adobe.com/docs/experience-manager-65/deploying/deploying/revision-cleanup.html?lang=en`).
