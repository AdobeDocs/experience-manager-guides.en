---
title: Release Notes | What's New in Adobe Experience Manager Guides 2026.01.0 release
description: Learn about the new and enhanced features in the 2026.01.0 release of Adobe Experience Manager Guides
role: Leader

---
# What's new in the 2026.01.0 release (January 2026)

This article covers the new and enhanced features introduced with the 2026.01.0 release of Adobe Experience Manager Guides as a Cloud Service.

For the list of issues fixed in this release, view [Fixed issues in the 2026.01.0 release](fixed-issues-2026-01-0.md).

Learn about [upgrade instructions for the 2026.01.0 release](../release-info/upgrade-instructions-2026-01-0.md).

## New Document state filter for Repository on the Home page

Now, filter your Repository search based on the current document state of the files. With the new **Document state** filter, you can narrow down your search using the available filter values defined in the `ui_config.json` file within your Folder profile.  

This means: 

- If you are using the Global Profile, the filters values configured in the Global profile are applied. 
- If you select a specific Folder profile, the filters values defined in that profile are fetched. 

![](assets/document-state-filter-repository.png){width="300" align="left"}

The default filter values available for Document state are: Draft, Edit, In-Review, Approved, Reviewed, and Done. For details on customizing the default document state filters values, view [Configure document state filters](../cs-install-guide/config-doc-state-filters.md). 

## Refresh topics or map in the Preview mode

Introducing the new **Refresh** functionality for maps that are already opened in the Preview mode. With this new feature, you can easily refresh the content of the entire map or individual topics present within it  - which otherwise do not refresh if you switch back to the Preview mode from any other tab present in the Editor. 

- To refresh the entire map (including all topics), a new **Refresh** button is available on the top-left corner of the Editor. 

    ![](assets/refresh-map.png){width="600" align="left"}

- To refresh the content of individual topics, a new **Refresh topic** option is available in the context menu.

    ![](assets/refresh-topic.png){width="600" align="left"}


## Add or remove topics from an ongoing Review task

Now, you can add new topics to an ongoing review task (if they were not previously sent for review) or remove topics from an ongoing review task without affecting the review workflow.

On the **Task Details** page, you can simply select or unselect topics to modify the topic list. Reviewers are notified (via AEM and email) about any changes to their assigned topics, ensuring they stay informed and aligned with the latest review requirements. For more details, view [Send topics for review](../user-guide/review-send-topics-for-review.md).

![](assets/modify-review-topics.png){width="650" align="left"}

## Enhanced file and folder browsing experience 

Experience Manager Guides now introduces enhanced user interface for browsing folders and files in Experience Manager Guides.

The new **Select file** dialog features two tabs - **Repository** and **Collections**, allowing you to choose where your files are located before proceeding. In the Repository tab, you can search for files by name, title, or content within the selected path. You can also use the breadcrumbs at the top and the folder navigation panel on the left to move through folders. To narrow down your search results, you can use the available filtering options from the Filters panel.  

For more details on using Repository filters, view [Filter search in Repository](../user-guide/web-editor-left-panel.md#filter-search-in-repository).

The **Select path** dialog, on the other hand, provides an enhanced user interface for selecting folder paths with ease. Folders are displayed in a clear, tree-structured view, allowing you to quickly navigate through the hierarchy and choose the correct path for your content. 

## Working copy indicator for metadata changes

Any changes to the metadata fields available under **File properties** will now trigger the working copy indicator. A document version is marked as _dirty (*)_ whenever you add, delete, or modify any default or custom metadata fields. This enhancement ensures that all metadata changes are accurately tracked, providing greater visibility and control over document versions.

## Indicator for unversioned assets sent for translation 

When managing translations, it's important to ensure that all content is versioned before sending it for processing. To help with this, Experience Manager Guides now provides a clear indicator for topics that have saved changes but are not yet versioned.

If a file contains unversioned changes (not saved as a new version in your map), an _info_ icon appears next to the file, indicating that updates exist. To quickly focus on these files, enable the **Show assets with unversioned changes only** option in the Filters panel.

For more details, view [Translate documents from the Map Console](../user-guide/translate-documents-web-editor.md). 

![](assets/unversioned-changes-translation.png){width="650" align="left"}

## Support for word count in Experience Manager Guides

You can now track the word count present within a map or topic file. The new **Word count** field in the Right panel would display the total number of words in a topic where words separated by spaces are counted as individual words. It refreshes automatically each time you save changes. For cross-references, only the display text is included, while keys are excluded.

![](assets/file-properties-new.png){width="350" align="left"} 

With this release, the word count feature is available for all new topics you create in Experience Manager Guides. For existing topics, you need to [reprocess assets](../user-guide/asset-processor.md) to enable this functionality.

For details, view [Right panel in Editor](../user-guide/web-editor-right-panel.md#file-properties).

## Configure custom image renditions for specific output presets

You can now configure different image renditions for individual output presets under the same output type by using the `outputName` attribute in `renditionmapping.xml`. This enhancement gives you greater flexibility when publishing content that requires varying image resolutions for different scenarios. For example, you might want a high-resolution image for your main HTML5 output while using a smaller thumbnail for a lightweight preset.

For more details, view [Handle image rendition in output generation](../cs-install-guide/conf-output-generation.md#handle-image-rendition-during-output-generation).

## Enhancements to Asset processing 

With this release, Experience Manager Guides provides greater flexibility in asset processing. You can now:

- Run asset processing for selected files instead of processing all assets. 
- Choose a specific asset type such as topics, maps, Markdown, HTML/CSS, DITAVAL, or other supported files for targeted processing. 
- Apply date filters to process only assets created within a specified timeframe.
- Reprocess assets directly using the new option available in the context menu of files and folders within Repository and Explorer panel. 

For more details on processing assets, view [Process assets](../user-guide/asset-processor.md).

## Download logs for generated output

When generating output through the Assets UI, you can now **Download logs** to your local device for easier access and review. This option becomes available when the log list is extensive, ensuring you can review detailed information more efficiently. 

## Thumbnail icon for images in Repository and Search panel

All image files are now displayed with thumbnail icons, making it easier to visually identify and locate images within the Repository. This enhancement also applies when searching for files in the Search panel, helping you quickly distinguish image assets from other file types. 

## API enhancements

The following API enhancements have been made in this release:

- New API introduced to easily create new translation project and track their status. 
- Support for element-level mapping for AEM Sites (using Composite component mapping), allowing authors to define custom mappings for individual DITA elements. 
- Enhanced APIs to support filtering ability for asset processing for files and folders.

## Find and replace new enhancements 












   

