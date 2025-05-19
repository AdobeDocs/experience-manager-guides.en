---
title: Configure Adobe Workfront in Experience Manager Guides
description: Learn how to Configure Workfront in Experience Manager Guides
feature: Authoring
role: Admin
level: Experienced
exl-id: 1f72642c-e694-47cd-9182-f4f4aaf69655
---
# Configure Adobe Workfront

Adobe Workfront is a cloud-based work management solution that helps teams and organizations plan, track and manage their work efficiently. The integration between Experience Manager Guides and Adobe Workfront gives you access to robust project management features on top of Experience Manager Guides core CCMS capabilities, allowing you to plan, allocate, and track tasks efficiently.  

Learn more about [Adobe Workfront integration](../user-guide/workfront-integration.md) in Experience Manager Guides.

## Prerequisites 

Before getting started, ensure that: 

1. You have standard access to Adobe Workfront and administrator access to Experience Manager Guides.
2. You [create a new custom form in Adobe Workfront](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/customize/custom-forms/design-a-form/design-a-form) required for Experience Manager Guides by specifically using the below fields: 

    | Field type | Label| Name | Choices (Show values enabled) |
    |------------|------|------|-------------------------------|
    |Single-select dropdown | Task Type | task-type | Authoring (value = AUTHOR), Publishing (value = PUBLISH), Translation (value = TRANSLATION), Review (value = REVIEW) | 
    |Single-select dropdown | Task State | task-state  | Authoring (value = AUTHOR), Review (value = REVIEW)| 
    |Text with formatting|Author List   | author-list  |  - | 
    |Text with formatting|Reviewer List   | reviewer-list  | -  |
    |Single line text| Review URL   | review-url  | - |
    |Single line text| Task URL   | task-url  | - |
    |Single Line Text | Email subject  | email-subject  | - |

>[!NOTE]
>
> In the above table, the choices represent the options available under the **Task type** field. For each option, you would require to provide the **task name** and **task value**. The name and values for each task type must be exactly same as mentioned in the above table. For example, for task type Author, provide **Authoring** as name and **AUTHOR** as its corresponding value.
> When working with on-prem services, always ensure that `localhost` is replaced with the correct server address in the **Day CQ Link Externalizer** configuration to properly receive the resolved task link in the email notifications.  

## Get started 

Perform the following steps to configure Adobe Workfront in Experience Manager Guides. 

1. Open the **Tools panel** and select **Guides**.  
2. Select **Configure Workfront**. 

   The **Workfront configuration** page is displayed.

   ![](assets/configure-workfront-page.png) 
     
3. On the **Workfront configuration** page, enter the full URL of your organization's Workfront domain, Client ID, and Client Secret key.  
   
   To access the **Client ID** and **Client Secret** key configured in your Adobe Workfront setup, navigate to `Setup >> Systems>> oAuth2 Applications`. 

    For more details about configuring your Adobe Workfront domain, view the Authorization code flow section in [Create OAuth2 applications for Workfront integrations](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/configure-integrations/create-oauth-application#create-an-oauth2-application-using-user-credentials-authorization-code-flow).

4. Select **Login and verify**. 

   You are redirected to the Adobe Workfront Sign in page.
5. Sign in using your Adobe Workfront email address, and then select **Allow access** to let the Oauth2 application access your respective Adobe Workfront account.

   You are automatically redirected to the Workfront configuration page on Experience Manager Guides. 

6. In the custom form dropdown list, select the Adobe Workfront custom form that you created for Experience Manager Guides. View [Prerequisites](#prerequisites).
7. Select **Save and close** to apply and save the Workfront configuration changes.  

Once configured, [add users to Adobe Workfront](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/add-users/create-manage-users/add-users) using the same email addresses they have in Experience Manager Guides.
