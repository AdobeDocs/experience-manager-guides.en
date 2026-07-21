# Create and use Template Presets for output generation

Template Presets allow administrators to standardize output preset configurations across multiple DITA maps. Instead of configuring the same output preset individually for every map, you can define a preset as a template and apply it to all maps associated with a folder profile.

This capability helps you to maintain consistent publishing configurations across projects and reduces manual configuration effort.

> [!NOTE]
>
> - Template presets can only be created and managed by **Administrators** and **Folder Profile Administrators**.
> - Template presets are intended for configuration management and are not used directly for output generation.

## Create a template preset

1. Configure the Folder profile you want to use
2. Open **Output presets** from the Map console for the associated folder.
3. Create or select the output preset that you want to use as a template.
4. Select the Set as tempalte from the context menu for the preset
4. From the **More** (**...**) menu, select **Set as template**.

The selected output preset is converted into a Template Preset.

> **NOTE**
>
> Any existing output generated from the preset remains available.
> However, once a preset is converted into a template, it can no longer
> be used to generate new output directly.

## Apply a Template Preset to a Folder Profile

After creating a Template Preset, you can associate it with a Folder
Profile so that its configuration is available for all maps within that
profile.

When applying the template, Experience Manager Guides displays the
number of maps that will be updated before you confirm the operation.

The template configuration is then propagated to all eligible maps
within the selected Folder Profile.

## Manage Template Presets

Template Presets are centrally managed to ensure configuration
consistency.

Only users with one of the following roles can perform template-related
operations:

-   Administrator
-   Folder Profile Administrator

Other users can use the output presets inherited from the template but
cannot modify the template configuration.

## Supported output types

Template Presets are supported for most output preset types.

The following output types are currently **not supported**:

-   Edge Delivery Services
-   Knowledge Base
-   SCORM

## Output generation behavior

Template Presets are configuration templates and are not intended for
direct publishing.

When a preset is marked as a template:

-   **Generate output** is disabled.
-   The template cannot be used directly for publishing.
-   Existing generated outputs remain accessible if they were created
    before the preset was converted into a template.

## Benefits

Using Template Presets provides the following advantages:

-   Ensures consistent publishing configurations across multiple maps.
-   Reduces manual effort by eliminating repetitive preset
    configuration.
-   Enables centralized management of output preset settings.
-   Allows administrators to enforce organization-wide publishing
    standards.

## Feature availability

> **NOTE**
>
> Template Presets are available only when the corresponding feature is
> enabled for your Experience Manager Guides environment. Contact your
> Adobe representative or Customer Success team if the feature is not
> available in your instance.

## Suggested placement

Insert this section after **Create an output preset** and before
**Generate output using an output preset** in the existing article.
