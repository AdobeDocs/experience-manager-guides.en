# Connecting AEM Guides with Guides Knowledge AI (Beta)

>[!IMPORTANT]
>
> Contact your Customer Success team to enable this feature.


This article provides Administrators and Content engineers with the end-to-end process for configuring Guides Knowledge AI access and uploading AEM Guides content for consumption within Knowledge AI. 

## Process at a glance

| Step | What you'll do |
|---|---|
| **1** | Create a Service Account in Adobe Developer Console and configure it for your environment. |
| **2** | Retrieve the technical account email from the Service Account credentials file. |
| **3** | Grant the Service Account access in Knowledge AI by creating a role and adding the user. |
| **4** | Configure a Knowledge AI output preset in AEM Guides and upload content. |


## Prerequisites

Ensure you have the following access and permissions before starting:

| Requirement | Purpose |
|---|---|
| **Adobe Developer Console** | Create the Service Account and download its JSON credentials. |
| **AEM Guides** | Author content and configure the output preset for Knowledge AI. |
| **Knowledge AI ([guidesai.adobe.io](https://guidesai.adobe.io/))** | Manage roles and users, and receive the uploaded content. |
| **Permission: Create Service Accounts** | Required in Adobe Developer Console to complete Step 1. |
| **Permission: Manage users & roles in Knowledge AI** | Required to grant the Service Account access in Step 3. |


## Step 1: Create a Service Account

Knowledge AI uses a Service Account to securely authenticate and access content.

1. Follow the instructions in [Configure Microservices IMT Configuration](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/kb-articles/publishing/configure-microservices-imt-config)

2. Create a new Service Account and download the generated JSON credentials file.

3. Configure the required environment settings using the downloaded credentials.

Once completed, the Service Account should be successfully associated with your environment.

>[!NOTE]
>
> If you have already created and configured a Service Account for your environment, you can skip and directly move to next step.


## Step 2: Retrieve the Technical Account Email

Identify the Service Account to grant access to Knowledge AI.

1. Open the downloaded Service Account JSON file.
2. Search for the field named `technical_account_email`.

You should see a value similar to the following:

```json
{
  "technical_account_email": "a1b2c3d4e5f6@techacct.adobe.com"
}
```

3. Copy the email address associated with `technical_account_email`.

You'll use this email address in the next step.

## Step 3: Grant Access in Knowledge AI

Add the Service Account to Knowledge AI with the appropriate permissions to allow it to manage and upload content.

1. Open [Knowledge AI](https://guidesai.adobe.io/).
2. Navigate to **Security → Roles** and create a role with the minimal required permissions.
3. Navigate to **Security → Users → Add User**. Add a new user using the `technical_account_email` copied from the Service Account JSON, select the domains from the **Domains** dropdown, and assign the role created in the previous step.

The Service Account is now authorized to perform content administration and upload operations.

## Step 4: Configure a Knowledge AI Preset and Upload Content

Once you have set up permissions, configure AEM Guides to publish content to Knowledge AI.

### Create the Preset

1. Open the AEM Guides Map console.
2. Navigate to Output Presets.
3. Create a new preset for Knowledge AI ingestion.

### Upload Content

1. Open the configured Knowledge AI preset.
2. Select the domain for which the role was granted to the `technical_account_email`, then select **Upload Content**.
  This triggers the content upload workflow to Knowledge AI. Wait for the upload process to complete.
5. After the upload is complete, click **Open in Knowledge AI**. This opens the Knowledge AI chat within the domain, using the uploaded content.

You have configured the Service Account, granted permissions, and made your AEM Guides content available in Knowledge AI. Repeat [Step 4](#step-4-configure-a-knowledge-ai-preset-and-upload-content) whenever you publish updated content.

## Reference Links

| Resource | Link |
|---|---|
| **Configure Microservices IMT Configuration** | [Experience League documentation](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/kb-articles/publishing/configure-microservices-imt-config) |
| **Knowledge AI** | [guidesai.adobe.io](https://guidesai.adobe.io/) |
