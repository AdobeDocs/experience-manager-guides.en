---
title: Incremental output generation
description: Learn how incremental output generation for AEM Sites works in AEM Guides. 
exl-id: 019d9fbf-2f23-4669-8022-d693be75c1c3
feature: Publishing
role: User
---

# Incremental output generation

>[!NOTE]
>
> Incremental output generation is applicable only for AEM Sites output. Also, you can only regenerate DITA \(.dita/.xml\) topics from a DITA map or sub-maps. If you select a DITA map, sub-map, topic group, or a topic with `@processing-role="resource-only"`, then the regenerate option is not available.

There could be a number of instances where you would update only a few topics in your DITA map and push only those updated topics live. To handle such scenarios, Experience Manager Guides allows you to create incremental outputs. If you have updated a few topics, you do not need to regenerate the entire DITA map. You can select only the updated topics and regenerate them.

If your map is chunked and you have updated a single topic in that map, then you need to regenerate the entire map for the updated topic or content to reflect in the output. You will not get the output regeneration option at a topic level, it is only available at the \(chunked\) map level. This is applicable to the parent map and all sub-maps.

Perform the following steps to regenerate output for a specific topic or a group of topics:

## Generate incremental output from Map console (using composite component mapping)

Perform the following steps to generate incremental output for AEM Sites using Map console:

1. [Open the DITA map file in Map console](./open-files-map-console.md).
1. Select the AEM Sites preset for which you want to generate incremental output.
1. In the **Topics** tab, select the topics that you want to publish. 

    - Without baseline 
    
       ![aem sites topic list](images/aem-presets-topic-list.png) {align="left"}

    - With baseline

       ![aem sites topic list with baseline](images/aem-presets-topic-list-new.png) {align="left"}

    >[!NOTE] 
    >
    > When a Baseline is selected in the **Content** tab, the Topic list displays topics and their versions from the attached Baseline.<br><br>
    > The incremental publishing from the Topics list should be used only when there is no change to the structure of the map. If there is a change in the map structure/TOC, then the entire map should be published once to update the TOC.

1. Select **Save** to save the changes.
1. Select **Generate output** to generate the output.


## Generate incremental output from Map dashboard (using legacy component mapping)

Perform the following steps to generate incremental output for AEM Sites using map dashboard:

1.  In the Assets UI, navigate to and select the DITA map file.

    The DITA map console appears with the list of Output Presets available to generate output.

1.  Select the **Topics** tab.

    A list of topics available in the DITA map is displayed.

1.  Select the topics that you want to regenerate.

    >[!NOTE]
    >
    > If you have added new topics to the DITA map, you will not be able to generate those new topics from here. You must first publish the newly added topics by using the DITA map publish function.

    ![](images/regenerate-topics.png){align="left"}

1.  Select **Regenerate**.

    The **Regenerate Selected Topics** page appears.

1.  Select the output preset that you want to use to regenerate the selected topics.

    When creating AEM Sites output preset using legacy component mapping, if a baseline is selected, the topic versions included in that baseline are used for output generation. Additionally, incremental publishing from the Topics list should be used only when there are no changes to the map structure. For details on using AEM site preset, view [AEM Sites presets on the map dashboard](./generate-output-aem-site-map-dashboard.md).


1.  Select **Regenerate** to start the output generation process.


>[!IMPORTANT]
>
> If you rename a topic title and regenerate the topic, the updated topic title does not reflect in the DITA map table of contents. To update the topic title in the TOC, you must generate the entire DITA map.

You can view the current status of the output generation request in the **Outputs** tab. For more information, view [View the status of the output generation task](#view-the-status-of-the-output-generation-task).



**Parent topic:** [Understanding the output presets](generate-output-understand-presets.md)
