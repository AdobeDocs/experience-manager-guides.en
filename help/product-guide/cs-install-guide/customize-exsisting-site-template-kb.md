---
title: Download and install AEM Sites templates
description: Learn how to Download and install AEM Sites templates
feature: Installation
role: Admin
level: Experienced

---
# General Instructions to customize existing AEM Site templates for AEM Guides

This guide provides step-by-step instructions to customize existing AEM Site templates for use with AEM Guides to generate AEM Sites from DITA maps and topics.

If you are using the out-of-the-box AEM Guides (AEMG Docs) template, the configurations and components are already in place and can be used as-is to publish your AEM Guides content. However, if you want to use your existing AEM Sites templates with custom branding to publish AEM Guides content, follow the steps below to align your sites templates with AEM Guides rendering requirements.


## Prerequisites

- You have appropriate permissions and access to AEM Templates.
- You understand AEM editable templates and AEM Site structure.
- You have an existing site hierarchy built using editable templates.
- You have at least two templates from your existing project:

    - Documentation Container Page Template used for rendering the DITA map as a documentation root.
    - Topic Page Template used to render individual DITA topic pages.

## Template naming considerations

Template names will vary based on project setup. For example, in the OOTB AEMG Docs configuration:

- Documentation Container Page Template:  /conf/AEMG-Docs-Site/settings/wcm/templates/kb-content

- Topic Page: /conf/AEMG-Docs-Site/settings/wcm/templates/topic-content

## Customization

The customization process involves two major steps:

1. Template setup: Identify and configure the two templates (container and topic).
2. Render Guides components: Embed required AEM Guides components to enable features like TOC, navigation, and metadata display.

## Template setup

Choose and configure two editable templates from your AEM site.

### Documentation Container Page Template
  
The Documentation Container Page template is used to create the Product Documentation Container Page rendering the content of a DITA map.

- It serves as the entry point or homepage for a specific set of documentation (e.g., a product manual or guide).
- Add id="category-page" property to the jcr:content of the template, This ensures all pages created from this template are automatically treated as documentation containers by AEM Guides.
- Add a Text component with the mandatory property: text="$category.html$".
- Typically includes navigation elements, such as links to sections or topics within the documentation.
- It can be customized to include branding, headers, footers, and other design elements.

**Example Use Case:**
If you have a DITA map for a product manual, the documentation container page template will generate the homepage for that manual, displaying an overview and links to individual topics.

### Topic Page Template

- The Topic Page template is used to create pages for individual DITA topics.
- Each topic in a DITA map is rendered as a separate page using this template.
- Contains a Text component with the mandatory property:
text="$topic.content$".
- This placeholder is replaced with the actual content of the DITA topic during site generation.
    - The text component is typically placed inside a Container Component to ensure proper layout and styling.
    - Can be customized to include consistent headers, footers, and navigation elements across all topic pages.

**Example Use Case:**
If you have a DITA topic about "Installation Instructions," the topic page template will generate a page displaying the content of that topic.

**Container component:**

>[!NOTE]
>
> Ensure that components using sling:resourceType under wcm/foundation/components are migrated to the corresponding core/wcm/components.

Add the same (container and text component) in the structure of the same template:

## Render Guides Components in customized templates

To enable core AEM Guides components features such as Table of Contents, page redirection, navigation, and metadata display, you need to include specific AEM Guides components in your custom templates. These components must be explicitly added to the corresponding editable templates (Documentation Container Page or Topic Page) to ensure the intended functionality is available during site generation and runtime.

Refer to the table below for the list of components and their usage:

## Component use cases

- **Redirect Component (childredirect):** Add this to the documentation container page template so that product home page generated from the DITA map automatically redirect to the first topic page. If your documentation container page is designed to act as a standalone homepage with custom components and layout, this component is not required.

- **Table of Contents (guidessidenavigation):** Add this to the topic page template to render a navigable TOC alongside the topic content. The TOC is derived from the DITA map and helps users navigate across sibling topics.


## Enabling Guides Client Libraries

By default, the client libraries (clientlibs) provided in the AEM Guides components package are not applied to custom templates. To enable them:

1. **Edit the Template:**

    1. Open the **Product Page** in **Editor Mode**.
    2. Click **Edit Template** (this will open a URL like editor.html/conf/<site-name>/settings/wcm/templates/<template-name>/structure.html).

2. **Update Page Policy:**

    1. Go to the Page Information button and select Page Policy.
    2. Add the following client libraries:
        - Client Libraries
        - Client Libraries JavaScript Page Head

3. Save the template after adding the required client libraries.        


>[!NOTE]
>
> * Ensure that the templates are tested in a non-production environment before deploying to production.
> * Refer to the official AEM Guides and AEM Sites documentation for additional details.
