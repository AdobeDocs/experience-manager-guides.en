---
title: Configure Workfront in Adobe Experience Manager Guides 
description: Learn how to Configure Workfront in Experience Manager Guides
feature: Workfront Configuration
role: Admin
level: Experienced
---
# Configure Workfront

Adobe Workfront is a cloud-based work management solution that helps teams and organizations plan, track and manage their work efficiently. The native integration between Adobe Workfront and Adobe Experience Manager Guides provides you with a unified workspace to seamlessly author and manage content, as well as allocate and track tasks. 

Learn more about [Workfront integration with Adobe Experience Manager Guides](../user-guide/workfront-integration.md)

## Prerequisites 

Before getting started, ensure that: 

1. You have the Administrator access to both Adobe Workfront and Experience Manager Guides. 2. 
2. You have created the [Experience Manager Guides Custom form](#create-experience-manager-guides-custom-form). 

### Get Started 

Perform the following steps to configure Workfront in Experience Manager Guides. 

1. Open the **Tools panel** and select **Guides**.  
2. Select **Configure Workfront**. 
3. On the **Workfront Configuration** page, enter the full URL of your organization's Workfront Domain, Client ID, and Client Secret Key.  
   
   To access the **Client ID** and **Client Secret** key configured in your Workfront setup, navigate to `Setup >> oAuth2 Applications`. 

    For more details about configuring your Workfront Domain, view [Create OAuth2 applications for Workfront integrations](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/configure-integrations/create-oauth-application) 
4. Select **Login and verify** to validate the authentication.  
5. Select [Experience Manager Guides Custom form](#create-experience-manager-guides-custom-form).  

## Create Experience Manager Guides Custom form

To map Experience Manager Guides workflows with Workfront, [create a new custom form](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/customize/custom-forms/design-a-form/design-a-form) by specifically adding the below fields: 

| Field type | Label| Name | Choices (Show values enabled) |
|------------|------|------|-------------------------------|
|Single-select dropdown | Task Type | task-type | Authoring, Publishing, Translation, Review | 
|Single-select dropdown | Task State | task-state  | Authoring, Review | 
|Text with formatting|Author List   | author-list  |  - | 
|Text with formatting|Reviewer List   | reviewer-list  | -  |
|Single line text| Review URL   | review-url  | - |

Select **Close and Save**, and then **Apply** to save the changes.  

Once configured, [add users to Adobe Workfront](https://experienceleague.adobe.com/en/docs/workfront/using/administration-and-setup/add-users/create-manage-users/add-users) using the same email addresses they have in Experience Manager Guides. 



