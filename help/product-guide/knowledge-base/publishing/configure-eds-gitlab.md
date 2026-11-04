---
title: Set up and configure GitLab for Edge Delivery Services
description: Learn how to configure GitLab repositories, access tokens, Cloud Manager, webhooks, and Bring Your Own Git to publish content from Experience Manager Guides to Edge Delivery Services.
feature: Output Generation
role: Admin
level: Experienced
---

# Set up and configure GitLab for Edge Delivery Services

To publish content from Experience Manager Guides to Edge Delivery Services (EDS) using GitLab, you connect a GitLab repository to your EDS site through Cloud Manager's *Bring Your Own Git* (BYOG) capability. This article lists the steps in sequence. For details on each step, follow the linked documentation.

## How it works

- A **GitHub repository** creates the EDS site through the AEM Code Sync app.
- A **GitLab repository** stores the content published from Experience Manager Guides.
- **Cloud Manager** links the two by receiving GitLab push events (webhook) and syncing them to the EDS site.

## Prerequisites

- Access to GitHub and GitLab (GitLab.com or self-hosted) to create repositories and tokens.
- Access to Cloud Manager, with a role that allows adding repositories (Deployment Manager or Business Owner).
- System Administrator or API Developer role in your Adobe organization to create the Cloud Manager API integration.
- An `aem.live` organization registered in the configuration service. Learn more in [Configuration service setup](https://www.aem.live/docs/config-service-setup).

## Configuration sequence

1. [Create the EDS site using GitHub](#1-create-the-eds-site-using-github)
2. [Create the GitLab repository](#2-create-the-gitlab-repository)
3. [Configure the mountpoint URL](#3-configure-the-mountpoint-url)
4. [Create GitLab access tokens](#4-create-gitlab-access-tokens)
5. [Add the GitLab repository to Cloud Manager](#5-add-the-gitlab-repository-to-cloud-manager)
6. [Generate a Cloud Manager API key](#6-generate-a-cloud-manager-api-key)
7. [Configure the GitLab webhook](#7-configure-the-gitlab-webhook)
8. [Add the EDS site to Cloud Manager](#8-add-the-eds-site-to-cloud-manager)
9. [Connect the repository using Bring Your Own Git](#9-connect-the-repository-using-bring-your-own-git)
10. [Configure the EDS site to use Cloud Manager](#10-configure-the-eds-site-to-use-cloud-manager)
11. [Sync and verify](#11-sync-and-verify)
12. [Publish from Experience Manager Guides](#12-publish-from-experience-manager-guides)

### 1. Create the EDS site using GitHub{#1-create-the-eds-site-using-github}

Create a GitHub repository from the AEM Guides boilerplate and install the AEM Code Sync app on it. Save the generated **Live URL** (`https://<branch>--<github-repo>--<github-username>.aem.live`) for later.

For steps, view [Create a GitHub repository for EDS](./configure-eds.md#create-a-github-repository-for-eds) and [Connect GitHub to Adobe via AEM Code Sync](./configure-eds.md#connect-github-to-adobe-via-aem-code-sync).

>[!IMPORTANT]
>
> Do not create the EDS site using the one-click option in Cloud Manager. Sites created that way do not give you the admin permissions required for the later steps. Learn more in [Prepare your Edge Delivery Services site](https://www.aem.live/developer/byo-git#1.-prepare-your-edge-delivery-services-site).

### 2. Create the GitLab repository{#2-create-the-gitlab-repository}

Create a separate GitLab repository (for example, `my-eds-gitlab`) from the same AEM Guides boilerplate. Experience Manager Guides publishes the generated output to this repository. EDS expects a `main` branch.

To create the repository, either create a blank project and push the contents of [aem-guides-boilerplate](https://github.com/adobe/aem-guides-boilerplate) to it, or import the boilerplate into a new project. For steps, view [Create a project](https://docs.gitlab.com/user/project/) and [Import your project from GitHub to GitLab](https://docs.gitlab.com/user/project/import/github/) in the GitLab documentation.

### 3. Configure the mountpoint URL

In the GitHub repository, update `fstab.yaml` so the content source points to the GitLab repository, and commit the change to `main`.

```text
https://<worker URL>/gitlab/<git acc domain>/<git username>/<git repo>/main/docs
```

| Parameter | Description |
|---|---|
| `<worker URL>` | Worker node URL provided by Adobe. |
| `<git acc domain>` | GitLab domain, such as `gitlab.com`, or your self-hosted domain. |
| `<git username>` | Your GitLab username. |
| `<git repo>` | Name of the GitLab repository. |
| `main` / `docs` | Branch and root folder. Defaults for Experience Manager Guides. |

### 4. Create GitLab access tokens

Create the access token(s) required for:

- **Cloud Manager**, to validate and access the repository. Learn more in [Add external repositories in Cloud Manager](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager/content/managing-code/external-repositories).
- **Experience Manager Guides publish profile**, to commit published output. Create a GitLab project access token with the **Developer** role and the `api` scope. Learn more in the [GitLab documentation](https://docs.gitlab.com/ee/user/project/settings/project_access_tokens.html).

>[!NOTE]
>
> Renew tokens before they expire. Publishing fails if the token in the publish profile has expired. To update a token used by Cloud Manager, view [Manage access tokens for external repositories](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager/content/managing-code/manage-access-tokens).

### 5. Add the GitLab repository to Cloud Manager

In Cloud Manager, go to **Repositories** > **Add Repository**, select **Private Repository**, and validate ownership using the access token. Wait until the repository status is **Ready**. The BYOG option is available only after at least one external repository is Ready.

For steps, view [Add external repositories in Cloud Manager](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-manager/content/managing-code/external-repositories).

### 6. Generate a Cloud Manager API key

Create an API integration in Adobe Developer Console (**Cloud Manager** API, **OAuth Server-to-Server**) and copy the **Client ID (API Key)**.

For steps, view [Creating an API integration project](https://developer.adobe.com/experience-cloud/cloud-manager/guides/getting-started/create-api-integration).

### 7. Configure the GitLab webhook

In Cloud Manager, select **Config Webhook** for the repository and copy the **Webhook URL** and **Secret**. Append the API key to the URL (`<webhook URL>&api-key=<CLIENT_ID>`). In GitLab, go to **Settings** > **Webhooks**, add the URL and secret, select the `main` branch, and enable **Push events**.

For details, view [Configure your external repository in Cloud Manager](https://www.aem.live/developer/byo-git#2.-configure-your-external-repository-in-cloud-manager).

### 8. Add the EDS site to Cloud Manager

In Cloud Manager, go to **Edge Delivery** > **Add Edge Delivery Site** and enter the Live URL saved in step 1. Complete the ownership validation.

For steps, view [Add an Edge Delivery site](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/implementing/using-cloud-manager/edge-delivery-sites/add-edge-delivery-site).

### 9. Connect the repository using Bring Your Own Git

On the EDS site in Cloud Manager, select **Bring Your Own Git (BYOG)**, choose the GitLab repository, and confirm. Copy and securely store the generated secret. It is shown only once, and a new secret is generated if you reconfigure the site.

For details, view [Configure your Edge Delivery site in Cloud Manager](https://www.aem.live/developer/byo-git#3.-configure-your-edge-delivery-site-in-cloud-manager).

### 10. Configure the EDS site to use Cloud Manager

Set the EDS site's code source to the Cloud Manager repository, using the **Program ID** (`/program/<PROGRAM_ID>/`) and **Repository ID** (`/repo/<REPO_ID>/`) from the webhook URL. Then create a secret named exactly `cm-byog` with the secret from step 9.

For the Admin API calls, view [Configure your AEM site to use Cloud Manager](https://www.aem.live/developer/byo-git#4.-configure-your-aem-site-to-use-cloud-manager).

### 11. Sync and verify

In Cloud Manager, select **Sync Code** from the site's menu and choose the `main` branch. Then open `https://main--<site>--<org>.aem.page` to verify the site.

For details, view [Trigger your first sync](https://www.aem.live/developer/byo-git#5.-trigger-your-first-sync) and [Verify your AEM site](https://www.aem.live/developer/byo-git#6.-verify-your-aem-site).

### 12. Publish from Experience Manager Guides

Create an EDS publish profile with **Git account type** set to **GitLab**, using the project access token from step 4. Then select this profile in an EDS output preset and generate the output. The output is committed to the `docs` folder of the GitLab repository.

For steps, view [Create the EDS publish profile](./configure-eds.md#create-the-eds-publish-profile-for-github-or-gitlab) and [Create an Output preset for EDS and generate output](./configure-eds.md#create-an-output-preset-for-eds-and-generate-output).

## Troubleshooting

- **Site shows old content after a push:** Verify that the webhook is delivering events to Cloud Manager, then check the status of the latest sync job.
- **Sync error `Unable to fetch hlxignore: 401`:** The `cm-byog` secret is incorrect. Re-create it with the secret from step 9.
- **Repository linked to another site:** A Cloud Manager repository can be linked to only one site at a time. To share a repository across sites, use [Repoless](https://www.aem.live/docs/repoless).

For more details, view [Troubleshooting in Bring Your Own Git](https://www.aem.live/developer/byo-git#troubleshooting).
