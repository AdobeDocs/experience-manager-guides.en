---
title: Release Notes | What's New in Adobe Experience Manager Guides 2025.04.0 release
description: Learn about the new and enhanced features in the 2025.04.0 release of Adobe Experience Manager Guides
role: Leader
exl-id: 3e3177e8-cd29-4a86-b786-7c7a1d0047d9
---
# What's new in the 2025.04.0 release (April 2025)

This article covers the new and enhanced features introduced with the 2025.04.0 release of Adobe Experience Manager Guides as a Cloud Service.

## Implement 'Format' Attribute for External Web Links

Adobe Experience Manager Guides now features a **format** attribute for files linked to external web pages using DITA within the editor. This attribute will be displayed in the source view and will clearly indicate the file type, such as for files with a **.pdf** extension, the format will be set to **.pdf**. Similarly, files with a **.html** extension will have their format set to **html** and for **.dita** or **.ditamap** files their format set to **dita**. Additionally, files with a **.xml** extension will also have their format set to **dita**. For files without any extension, the format will be left blank. Furthermore, for any cross-references (xrefs) with a scope set to **external**, the format will be set to **html** regardless of the file extension in the xref.


## Handling large files in the Editor for enhanced productivity 

Experience Manager Guides has introduced several key features to improve the handling of large files. To enhance performance, functionalities such as undo, redo, outline panel, and the dirty marker are disabled for large files. An alert message is displayed at the top of the interface for large files as shown in the snippet below, indicating the number of elements based on the **largeFileTagCount** parameter in the **uiconfig.json** file. 

Additionally, the tag count is shown on the bottom bar, with a tooltip appearing when you hover over it. Selecting the **Learn more** tab provides detailed information about handling large files. This alert is available only for DITA files and is visible across all views: Author, Source, and Layout.  

![](assets/add-toast-tag-count.png){width="300" align="left"}

## Exported Baseline now includes Document state

The Export Baseline feature has been enhanced to allow you to export a snapshot of the baseline in a Microsoft Excel file. This snapshot now includes the document state along with key details such as the title, file name, file type, version number. By incorporating the **document state** metadata, this feature offers a comprehensive view of document statuses, enhancing tracking and management within your workflow.

## Reusable panel enhancement
