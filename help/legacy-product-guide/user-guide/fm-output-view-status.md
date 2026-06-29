---
title: View the status of the output generation task
description: View the output generation queue of FrameMaker documents. Learn how to view the status of an output generation task.
feature: Publishing FrameMaker Documents
role: User
hide: true
exl-id: bf5a4365-0183-43d5-a39a-b9eb8a34b27d
TQID: https://experienceleague.adobe.com/FP5RxNtyWcdS-xpw2Atttt3x6DHx73Ljv-Ym91IxY5s
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
  - id: bf79f6d3-0ad0-4d82-99e4-42ce98324d60
    internal-label: Publishing FrameMaker documents
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# View the status of the output generation task {#viewing_output_history}

Once you initiate the output generation task for a FrameMaker document, AEM Guides sends this task to the output generation queue. This queue is updated in real time, showing the status of each output generation task in the queue.

Perform the following steps to view the output generation queue:

1.  In the Assets UI, navigate to and click FrameMaker document for which you want to check the output generation status.

1.  Click Outputs.

    ![](images/output-queued-fm.png){width="800"}

1.  The Outputs page is divided into two parts:

    -   **Queued Outputs:**

        Lists the outputs that are either waiting to be generated or are under generation process. You can also find the output generation setting or preset used for the queued task, the type, user who initiated the task, time since when the task is queued, and the current status.

    -   **Generated Outputs**

        Lists the output tasks that have been completed. Again, the information shown in this is similar to the Queued Outputs section, with the only difference of the output generation time.

        In this list, you could have tasks that have executed successfully or tasks that failed. For the tasks that have completed successfully, the publishing process creates a log file \(logs.txt\) that can be accessed by clicking the link in the Generated At column.

> **How to define attributes on multiple cells, entire row, or column of a table**
>
> You can define attributes at the cell, row, or column level
>
> <details>
> <summary>Show steps</summary>
>
> You can also define attributes on multiple cells, entire row, or column of a table. For example, to align table cell, drag and select the required cell. In the Content Properties panel (on the right), the property **Type** changes to **entry**.
>
> 1. In the **Attributes** section, select **+Add**.
> 1. Select the `@valign` attribute from the **Attribute** dropdown list.
> 1. From the value dropdown list, select the desired text alignment you want to apply on the selected table cells.
> 1. Select **Add.**
>
> ![](images/align-table-cell_cs.png)
>
> </details>



**Define attributes on multiple cells, entire row, or column of a table**

You can define attributes at the cell, row, or column level.

<details>
<summary>Show steps</summary>

You can also define attributes on multiple cells, entire row, or column of a table. For example, to align table cell, drag and select the required cell. In the Content Properties panel (on the right), the property **Type** changes to **entry**.

1. In the **Attributes** section, select **+Add**.
1. Select the `@valign` attribute from the **Attribute** dropdown list.
1. From the value dropdown list, select the desired text alignment you want to apply on the selected table cells.
1. Select **Add.**

    ![](images/align-table-cell_cs.png)

    </details>

>[!BEGINSHADEBOX]
>
> **How to define attributes on multiple cells, entire row, or column of a table**
>
> You can define attributes at the cell, row, or column level.
>
> <details>
> <summary>Show steps</summary>
>
> You can also define attributes on multiple cells, an entire row, or a column of a table. For example, to align a table cell, drag and select the required cell. In the Content Properties panel (on the right), the **Type** property changes to **entry**.
>
> 1. In the **Attributes** section, select **+Add**.
> 1. Select the `@valign` attribute from the **Attribute** dropdown.
> 1. From the **Value** dropdown, select the desired text alignment.
> 1. Select **Add**.
>
> ![](images/align-table-cell_cs.png)
>
> </details>
>
>[!ENDSHADEBOX]




**Parent topic:**[Generate output of FrameMaker documents](fm-output-generatation.md)

