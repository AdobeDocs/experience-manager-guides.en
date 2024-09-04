---
title: Increase translation performance for your DITA files in AEM guides 
description: Best Practices , tips and tricks to increase DITA translation project performance in AEM Guides 
feature: Translation
role: User, admin

---
# Best practices to follow for translation in AEM Guides 

Performance for your translation project may decrease as translation activity on system increases over the time.

Each translation project generates multiple user groups for access, leading to a  increase in the number of user groups within the system . . As the number of user groups expands, it can gradually slow down CRUD operations related to user permissions, potentially affecting overall AEM performance. Additionally, if translation projects remain active after completion, it can negatively impact the performance of translation synchronization between AEM and the translation vendor.

**We should follow below  best practices to keep using environment in efficiently way**

## If you are  on older build than  4.6(on-prem) or 2404(cloud ):

-  Mark all projects as "Inactive" once translation is complete and approved.( Project will be available for review and will just be marked as inactive )
    - This will help you keep your overall translation performance in good health.
![Inactive Translation Project ](../assets/translation/translation-project-image1.png)

- For older projects folder  which are marked as inactive , approved and reviewed should be deleted
    - This will help you keep overall AEM performance in good health by cleaning up temporary translation files and user groups associated with this project folder.
![Delete Translation Project and folder  ](../assets/translation/translation-project-image2.png)
   

## If you are on build 4.6 or 2404 or later  :

You can continue to follow the same steps as mentioned above, but starting with version 4.6/2404, AEM Guides has introduced an editor setting (for administrators) that allows you to disable the automated deletion of translation projects.

Refer : [Automatically delete or disable a completed translation project](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/user-guide/author-content/create-preview-topics/author-content-aem-guides/work-with-web-editor/translate-documents-web-editor#automatically-delete-or-disable-a-completed-translation-project)

![Automated settings to delete and disable translation project  in AEM Guides  ](../assets/translation/translation-project-image3.png)




