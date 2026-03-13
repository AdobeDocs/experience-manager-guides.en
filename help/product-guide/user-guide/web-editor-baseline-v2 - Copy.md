---
title: Create and manage new baseline (Beta) from the Map console
description: Create and manage new baseline (Beta) from the map console in Adobe Experience Manager Guides. 
feature: Authoring, Features of Web Editor, Publishing
role: User
---
# New Baseline (Beta) in Experience Manager Guides

>[!NOTE]
>
> This article applies to new Baseline (Beta) offering improved performance and stability available with the Experience Manager Guides 2026.03.0 release. To use this baseline, contact the Customer Success Team to have the feature enabled.

The New baseline, currently available as a *Beta* feature, in Experience Manager Guides addresses critical reliability and performance issues associated with large, complex maps. It comes with a redesigned baseline architecture that delivers a faster, more stable, and more consistent baseline experience.  

The new baseline model strengthens baseline handling by addressing the common pain points:

- Slow loading and poor responsiveness when working with large baselines
- Inconsistent baseline states caused by partial updates or failed validations
- Limited visibility and control when managing extensive baseline content
- Performance bottlenecks during baseline creation, updates, or rebuilds

By modernizing how baseline data is stored, loaded, and processed, the new Baseline enhances baseline‑driven workflows especially for large and complex maps.

The following sections describe the new baseline model, including the enhancements it introduces, key behavior changes to consider before migration, and instructions for migrating to and using the new baseline:

- [Key enhancements introduced in the new baseline](#key-enhancements-introduced-in-the-new-baseline)
- [Behavior changes to know before migrating to the new baseline](#behavior-changes-to-know-before-migrating-to-the-new-baseline)
- [Migrate to the new baseline](#migrate-to-new-baseline)
- [Use the new baseline](#use-the-new-baseline)

## Key enhancements introduced in the new baseline

The new Baseline introduces significant improvements that make baseline management faster, safer, and easier to scale without changing how you work. Consider moving to the new baseline for:

- **Improved performance and scalability:** The baseline data model and rendering behavior have been optimized to scale efficiently with large baselines, using incremental loading and a streamlined data structure to improve responsiveness.
- **Stronger UI and backend consistency:**  Baseline updates are reflected in the UI only after successful backend validation, ensuring that the displayed baseline state always represents persisted and validated data.
- **Filtering, sorting, and navigation:** Baselines support comprehensive filtering across multiple attributes, including document state, labels, file type, reference type, and GUID‑based search across the entire baseline. Pagination is supported for large baselines, with an option to include files that have no labels.
- **Clear visibility into dependency impact:**: Dependency impact (for added or removed dependancies) is calculated automatically before version changes are applied, allowing you to review the impact of a change before applying it.
- **More flexible label management:** Labels can be moved between versions within a baseline, providing greater flexibility when managing labels across evolving content.
- **Deterministic editing and saving behavior:** Baseline edits support row-level updates, load resource-intensive data (such as version trees and dependency differences) only during version updates, and complete save operations deterministically in a single step - reducing unexpected save failures and partial updates.
- **More reliable baseline creation:** Baselines are created using stored reference data rather than runtime parsing, with required version information validated upfront to prevent incomplete or invalid baselines.
- **API and automation support:** The new baseline model is fully supported through REST APIs and the Java SDK, enabling automation and integration with external workflows.


## Behavior changes to know before migrating to the new baseline

Before migrating to the new baseline model, review the following behavior changes. These changes affect how baselines are created, updated, and managed, and may influence existing workflows.

| Area | Change (description) |
|------|-------------|
| **Reference resolution** | Direct map references are classified as **DIRECT**. Invalid references are skipped, and references from `reltable` continue to be excluded. |
| **Pick Automatically** | Version selection for Pick automatically functionality is evaluated just before the time of direct reference, and not after the direct referenc. |
| **Baseline creation rules** | Version **1.0** is mandatory. Baselines with missing or ambiguous versions may resolve differently after migration. |
| **Migration handling** | Invalid references are skipped. **DIRECT** references take precedence, unpinned references move to the latest version, and additional metadata is added from version **5.0** onward. |
| **Baseline data model** | The new graph‑based baseline model removes mutable fields and is not backward compatible with legacy baselines. |
| **API usage** | Baseline operations are supported through REST APIs and the Java SDK. Raw baseline objects are no longer exposed. |
| **Version purging** | After migration, version purging considers only baselines stored in the new baseline repository. |

## Migrate to new Baseline  

Once you have the feature enabled from Customer Success Team, you need to migrate the existing baselines to the new Baseline. 

Perform the following steps, to migrate the existing baseline to the new Baseline.

1. Select the Adobe Experience Manager logo at the top and choose **Tools**.
1. In the **Tools** panel select **Guides**.
1. Select the **Bulk Processor** tile.

    ![flow-asset-processor](images/flow-asset-processor.png){align="left"}

    The Guides Bulk Processor window opens.    

1. Select **New Process** tab on the top right corner of the window to start a new processing task.

    The **New process** dialog opens.   

1. Provide the following details in the dialog:

    1. **Feature Type**: Select **Baseline** from the drop drown.
    1. **Select folders and files**: Navigate and choose one or multiple folders and files to process. 
    1. **Select folders to ignore**: Optionally, select sub-folders within the chosen parent folder to exclude from migrating.   

    ![new-process-baseline](images/new-process-baseline.png){align="left"}

1. Select **Create**. You get a pop-up showing **Asset processing triggered successfully**. You can see the status of the processing task on the window.
You can also select **View logs** to check and download the logs for the migration task. 

    ![view-logs-baseline](images/view-logs-baseline.png){align="left"}

    The log report provide details of the migration, including the number of maps migrated, baselines successfully migrated, and related details.      

    ![logs-detail-baseline](images/logs-detail-baseline.png){align="left"}

>[!NOTE]
>
> No baseline edits should be made during migration, particularly in working copies, to prevent failures. Post‑migration, some baselines may require rebuilding if versions are missing.    

## Use the new Baseline

The new baseline model uses the same workflows and user interface as the existing baseline feature in AEM Guides. You continue to [Create and manage baseline from Map console](./web-editor-baseline.md) using the available options. 

>[!NOTE]
>
> New baseline does not support creating and managing baselines from Map dashboard. 

This section describes only the changes and enhancements introduced with the new baseline model. Common baseline workflows remain unchanged unless explicitly mentioned.

**New/enhanced options available in the new baseline UI**

The following updates apply when working with baselines created using the new baseline model:

- The **Export baseline** option in the Options menu is renamed to **Download** for baselines created using both Manual and Automatic updates.
    ![](images/baseline-v2-options-menu.png)

- Dynamic baselines can now be opened directly from the Baseline panel and managed using the available Options menu actions.

     ![](images/baseline-v2-dynamic-baseline-new.png)
    
    You can also use the new options introduced for dynamic baselines created using the new baseline models:       
    - **Edit properties**: Allows you to edit the properties of an existing static baseline that you have set while creating the baseline.
    - **Rebuld**: Allow you to rebuild the dynamic baseline whenever changes occur.

        ![rebuild-baseline](images/rebuild-baseline.png){align="left"}

- The **Download** action supports paginated downloads. All baseline content that matches the applied filters is included in the download, not just the content visible on the current page.
- Filter files by GUID, in addition to file names, or file location. An additional option to **Filter files with no labels** is also available. 

    ![](images/baseline-v2-filters.png)
- The new baseline model supports deterministic editing, allowing you to update one reference at a time with validated dependency resolution. 

    +++Steps for editing the references of a new baseline

    Perform the following steps to make edits to a baseline:

    - Open the baseline from the **Baseline** panel.

        The tabular view of files mapped with the baseline is displayed. 

    - Navigate to and hover-over the file which you want to edit. 
    - Select the **Edit** icon. 

        ![edit-baseline-icon](images/edit-baseline-icon.png){align="left"}
        
        The **Edit version** dialog is displayed. 

        ![edit-version-baseline](images/edit-version-baseline.png){align="left"}
    - Select the required version from the Version dropdown (for example, change from version 1.0 to 1.1) and select Update.
    
        Added and removed dependencies are evaluated automatically and displayed.
    
        ![](images/baseline-v2-version-added.png)and select **Update**. The baseline is then updated with the new version.

        If no dependency changes are detected, an empty‑state message is displayed.

    - Select **Update**. 

    The baseline is updated with the selected version.








 


+++



    

   