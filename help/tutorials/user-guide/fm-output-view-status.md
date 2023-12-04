---
title: View the status of the output generation task
description: View the output generation queue of FrameMaker documents. Learn how to view the status of an output generation task.
exl-id: c358f747-f0a5-4d9e-a96f-20f30663101f
---
# View the status of the output generation task {#viewing_output_history}

Once you initiate the output generation task for a FrameMaker document, AEM Guides sends this task to the output generation queue. This queue is updated in real time, showing the status of each output generation task in the queue.

Perform the following steps to view the output generation queue:

1.  In the Assets UI, navigate to and click FrameMaker document for which you want to check the output generation status.

1.  Click Outputs.

    ![](images/output-queued-fm.png){width="800" align="left"}

1.  The Outputs page is divided into two parts:

    -   **Queued Outputs:**

        Lists the outputs that are either waiting to be generated or are under generation process. You can also find the output generation setting or preset used for the queued task, the type, user who initiated the task, time since when the task is queued, and the current status.

    -   **Generated Outputs**

        Lists the output tasks that have been completed. Again, the information shown in this is similar to the Queued Outputs section, with the only difference of the output generation time.

        In this list, you could have tasks that have executed successfully or tasks that failed. For the tasks that have completed successfully, the publishing process creates a log file \(logs.txt\) that can be accessed by clicking the link in the Generated At column.


**Parent topic:**[Generate output of FrameMaker documents](fm-output-generatation.md)
