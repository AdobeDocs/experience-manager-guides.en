---
title: Increase translation performance for your DITA files in AEM guides 
description: Best Practices, tips and tricks to increase DITA translation project performance in AEM Guides 
feature: Translation
role: User, Admin

---
# Best practices to follow for translation in AEM Guides 

Performance for your translation project may decrease as translation activity on the system increases over the time.

Each translation project generates multiple user groups for access, leading to an increase in the number of user groups within the system. As the number of user groups expands, it can gradually slow down CRUD operations related to user permissions, potentially affecting overall AEM performance. Additionally, if translation projects remain active after completion, it can negatively impact the performance of translation synchronization between AEM and the translation vendor.

**Following the best practices outlined below will help maintain an efficient environment.**

## If you are on older build than  4.6(on-prem) or 2404(cloud):

-  Mark all projects as "Inactive" once translation is complete and approved.The project remains available for review and is simply marked as inactive.
    - Following these steps will help maintain overall translation performance in good health.
![Inactive Translation Project ](../assets/translation/translation-project-image1.png)

- For older projects folder, which is marked as inactive, approved and reviewed should be deleted
    - Following these steps will help maintain overall translation performance in good health by cleaning up temporary translation files and user groups associated with this project folder.
![Delete Translation Project and folder  ](../assets/translation/translation-project-image2.png)
   

## If you are on, build 4.6 or 2404 or later:

You can continue to follow the same steps as mentioned above. Starting with version 4.6/2404, AEM Guides introduces an editor setting for administrators to disable the automated deletion of translation projects.

Refer : [Automatically delete or disable a completed translation project](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/user-guide/author-content/create-preview-topics/author-content-aem-guides/work-with-web-editor/translate-documents-web-editor#automatically-delete-or-disable-a-completed-translation-project)

![Automated settings to delete and disable translation project  in AEM Guides  ](../assets/translation/translation-project-image3.png)