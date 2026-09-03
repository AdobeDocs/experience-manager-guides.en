---
title: Configure AI Assistant in Agentic mode
description: Learn how to configure the Agentic AI Assistant in Experience Manager Guides
---

# Configure AI Assistant in Agentic mode

As an Administrator, you can configure AI Assistant in Agentic mode for your organization in Experience Manager Guides. The configuration steps vary depending on whether Unified Shell setting is enabled in your AEM as a Cloud Service environment, and whether the users are logged in through SSO or non-SSO authentication. This article walks you through the configuration process for each scenario.

## Prerequisite

Your organization must be onboarded to **CX Enterprise Coworker** before you configure AI Assistant in Agentic mode. 

## Configure AI Assistant based on your environment

Use the following table to identify which configuration path applies to your users, then follow the corresponding steps.

| Unified shell | Login type | Configuration required |
|---|---|---|
| Enabled | SSO | No additional configuration. Everything works out of the box|
| Enabled | Non-SSO | Add IMS configuration to the environment |
| Disabled | SSO | Add IMS configuration to the environment |
| Disabled | Non-SSO | Add IMS configuration to the environment |

### Users with Unified shell enabled

**SSO login**

If Unified shell is enabled and your users log in through SSO, no additional configuration is required. AI Assistant in Agentic mode works automatically once your organization is onboarded to CX Enterprise Coworker.

**Non-SSO login**

If Unified shell is enabled but your users log in without SSO, you must [Add IMS configuration to the environment](#add-ims-configuration-to-the-environment) below.

### Users with Unified shell disabled

If Unified shell is disabled, you must [Add IMS configuration to the environment](#add-ims-configuration-to-the-environment) for both:

- SSO login
- Non-SSO login

## Add IMS configuration to the environment

Perform the following steps to add the IMS configuration to the environment:

1. Open Experience Manager and then select your program which contains the environment you want to configure.

2. Switch to the **Environments** tab.

3. Select the environment name which you want to configure. This navigates you to the **Environment Information** page.

4. Switch to the **Configuration** tab.

5. Paste the JSON service details (downloaded when you created the IMS configuration in Adobe Developer Console) into the **Value** field corresponding to `SERVICE_ACCOUNT_DETAILS`. Ensure that you use the same name and configuration expected by the environment.

> [!NOTE]
> If you have not yet created the OAuth/IMS credentials for your environment, do so first in Adobe Developer Console before completing this step.

![ims service account configuration](assets/ims-service-account-config.png){width="800"}

## Enable the Agentic mode

Once the configuration is complete for your environment, contact the **Customer Success team** to enable the Agentic mode.