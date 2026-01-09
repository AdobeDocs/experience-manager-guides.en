---
title: Component mapping for New AEM Sites
description: Learn how to do Component mapping for New AEM Sites
feature: Installation
role: Admin
level: Experienced

---
# Component mapping in New AEM Sites 

The article talks about the various aspects of component mapping for AEM sites 

## Component mapping rules

Use a JSON array of rules (your `componentmapping.json`) to convert HTML into components. Keep the rules as simple, explicit, and specific as possible.

### Target the HTML element and its class

- Write the HTML tag name in `name`.
- Include the CSS class applied on that element in `class`, if class exists.
  Example:

    ```html
    <div class ="sample-class">
    <p> Sample html element </p>
    </div>

    ```

    ```json
    {
    "name": "div",
    "class": "sample-class",
    "resourceType": "example/components/name",
    "attributeMap": []
    }
    ```
    
>[!NOTE]
>
>* `name` can be a comma-separated list (e.g., `"h1, h2"`).
>* `class` must be present on the element (all listed classes must match).

### Use attributeMap to save properties on the JCR node

Add entries to `attributeMap` to set properties on the output node. Each entry produces `attrs[to] = value`.
Common patterns:

```json
// copy an attribute
{ "attribute": "src", "to": "image-src" }
// read content or tag name
{ "from": "textContent", "to": "jcr:title" }
{ "from": "outerHTML",  "to": "text" }
{ "from": "innerHTML",  "to": "text" }
{ "from": "name",       "to": "type" }  // the tag name, e.g., "h2"
// constant value
{ "value": true, "to": "textIsRich" }
```

Below is an example for HTML to JSON for an image element.

```html
<img src="/content/dam/aemg-docs/tragopan.svg" class="cmp-image__image" itemprop="contentUrl" data-cmp-hook-image="image" alt="">
```

```json
{
    "name": "img",
    "resourceType": "core/wcm/components/image/v2/image",
    "attributeMap": [
      {
        "from": "src",
        "to": "fileReference"
      },
      {
        "value": ["fileReference"],
        "to": "path-attributes"
      }
    ]
  }
```

### Normalize paths via a dedicated entry

If you want to normalize (make absolute) values, declare which attribute keys should be normalized using:

```json
{
  "value": ["text"],
  "to": "path-attributes"
}
```

Ensure to take care of the following important points:

- Put the list of property names you want normalized in `value` (e.g., `["text"]`, or `["href", "src"]`).
- The system will normalize any values found under those property names when building the final component.


### Extract HTML values before splitting into components

Use `from` to specify how to read a value from the element before the document is split into separate components:

- `"textContent"`: plain text of the element
- `"outerHTML"`: the element and its inner markup
- `"innerHTML"`: the element's inner markup only
- Any other string: treated as an attribute name (e.g., `"src"`, `"href"`)


Examples:

```json
{ "from": "textContent", "to": "jcr:title" }
{ "from": "outerHTML",  "to": "text" }
{ "from": "innerHTML",  "to": "snippet" }
{ "from": "src",        "to": "image#src" }
```

### Minimal end-to-end example in componentmapping.json

```json
[
  {
    "name": "h1, h2",
    "class": "topic-title",
    "resourceType": "core/wcm/components/title/v2/title",
    "attributeMap": [
      { "from": "textContent", "to": "text" },
      { "from": "name",        "to": "type" }
    ]
  },
  {
    "name": "img",
    "class": "hero",
    "resourceType": "example/components/hero-image",
    "attributeMap": [
      { "from": "src", "to": "image#src" },
      { "value": ["image#src"], "to": "path-attributes" }
    ]
  },
  {
    "name": "#element",
    "resourceType": "core/wcm/components/text/v2/text",
    "attributeMap": [
      { "from": "outerHTML", "to": "text" },
      { "value": true,        "to": "textIsRich" }
    ]
  }
]
```

Define the element and class to target, use `attributeMap` to set the node properties, add a `path-attributes` entry to normalize paths, and pick the right `from` for the values you want to extract.

>[!NOTE]
>
>It is important to discuss the default rich text and identify the elements for which it is utilized.

## Build a custom component

Learn how to create a custom table component that displays images within its cells. This approach ensures a clean, reusable design for dynamic content. It covers what you'll build, why it's effective, the key prerequisites, high level design, and more. 

### What you'll build

A custom table component that accepts HTML table content and replaces every `<img>` inside it with the output of the AEM Core Image component. This lets you reuse Core Image's features (responsive images, alt handling, accessibility) while keeping full control over your table markup.
Using this approach, you can build other custom components for your new AEM site website.

### Why this approach

- **Reuse**: Leverage Core Image's mature behavior instead of re‑implementing it.
- **Consistency**: Images in your table behave the same as images elsewhere on the site.
- **Server‑side**: Images are rendered on the server for performance, SEO, and accessibility.

### Prerequisites

- AEM SDK running and this project checked out.
- Core components installed on your AEM instance.
- Maven available to build and deploy.

### High‑level design

- Author provides HTML for the table in the component dialog.
- A Sling Model parses that HTML, finds <img> tags, and for each image calls a service that renders the Core Image component server‑side.
- The model swaps the original <img> with the captured Core Image HTML and passes the completed HTML to HTL for output.

Your table is output once, already containing Core Image markup. No client‑side DOM manipulation is needed.

### Folder structure and key files (in this repo)

- Component HTL and clientlibs: `ui.apps/src/main/content/jcr_root/apps/guides-components/components/table/`
    - `table.html` (HTL renderer)
    - `_cq_editConfig.xml` (refresh listeners)
    - `clientlibs/` with `css.txt`, `js.txt`, `css/table.css`, `js/table.js`
- Sling Model: `core/src/main/java/com/adobe/guides/aem/components/core/models/TableModel.java`
- Image rendering service: `core/src/main/java/com/adobe/guides/aem/components/core/services/ImageComponentRenderer.java`

### Implementation steps

**Define the Table component (component node)**

Create the component under `apps/guides-components/components/table`. If you don't already have one, add a minimal `.content.xml` like below to register it in the side panel.

```xml
<?xml version="1.0" encoding="UTF-8"?>
<jcr:root xmlns:sling="http://sling.apache.org/jcr/sling/1.0"
          xmlns:jcr="http://www.jcp.org/jcr/1.0"
          jcr:primaryType="cq:Component"
          jcr:title="Table"
          componentGroup="Guides - Custom"/>
```

Indicates to AEM that this is a component available for authors to add to pages.

**Render with HTL and include styles**

Use a Sling Model and output the processed HTML. Include your clientlib category for CSS/JS.

```html
<sly data-sly-use.model="com.adobe.guides.aem.components.core.models.TableModel"
     data-sly-use.clientLib="/libs/granite/sightly/templates/clientlib.html">
</sly>
<sly data-sly-call="${clientLib.css @ categories='guides-components.table'}"></sly>
<sly data-sly-test="${wcmmode.edit && !model.hasContent}">
  <div class="cq-placeholder" data-emptytext="${component.title}"></div>
</sly>
<div data-sly-test="${model.hasContent}"
     class="gu-table-wrapper ${model.enableResponsive ? 'gu-table--responsive' : ''} gu-table--style-${model.tableStyle}"
     id="${model.componentId}">
  ${model.processedTableHtml @ context='unsafe'}
</div>
```

The model returns complete HTML with Core Image already rendered, so HTL just prints it.

**Add the Sling Model to process HTML and render Core Image**

The model reads dialog fields, parses the table HTML, finds each `<img>`, and replaces it with Core Image HTML via a service.

Following are some of the important knowhows for `TableModel`:

- Reads `tableHtml`, `enableResponsive`, `tableStyle` from resource properties.
- Uses Jsoup to parse and edit HTML safely.
- Calls `ImageComponentRenderer` to render Core Image and capture the HTML.
- Preserves CSS classes and style from the original `<img>`.
- Normalizes DAM paths (removes `/jcr:content/renditions/*`).

```java
@Model(adaptables = {Resource.class, SlingHttpServletRequest.class},
       defaultInjectionStrategy = DefaultInjectionStrategy.OPTIONAL)
public class TableModel {
  @ValueMapValue private String tableHtml;
  @ValueMapValue private boolean enableResponsive;
  @ValueMapValue private String tableStyle;
  @OSGiService private ImageComponentRenderer imageRenderer;
  // ...
  @PostConstruct
  protected void init() {
    // parse HTML, for each <img> build image props (fileReference, alt, title)
    // call imageRenderer.renderImageComponent(...)
    // replace <img> with returned Core Image HTML
  }
  public String getProcessedTableHtml() { /* return final HTML */ }
}
```

This centralizes the logic on the server and reuses Core Image behavior.

**Render Core Image via a service (server‑side include)**

`ImageComponentRenderer` renders the Core Image component and captures the output. It

- wraps a resource that forces `core/wcm/components/image/v2/image`.
- uses `RequestDispatcher#include` to render it.
- captures the response as a string.

```java
@Component(service = ImageComponentRenderer.class)
public class ImageComponentRenderer {
  private static final String IMAGE_RESOURCE_TYPE = "core/wcm/components/image/v2/image";
  public String renderImageComponent(Resource base, Map<String,Object> props,
                                     SlingHttpServletRequest req, SlingHttpServletResponse resp) {
    // create wrapped resource with IMAGE_RESOURCE_TYPE and props
    // dispatcher.include(...) with a response wrapper to capture HTML
    // return captured HTML
  }
}
```

This lets you **drop in** Core Image wherever you need it, not only as a child component.

**Client libraries**

Create a clientlib for small styles or future JS. The HTL above loads the `guides-components.table` category.

```
clientlibs/css.txt
  #base=css
  table.css
clientlibs/js.txt
  #base=js
  table.js
```

This keeps the styles/scripts modular and discoverable.

**Dialog fields (Author inputs)**

Add a dialog with at least these properties:

- **Table HTML**: `./tableHtml` (textarea);  the HTML of the table.
- **Enable responsive**: `./enableResponsive` (checkbox); toggles a responsive wrapper class.
- **Table style**: `./tableStyle` (select); applies a style modifier class.

These map 1:1 to the Sling Model's properties and control rendering.

**Allow the component on templates**

In the Template Editor, edit the Layout Container policy > Allowed Components > enable your Table component under **Guides - Custom**.

The Authors can't add components until policies allow them.

## Authoring tips

- Paste valid HTML for the table. The model sanitizes and adjusts image URLs.
- Use DAM asset paths for images; renditions are normalized to the original asset path.
- Provide alt text in the HTML when possible; otherwise, images are marked decorative.

## Constraints

- The service forces Core Image v2. To switch versions, update `IMAGE_RESOURCE_TYPE`.
- For synthetic rendering, the model replaces Core Image's generated `.coreimg.` URLs with direct DAM paths and removes `srcset` to avoid broken URLs.
- All rendering happens once on the server; JavaScript is optional.

## Quick reference (implementation)

- HTL: `ui.apps/.../components/table/table.html`
- Clientlibs: `ui.apps/.../components/table/clientlibs/`
- Model: `core/.../models/TableModel.java`
- Service: `core/.../services/ImageComponentRenderer.java`

This pattern shows how to compose a custom component with a Core Component server‑side, keeping your markup while reusing Core logic.



