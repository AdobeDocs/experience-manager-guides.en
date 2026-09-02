# Configure AI Assistant in Agentic Mode

AI Assistant in Agentic mode makes tagging your content faster, easier, and more consistent. Using the agentic Smart Tagging skill from Adobe CX Enterprise Coworker, AI Assistant analyzes your content and recommends relevant tags based on your organization's taxonomy, instead of you manually reading through content to decide which tags apply. You stay in control by reviewing the suggested tags and choosing to apply or reject them before confirming your selection, significantly reducing manual effort, improving tagging accuracy, and ensuring consistent metadata across your documentation.

Configuration depends on whether your environment uses **Unified Shell** setting and whether users log in through **SSO** or **non-SSO** authentication. Follow the steps in this article that match your environment.

## Prerequisite

Your organization must be onboarded to **CX Enterprise Coworker** before you configure AI Assistant in Agentic mode. Contact your Adobe representative to confirm onboarding is complete before proceeding.

## Configure AI Assistant based on your environment

Use the following table to identify which configuration path applies to your users, then follow the corresponding steps.

| Unified Shell | Login type | Configuration required |
|---|---|---|
| Enabled | SSO | No additional configuration. Everything works out of the box. |
| Enabled | Non-SSO | Configure a technical account. |
| Disabled | SSO | Configure a technical account. |
| Disabled | Non-SSO | Configure a technical account. |

### Users with Unified Shell enabled

**SSO login**

If Unified Shell is enabled and your users log in through SSO, no additional configuration is required. AI Assistant in Agentic mode works automatically once your organization is onboarded to CX Enterprise Coworker.

**Non-SSO login**

If Unified Shell is enabled but your users log in without SSO, you must [Add IMS configuration to the environment](#add-ims-configuration-to-the-environment) below.

### Users with Unified Shell disabled

If Unified Shell is disabled, you must [Add IMS configuration to the environment](#add-ims-configuration-to-the-environment) for both:

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

## Enable the Agentic mode

Once the configuration is complete for your environment, contact the **Customer Success team** to enable the Agentic mode.