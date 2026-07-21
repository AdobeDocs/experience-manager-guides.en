---
title: Create and use Template Presets for output generation
description: Learn about creating and using Template Presets for output generation in Adobe Experience Manager Guides.
---

# Create and use template presets for output generation

Template Presets allow administrators to standardize output preset configurations across multiple DITA maps. Instead of configuring the same output preset individually for every map, you can define a preset as a template and apply it to all maps associated with a folder profile.

This capability helps you to maintain consistent publishing configurations across projects and reduces manual configuration effort.

> [!NOTE]
>
> - Template presets can only be created and managed by **Administrators** and **Folder Profile Administrators**.
> - Template presets are intended for configuration management and are not used directly for output generation.

## Benefits

Using Template Presets provides the following advantages:

-  Ensures consistent publishing configurations across multiple maps.
-  Reduces manual effort by eliminating repetitive preset configuration.
-  Enables centralized management of output preset settings.
-  Allows Administrators to enforce organization-wide publishing standards.

## Create a template preset

1. Configure the Folder profile you want to use
2. Open **Output presets** from the Map console for the associated folder.
3. Create or select the output preset that you want to use as a template.
4. Select the **Set as tempalte** from the **Options** menu for the preset.

    ![](images/template-preset.png){width="350"}

5. Select **Apply Preset Changes** , to apply the preset changes to all existing maps of the selelcted folder profile. 

    Apply Preset Changes dialog opens.

    ![](images/apply-preset-change.png){width="350"}

6. To **Overwrite the existing presets**, select teh Check box. Select **Ok**.

    A Confirm action dialog opens pointing to how many maps does the preset changes applies to.

    ![](images/confirm-preset-change.png){width="350"}

7. Select Ok.

The selected output preset is converted into a Template Preset.

> [!NOTE]
>
> Any existing output generated from the preset remains available.However, once a preset is converted into a template, it can no longer be used to generate new output directly.


## Supported output types

Template Presets are supported for all the output preset types except the following:

-   Edge Delivery Services
-   Knowledge Base
-   SCORM

## Output generation behavior

Template Presets are configuration templates and are not intended for direct publishing.

When a preset is marked as a template:

-   **Generate output** is disabled.
-   The template cannot be used directly for publishing.
-   Existing generated outputs remain accessible if they were created
    before the preset was converted into a template.



