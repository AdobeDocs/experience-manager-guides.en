---
title: Activate output
description: Activate output of DITA maps in AEM Guides. Learn how to activate your content on the publishing instance.
exl-id: 4da644b9-8c5f-4976-a212-960085b693b8
feature: Publishing, Bulk Activation
role: User
---
# Activate output {#id214GGF00V5U}

Once you have created a map collection for bulk activation, the next step is to activate your content on the publishing instance. To activate your content, perform the following steps:

1.  Select **Guides** from the list of tools.

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.

1.  Click on the **Bulk Publish Dashboard** tile.

    A list of bulk activation map collections are displayed.

1.  Select the collection that you want to publish and click **Open**.

    ![](images/bulk-activation-collection-open.png){width="800" align="left"}

1.  \(*Optional*\) Apply the required filters from the left rail to filter map on the basis of their modified \(status\), output preset, or language.

    >[!NOTE]
    >
    >Generate the output for the map using the output preset before activating them in the map collection. 

     
You can view the ways to activate your collection based on your setup.

<details>
<summary> Cloud Services </summary> 

![bulk-collection-publish on cloud service](images/bulk-activation-collection-quick-publish-CS.png){width="650" align="left"}

You can activate the output to the **Preview** or **Publish** instances.

 **Preview**

* To activate the output of selected maps, select the pregenerated map output and select **Publish to** > **Preview**.
*	To activate the output of all DITA maps with their configured presets, select the checkbox next to the **Map** column, and then select **Publish to** > **Publish**.
   
  
**Publish**

* To activate the output of selected maps, select the pregenerated map output and select **Publish to** > **Publish**.

 *  To activate the output of all DITA maps with their configured presets, select the checkbox next to the Map (column), and then select **Publish to** > **Publish**.


   >[!NOTE] 
   > 
   > The checkbox near a **Map** is enabled only if you have genrated the output for a map.

A success message is displayed when the map output is queued for publishing.

Once the output is activated for the selected map files, the audit history tab is updated, and the latest activated output appears on top. The **Published** column is updated with the publishing date and time. 

</details>

<details>    
<summary>  On-premise Software </summary>


Do one of the following:

-  To activate output of selected maps, select the pregenerated map output and select **Quick Publish**.
-  To activate the output of all DITA maps with their configured presets, select the checkbox next to the Map (column), and then select **Quick Publish.**
    ![bulk-collection-publish](images/bulk-activation-collection-quick-publish.png){width="650" align="left"}
   
   >[!NOTE] 
   > 
   > The checkbox near a **Map** is enabled only if you have genrated the output for a map.

A success message is displayed when the map output is queued for publishing.

Once the output is activated for the selected map files, the audit history tab is updated, and the latest activated output appears on top. The **Published** column is updated with the publishing date and time. 

**Parent topic:**[Bulk Activation of published content](conf-bulk-activation.md)
