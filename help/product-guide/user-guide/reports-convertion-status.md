---
title: Conversion Status Report
description: Convert documents of different formats into DITA in AEM Guides. Learn how to add filters and view a conversion status report.
exl-id: 0a4699e5-865f-40e1-a17f-5e1a248ea955
feature: Report Generation
role: User
TQID: https://experienceleague.adobe.com/-Jgxys5YiwelOf7jQHYQ4Y9ARYzwLCZ8lNStdnT4oLI
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: d90290ec-3e61-4ebd-8649-bcafe0836803
    internal-label: Reports
subfeature_v2:
  - id: cdab8659-8d50-4417-b6fd-762f347c13ee
    internal-label: Report generation
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
    internal-label: Content reuse
---
# Conversion Status Report {#id205BBA00WZZ}

Adobe Experience Manager Guides provides a robust conversion feature to convert documents of various formats into DITA. The Conversion Status Report provides a consolidated view of all conversion tasks executed by Experience Manager Guides.

Perform the following steps to view the Conversion Status Report:

1.  Select Adobe Experience Manager logo at the top and choose **Tools**.

1.  Select **Guides** from the list of tools.

1.  Select the **Conversion Status Report** tile.

    The Conversion Status Report is displayed for all conversion tasks executed on the system.

    ![](images/conversion-status-report-new.png)

1.  The report page is divided into two parts:

    -   **Filter:**

        You can filter the report data on the basis of File Type and conversion Status. In the File Type, you can choose to view the report data for Word document, structured HTML, XML, DocBook and IDML type of documents. In the Status, you can choose to view the report data for tasks that have executed Successfully, Failed, Active, or Queued.

        The following screenshot displays the report data for conversion tasks that has Success status.

        ![](images/conversion-report-failed-active-queued-new.png)

    -   **Report data:**

        The report data contains the following columns:

        - **File Name**: Name of the source file on which the conversion process was executed. Selecting the File Name link takes you to the source document location.

        - **File Type**: Type of the source document, which could be Word, structured HTML, XML, IDML and DocBook.

        - **Added By**: Name of the user who executed the conversion task.

        - **Date Added**: Date on which the task was executed. Selecting on the Date Added link downloads the log file.

        - **Path**: Complete path of the source document.

        - **Status**: Status of the conversion tasks - Success, Failed, Active, or Queued.

        - **Output**: Path of the successfully converted document. Selecting on the Output link takes you to the location where the output is saved.


**Parent topic:**[Introduction to reports](reports-intro.md)
