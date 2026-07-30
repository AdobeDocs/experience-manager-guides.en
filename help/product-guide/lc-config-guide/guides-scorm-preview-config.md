---
title: Generate SCORM output
description: Learn how to generate a SCORM output in the Product Training and Learning
feature: Authoring
role: User
---

# Configuring Content Security Policy (CSP) for SCORM preview

Experience Manager Guides SCORM preview is managed through a dedicated cloud variable that governs the Content Security Policy (CSP) applied to the preview experience. This variable allows Administrators to enable or disabled the setting. After the setting is enabled, Administrators can extend it with additional trusted sources including scripts, styles, fonts, images, media, frames, and more required by their SCORM packages to load and render the preview correctly in AEM.

This article walks you through adding and configuring the cloud variable in Cloud Manager, explains what each field in the JSON value controls, and shows how to update the value later if your requirements change.

## Configuration values

The variable `GUIDES_SCORM_PREVIEW_CONFIG` accepts a single JSON object as its value. Each key controls a specific aspect of the CSP applied during SCORM preview:

| Value | Type | Description |
|---|---|---|
| `CSP_ENABLED` | boolean | Turns CSP enforcement on (`true`) or off (`false`) for the SCORM preview. This is `true` by default. |
| `ALLOW_UNSAFE_EVAL` | boolean | Allows the use of `eval()` and similar unsafe JavaScript evaluation methods when set to `true`. |
| `ADDITIONAL_SCRIPT_SRC` | Array | Additional trusted sources allowed to serve JavaScript. |
| `ADDITIONAL_STYLE_SRC` | Array | Additional trusted sources allowed to serve stylesheets. |
| `ADDITIONAL_FONT_SRC` | Array | Additional trusted sources allowed to serve fonts. |
| `ADDITIONAL_FRAME_SRC` | Array | Additional trusted sources allowed to be loaded within `<iframe>` elements. |
| `ADDITIONAL_IMG_SRC` | Array | Additional trusted sources allowed to serve images. |
| `ADDITIONAL_MEDIA_SRC` | Array | Additional trusted sources allowed to serve audio/video content. |
| `ADDITIONAL_WORKER_SRC` | Array | Additional trusted sources allowed to serve web workers. |
| `ADDITIONAL_CONNECT_SRC` | Array | Additional trusted sources the preview is allowed to connect to (e.g., XHR/fetch calls). |
| `ADDITIONAL_MANIFEST_SRC` | Array | Additional trusted sources allowed to serve web app manifests. |
| `ADDITIONAL_OBJECT_SRC` | Array | Additional trusted sources allowed to be loaded via `<object>`, `<embed>`, or `<applet>`. |


## Default values

```json
{
  "CSP_ENABLED": true,
  "ALLOW_UNSAFE_EVAL": false,
  "ADDITIONAL_STYLE_SRC": ["https://fonts.googleapis.com"],
  "ADDITIONAL_FONT_SRC": ["https://fonts.gstatic.com"],
  "ADDITIONAL_FRAME_SRC": ["https://www.youtube-nocookie.com", "https://www.youtube.com"],
  "ADDITIONAL_SCRIPT_SRC": [],
  "ADDITIONAL_WORKER_SRC": [],
  "ADDITIONAL_IMG_SRC": [],
  "ADDITIONAL_MEDIA_SRC": [],
  "ADDITIONAL_CONNECT_SRC": [],
  "ADDITIONAL_MANIFEST_SRC": [],
  "ADDITIONAL_OBJECT_SRC": []
}
```
Depending on your project, you don't need to populate every value, leave any source type as an empty Array if you don't need to allow additional origins for it.

> [!NOTE]
>
> If you want to disable CSP enforcement for SCORM preview, set `"CSP_ENABLED": false` in the JSON value. This disables the CSP variable altogether for that environment.

## Adding the variable in Cloud Manager

1. **Sign in to Cloud Manager** and select the program and the environment where you want to apply the configuration.
2. Navigate to the environment's Configuration section.
3. Select **Add/Update** to add a configuration orenvironment variable.

    ![](assets/add-new-variable.png){width="650"}

4. Enter the name of the variable in the **Name** field, `GUIDES_SCORM_PREVIEW_CONFIG`.

    ![](assets/variable-name.png){width="650"}

5. Enter your complete JSON configuration, along with the source allow-lists your project needs into the **Value** field.
6. Select the **Service Applied** to choose whether the variable should apply to **Author**, **Publish**, or both. For Guides authoring, select **Author**.
7. Select the **Type** as variable.
8. Select **Add**.
9. Select **Save**.
    
    ![](assets/save.png){width="650"}

Once saved, Cloud Manager applies the configuration to the selected environment. Wait for the update to propagate. Applying the configuration to the environment typically takes 10 - 12 minutes. Once complete, the new configuration will be active for SCORM preview on that environment.

## Update the variable values

If your requirements change, the `GUIDES_SCORM_PREVIEW_CONFIG` variable can be revisited at any time from the same Configuration section in Cloud Manager. Locating the existing variable and selecting its **Add/Update** option opens it for editing, allowing the JSON value to be revised as needed. 