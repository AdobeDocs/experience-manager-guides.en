---
title: Activate output
description: Activate output of DITA maps in AEM Guides. Learn how to activate your content on the publishing instance.
feature: Publishing, Bulk Activation
role: User
hide: true
exl-id: de1fd057-60c6-4b1a-9e55-f32969eb0079
TQID: https://experienceleague.adobe.com/DjyZb6keMyvxaRF39lD1-xsugNBJPxP-WqfNnMEU-T4
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: c38bc65b-dea9-4a6e-9de3-3daf1d2b388b
    internal-label: Bulk activation
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Activate output {#id214GGF00V5U}

Once you have created a map collection for bulk activation, the next step is to activate your content on the publishing instance. To activate your content, perform the following steps:

1.  Select **Guides** from the list of tools.

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.

1.  Click on the **Bulk Publish Dashboard** tile.

    A list of bulk activation map collections is displayed.

1.  Select the collection that you want to publish and click **Open**.

    ![](images/bulk-activation-collection-open.png){width="800"}

1.  \(*Optional*\) Apply the required filters from the left rail to filter map on the basis of their modified \(status\), output preset, or language.

    >[!NOTE]
    >
    >Generate the output for the map using the output preset before activating them in the map collection. 

     
View the different ways to activate your collection based on your setup.

<details>
<summary> Cloud Services </summary> 

![bulk-collection-publish on cloud service](images/bulk-activation-collection-quick-publish-CS.png){width="650"}

You can activate the output to the **Preview** or **Publish** instances.

 **Preview**

* To activate the output of selected maps, select the pregenerated map output and select **Publish to** > **Preview**.
* To activate the output of all DITA maps with their configured presets, select the checkbox next to the **Map** column, and then select **Publish to** > **Publish**.
   
  
**Publish**

* To activate the output of selected maps, select the pregenerated map output and select **Publish to** > **Publish**.

 *  To activate the output of all DITA maps with their configured presets, select the checkbox next to the Map (column), and then select **Publish to** > **Publish**.


   >[!NOTE] 
   > 
   > The checkbox for a map output is enabled only if you have generated the output for a map.

A success message is displayed when the map output is queued for publishing.

Once the output is activated for the selected map files, the audit history tab is updated, and the latest activated output appears on top. The **Published** column is updated with the publishing date and time. 

</details>

<details>    
<summary>  On-premise Software </summary>


Do one of the following:

*  To activate the output of selected maps, select the pregenerated map output and select **Quick Publish**.
*  To activate the output of all DITA maps with their configured presets, select the checkbox next to the Map (column), and then select **Quick Publish.**
    ![bulk-collection-publish](images/bulk-activation-collection-quick-publish.png){width="650"}
   
   >[!NOTE] 
   > 
   >The checkbox for a map output is enabled only if you have generated the output for a map.


A success message is displayed when the map output is queued for publishing.

Once the output is activated for the selected map files, the audit history tab is updated, and the latest activated output appears on top. The **Published** column is updated with the publishing date and time. 

**Parent topic: **[Bulk Activation of published content](conf-bulk-activation.md)
