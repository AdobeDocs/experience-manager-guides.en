---
title: Set up and configure GitLab for Edge Delivery Services
description: Learn how to configure GitLab repositories, access tokens, Cloud Manager, webhooks, and Bring Your Own Git to publish content from Experience Manager Guides to Edge Delivery Services.
feature: Output Generation
role: Admin
level: Experienced
---

# Set up and configure GitLab for Edge Delivery Services

Learn how to configure GitLab as the publishing repository for Edge Delivery Services (EDS) using Adobe Experience Manager Guides.

To publish content to EDS using GitLab, you must configure repositories on both GitHub and GitLab. The GitHub repository is used to create the EDS site through the AEM Code Sync app, while the GitLab repository stores the content published from Experience Manager Guides.

## Prerequisites

Before you begin, ensure that you have:

- Access to GitHub and GitLab to create and configure repositories.
- Access to Cloud Manager to configure repositories, webhooks, and EDS sites.
- System Administrator or API Developer permissions in your Adobe organization to configure the Cloud Manager API integration.

## Create and configure the repositories

### Create the GitHub repository

[Create a GitHub repository using the AEM Guides boilerplate template](configure-eds.md#create-a-github-repository-for-eds).

The GitHub repository contains the files required to create the EDS site, including the `fstab.yaml` file that defines the content source.

### Create the GitLab repository

Create a separate GitLab repository to store the content published from Experience Manager Guides.

1. Sign in to GitLab.
2. Create a new repository using the same AEM Guides boilerplate template. You can import the GitHub template into GitLab or use a mirrored template.
3. Enter a repository name, for example, `my-eds-gitlab`.
4. Create the repository.

The GitLab repository serves as the publishing destination for the generated EDS content.

### Configure the mountpoint URL

Update the mountpoint URL in the GitHub repository to point to the GitLab repository.

1. Open the `fstab.yaml` file in your GitHub repository.
2. Configure the content source URL using the following format:

   ```text
   https://<worker URL>/<account type>/<git acc domain>/<git username>/<git repo>/main/docs
   ```

   Specify the following values:

   | Parameter | Description |
   |---|---|
   | `<worker URL>` | Worker node URL provided by Adobe. |
   | `<account type>` | Set to `gitlab`. |
   | `<git acc domain>` | GitLab domain, such as `gitlab.com`, or your self-hosted GitLab domain. |
   | `<git username>` | Your GitLab username. |
   | `<git repo>` | Name of the GitLab repository. |
   | `main` | Branch name (default). |
   | `docs` | Root folder where the published files are committed. |

3. Commit the changes to the `main` branch.

### Configure AEM Code Sync

Install the AEM Code Sync app on the GitHub repository to create the EDS site.

For detailed instructions, see [Connect GitHub to Adobe via AEM Code Sync](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/kb-articles/publishing/configure-eds#connect-github-to-adobe-via-aem-code-sync).

After installing the app, save the generated **Live URL**. You will need it when adding the EDS site to Cloud Manager.

The live URL follows this format:

```text
https://<branch>--<github-repo>--<github-username>.aem.live
```

## Configure GitLab authentication

Create a project access token to allow Experience Manager Guides to authenticate and publish content to the GitLab repository.

1. Open the GitLab repository.
2. Navigate to **Settings** > **Access tokens** and select **Add new token**.
3. Specify the following details:
   - **Token name:** Enter a descriptive name, for example, `AEM Guides EDS`.
   - **Expiration date:** Set an expiration date according to your organization's policy.
   - **Role:** Select **Developer**.
   - **Scopes:** Select `api` to allow reading, adding, editing, and deleting files in the repository.
4. Select **Create project access token**.
5. Copy and securely store the generated token. The token is displayed only once.

You will need this token when configuring the GitLab publish profile in Experience Manager Guides.

**Note:** Renew the access token before it expires and update it in the publish profile. Publishing fails if the token has expired.

## Configure Cloud Manager

### Add the GitLab repository

1. Open Cloud Manager.
2. Navigate to **Repositories** > **Add Repository**.
3. Specify the following details:
   - **Name:** Enter a display name for the repository.
   - **Repository path:** Enter the full URL or path of your GitLab repository.
4. Select **Save**.

### Generate an API key using Adobe Developer Console

Create an API integration in Adobe Developer Console to generate the API key required for authenticating the Cloud Manager webhook URL.

1. Navigate to [Adobe Developer Console](https://developer.adobe.com/console).
2. Select **Create new project** or open an existing project.
3. Optionally, select **Edit project** to update the project title and description.
4. Select **Add to Project** > **API**.
5. Under **Experience Cloud**, select **Cloud Manager**, and then select **Next**.
6. Select **OAuth Server-to-Server** as the authentication type.
7. Select the appropriate **Product Profile** to assign the integration to a Cloud Manager role.
8. Select **Save configured API**.
9. Copy the generated **Client ID (API Key)**.

You will need the Client ID when configuring the GitLab webhook.

### Configure the GitLab webhook

Configure a webhook to notify Cloud Manager whenever changes are pushed to the GitLab repository.

1. In Cloud Manager, locate the GitLab repository added earlier.
2. Select **Config Webhook**.
3. Copy the **Webhook URL** and **Secret** displayed in the dialog.
4. Append the Client ID generated in Adobe Developer Console to the webhook URL using the following format:

   ```text
   <webhook URL from Cloud Manager>&api-key=<CLIENT_ID>
   ```

5. Open your GitLab repository.
6. Navigate to **Settings** > **Webhooks** > **Add webhook**.
7. Specify the following details:
   - **Payload URL:** Enter the complete Cloud Manager webhook URL with the API key appended.
   - **Secret Token:** Enter the secret copied from Cloud Manager.
   - **Branch:** Select the branch to monitor, for example, `main`.
   - **Events:** Select at least **Push events**.
8. Save the webhook.

The GitLab repository is now connected to Cloud Manager.

### Add the EDS site to Cloud Manager

Add the EDS site created through AEM Code Sync to Cloud Manager.

**Important:** Do not create the EDS site directly from Cloud Manager. Sites created through Cloud Manager do not have the administrative rights required to modify content and settings. Create the site using AEM Code Sync, and then add it to Cloud Manager.

1. In Cloud Manager, navigate to the **Edge Delivery** section.
2. Select **Add Site**.
3. Specify the following details:
   - **Name:** Enter a display name for the site.
   - **Live URL:** Enter the live URL generated by AEM Code Sync.
   - **Description:** Optionally, enter a description.
4. Select **Add**.

### Connect the GitLab repository using Bring Your Own Git

Use Bring Your Own Git (BYOG) to connect the GitLab repository registered in Cloud Manager to the EDS site.

1. In Cloud Manager, navigate to the **Edge Delivery** section.
2. Locate the EDS site.
3. Select **Bring Your Own Git (BYOG)**.
4. Select the GitLab repository from the list.
5. Select **Confirm**.
6. Copy and securely store the secret key generated by Cloud Manager.

You will need this secret when configuring the Site Admin Tool.

## Configure the Site Admin Tool

Configure the Site Admin Tool to connect the EDS site to the GitLab repository through Cloud Manager.

### Configure the content source

1. Open the **Site Admin Tool** for your EDS site.
2. Locate your site. The site name is derived from the GitHub live URL using the following format:

   ```text
   <branch>--<github-repo>--<github-username>
   ```

3. Select **Edit Source**.
4. Enable **Bring Your Own Git**.
5. Specify the following details:
   - **Content Source URL:** Enter the same GitLab content source URL configured in the `fstab.yaml` file.
   - **Owner:** Enter the Cloud Manager Program ID, available in the webhook URL under `/program/<PROGRAM_ID>/`.
   - **Repo:** Enter the Cloud Manager Repository ID, available in the webhook URL under `/repo/<REPO_ID>/`.
6. Save the changes.

### Configure the Cloud Manager secret

1. In the Site Admin Tool, select **Manage Secrets**.
2. Add a new secret with the following values:
   - **Key name:** Enter `cm-byog`.
   - **Value:** Enter the secret generated by Cloud Manager when configuring BYOG.
3. Select **Create**.

**Note:** Use `cm-byog` as the exact secret key name.

The EDS site is now connected to Cloud Manager and the GitLab repository.

## Publish content to EDS using GitLab

After completing the GitLab configuration, create an EDS publish profile in Experience Manager Guides.

1. Follow the instructions in [Create the EDS publish profile](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/kb-articles/publishing/configure-eds#create-the-eds-publish-profile).
2. Select **GitLab** as the **Git account type** and provide the required repository details.
3. Enter the project access token generated earlier in the **Access token** field.
4. Save the publish profile.

To publish your content, follow the instructions in [Create an Output preset for EDS and generate output](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/kb-articles/publishing/configure-eds#create-an-output-preset-for-eds-and-generate-output).

Select the GitLab publish profile when configuring the output preset.

The generated content is committed to the `docs` folder in your GitLab repository and can be accessed through the EDS site.