---
title: Conditional attribute profiling
description: Learn how to create conditional attributes in AEM Guides. Use conditional attributes in the folder and global profiles to conditionalize your content.
feature: Publishing
role: User
hide: true
exl-id: f8397acf-acd3-4e68-adce-9adbbef55337
TQID: https://experienceleague.adobe.com/ZnmDICfuJvf66QBUIwCE5NA6iVlXl2XIzfJed2E6GiE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
---
# Conditional attribute profiling {#id1843I0HN0Y4}

At an enterprise level, it is extremely important to ensure that you have a standard tagging system in place. Tags or conditional attributes can be associated with digital assets in the repository, which helps in publishing output based on the chosen conditions. For example, you can create conditional attribute for Windows and Mac content. Then, you add these attributes to the relevant content in your topics. At the time of publishing content, you can choose whether you want to publish Windows or Mac only content.

AEM Guides allows you to easily create and associate conditional attributes using the relevant DITA attributes. You can define conditional attributes at the global level or folder level. The globally defined conditions are visible across all projects and folder-specific conditions are visible only in projects created within the specified folder. Content authors can use these conditional attributes to conditionalize content in their DITA topics or maps that they create or use. These conditions can then be used by the publisher to create conditional presets. Using the conditional presets, the publisher can decide which condition to include and exclude from the published output.

>[!NOTE]
>
> You can create or edit the conditional attributes in a Folder Profile that you have access to. If your system administrator has not given you access to a folder profile, you cannot create or edit the conditional attributes in the Folder Profile.

To define conditional attributes, perform the following steps:

1.  Click on the Adobe Experience Manager link at the top and choose **Tools**.

1.  Select **Guides** from the list of tools.

1.  Click on the **Folder Profiles** tile and select a Folder Profile.

    >[!NOTE]
    >
    > You cannot edit the global profile.

1.  Click on the **Conditional Attributes** tab and click **Edit**.

    The Conditional Attributes table is shown.

1.  Click **Add**.

1.  Enter the **Name**, **Value**, and a **Label** for the attribute.

    You can save a profile with only the attribute name. However, an attribute can only be used when it has a value specified to it. If you specify both - value and label for an attribute, the Web Editor would still show only the value of the attribute. The label is shown to the publishing administrator at the time of creating conditional preset.

    The following screenshot shows the definition for the `platform` attribute with value of `unix` and a label of `Red Hat Linux`.

    ![](images/add-profile.png){width="800"}

1.  If you want to add more values for the same attribute, click the **+** icon and enter additional value and label.

1.  If you want to add more attributes, click **Add**.

1.  Click **Save** to save the changes.


The `platform` attribute is stored in the system. Whenever an author decides to use the `platform` attribute in a DITA topic in a folder, they will see the values in the Properties tab in the Web Editor.

![](images/properties-tab.png){width="350"}

**Parent topic:**[Output generation](generate-output.md)
