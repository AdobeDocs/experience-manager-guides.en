---
title: Enabling Contextual Content Variables (CCVAR) in AEM Sites via AEM Guides
description: Working with Contextual Content Variables (CCVAR) in AEM Sites via AEM Guides
exl-id: 
feature: Web Editor
role: User, Admin
---
# Enabling Contextual Content Variables (CCVAR) in AEM Sites via AEM Guides

Contextual Content Variables (CCVAR) is an ACS Commons capability that enables authors to use dynamic content variables directly in their authored text. While CCVAR is commonly used in AEM Sites, this article explains how to achieve similar functionality via pages generated from content authored in **AEM Guides** *primarily by using keywords defined in the DITA map*.


## What are Contextual Content Variables (CCVAR)?

CCVAR allows authors to insert dynamic variables into their content, which are resolved at runtime based on the context. For example, variables like `((page_properties.pageTitle))` can dynamically pull the page title during content rendering.


## How to Enable CCVAR in AEM Sites Generated from AEM Guides?

Considering AEM Guides is used as the source of all content (including AEM Sites, PDF, or HTML5), to enable CCVARs on pages generated from AEM Guides, you need to use keywords to define the CCVAR name. To do this in Guides, define **keywords** in your DITA map using `<keydef>` elements. These keywords can correspond to dynamic values (or CCVAR names), allowing you to reference them in your DITA topics.


## Pre-requisites

Before proceeding, ensure the following pre-requisites are met:

1. **AEM ACS Commons Installed**:
   - Ensure that **ACS AEM Commons** is installed on your AEM instance. This is required for using CCVAR.

2. **Contextual Content Variables Configuration**:
   - Complete the setup for **Contextual Content Variables** in AEM using the [official documentation](https://adobe-consulting-services.github.io/acs-aem-commons/features/contextual-content-variables/index.html). This includes:
     - Enabling **Property Aggregation**.
     - Configuring **HTML Rewriting** (if using HTML output).
     - Configuring **JSON Rewriting** (if using JSON output).



## Steps to Enable CCVAR in AEM Guides

### 1. Define Keywords in the DITA Map

- In AEM Guides, define keywords using `<keydef>` elements in the DITA map to correspond to the CCVAR.
- For example:

```xml
  <keydef keys="product">
    <topicmeta>
      <keywords>
        <keyword>((page_properties.pageTitle))</keyword>
      </keywords>
    </topicmeta>
  </keydef>
```
  
- The `keys` attribute (`product` in this example) will be used to reference this variable in your DITA topics.


## 2. Use Keywords in DITA Topics

- In the topic, use the keyword wherever the CCVar is to be used.
- For example:

```xml
  <p>This is the title of the product: <keyword keyref="product"/> </p>
```
  
- The `keyref` attribute points to the `keys` value defined in the `<keydef>` element (`product` in this case).
- During output generation, the keyword will be replaced with the corresponding CCVar value.


## 3. Generate Output

- When you generate output for AEM Sites, the keyword references will be resolved to the corresponding dynamic values.
- For example:
  - If `((page_properties.pageTitle))` resolves to `My Product`, the output will display:

```xml
   This is the title of the product: My Product.
```


## Example Use Case

Suppose you want to dynamically insert the language of the page into your DITA topics. Here’s how you can achieve this:

1. **Define the Keyword in the DITA Map**:

```xml
   <keydef keys="pageLanguage">
     <topicmeta>
       <keywords>
         <keyword>((inherited_page_properties.jcr:language))</keyword>
       </keywords>
     </topicmeta>
   </keydef>
```

2. **Reference the Keyword in a DITA Topic**:

```xml
   <p>The title of this page is: <keyword keyref="pageLanguage"/>.</p>
```

3. **Generated Output**:

If `((inherited_page_properties.jcr:language))` resolves to `en`, the output will display:
    
```
     The language of this page is: en.
```

   
### Resources

For more details on **Contextual Content Variables**, refer to the official documentation:  
[Contextual Content Variables in AEM Commons](https://adobe-consulting-services.github.io/acs-aem-commons/features/contextual-content-variables/index.html)