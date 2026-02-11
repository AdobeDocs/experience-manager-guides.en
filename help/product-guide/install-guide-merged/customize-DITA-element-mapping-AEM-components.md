---
title: Customize DITA element mapping with AEM components
description: Learn how to Customize DITA element mapping with AEM components
feature: Output Generation
role: Admin
level: Experienced
---

# Customize DITA element mapping with AEM components {#id1679J600HEL}

DITA elements in the AEM Guides are mapped to their corresponding AEM components. AEM Guides uses this mapping in workflows such as publishing and review to convert DITA element to a corresponding AEM component. The mapping is defined in the `elementmapping.xml` file, which can be accessed using the package manager for Cloud Service setup and from the URL: `/libs/fmdita/config/elementmapping.xml` in the CRXDE Lite mode for On-Premise setup.

>[!NOTE]
>
> Do not make any customizations in the default configuration files available in the ``libs`` node. You must create an overlay of the ``libs`` node in the ``apps`` node and update the required files in the ``apps`` node only.

You may use the predefined DITA element mappings, or you can map DITA elements to your custom AEM components. To use your custom AEM components, you need to understand the structure of the `elementmapping.xml` file.

### elementmapping.xml structure 

A high-level overview of the `elementmapping.xml` structure is explained below:

1.  Every DITA element is first searched for a corresponding component mapping based on the element name. For example:

    ```XML
    <ditaelement>     
       <name>**substeps**</name>  
       <class>- topic/ol task/substeps</class>  
       <componentpath>dita/components/ditaolist</componentpath>  
       <type>COMPOSITE</type>  
       <target>para</target>
    </ditaelement>
    ```

    In the above example, all `substeps` DITA elements are rendered using the `dita/components/ditaolist` component.

1.  If a DITA element does not find a match based on the name, then a match on the basis of the `class` is done. For example:

    ```XML
    <ditaelement>  
       <name>topic</name>  
       <class>**- topic/topic**</class>  
       <componentpath>fmdita/components/dita/topic</componentpath>  
       <type>COMPOSITE</type>  
       <target>para</target>  
       <attributemap> 
          <attribute from="id" to="id" />  
       </attributemap>
    </ditaelement>
    ```

    In the above example, if there is no mapping defined for the `task` element, then the `task` element is mapped to the above component because `task` is inherited from the `topic` component.

1.  When an element has a corresponding component mapping, then further processing of its child elements is determined by `type`. For example:

    ```XML
    <ditaelement>  
       <name>title</name>  
       <class>- topic/title</class>  
       <componentpath>foundation/components/title</componentpath>  
       <type>**STANDALONE**</type>  
       <target>para</target>  
       <textprop>jcr:title</textprop>
    </ditaelement>
    ```

    `type` takes the following values:

    -   COMPOSITE: element to component *mapping continues for child elements* as well.

    -   STANDALONE: child elements of the current element are *not mapped further*.

    In the above example, if the `<title>` element has any child elements, they will not be mapped to any other component. The component for `<title>` element is responsible for rendering all child elements inside the `<title>` element.

1.  If there are multiple components mapped to a single DITA element, then the best match for the element is selected. To select the best match component, domain and structural specialization of DITA elements is considered.

    If there are DITA elements with domain specialization and a component is mapped for domain specialization, then that component is given high priority.

    Similarly, if there are DITA elements with structural specialization and a component is mapped for structural specialization, then that component is given high priority.

1.  You can use `<attributemap>` in element mapping to map attribute values to the corresponding node properties.
1.  `textprop` can be used for serializing the text content of a DITA element to a node property. In addition, it can be used multiple times in an element tag to serialize the text content at multiple locations in published hierarchy. You can also customize the location and name of the target property. For example:

    ```XML
    <ditaelement>
       <name>title</name>
       <componentpath>foundation/components/title</componentpath>
       <type>STANDALONE</type>
       <target>para</target>
        <textprop>**jcr:title**</textprop>
    </ditaelement>
    ```

    The above element mapping specifies that the text content of `<title>` element will be saved as value of a property named `jcr:title` on the output node.

1.  `xmlprop` can be used for serializing the entire XML for a given element to a node property. The component can then read this node property and do custom rendering. For example:

    ```XML
    <ditaelement>
        <name>svg-container</name>
       <class>+ topic/foreign svg-d/svg-container</class>
        <componentpath>fmdita/components/dita/svg</componentpath>
        <type>STANDALONE</type>
        <target>para</target>
       <xmlprop>**data**</xmlprop>
    </ditaelement>
    ```

    The above element mapping specifies that the entire XML markup for element `<svg-container>` will be saved as value of a property named `data` on the output node.

1.  There is a special attribute mapping to handle path resolution in output generation process. For example:

    ```XML
    <attributemap>
       <attribute from="href" to="fileReference" ispath="true" rel="source" />
       <attribute from="height" to="height" />
        <attribute from="width" to="width" />
    </attributemap>
    ```

    For the above `attributemap`, the `href` attribute in your DITA element will be mapped to a node property named `fileReference`. Now since `ispath` is set to `true`, the output generation process resolves this path and then sets it in `fileReference` node property.

    How this resolution happens is determined on the basis of value of the `rel` attribute in attribute mapping.

    -   If `rel=source`, then value of `href` is resolved with respect to the DITA source file that is currently being processed. The value of `href` is resolved and placed in the value of `fileReference` property.

    -   If `rel=target`, then value of `href` is resolved with respect to the root publish location. The value of `href` is resolved and placed in the value of `fileReference` property.

    If you do not want any pre-processing or resolution to happen on path attributes, then you need not specify the `ispath` attribute. The value is copied as is and the component can do the required resolution.


### DITA element schema 

Following is an example of the DITA element schema in `elementmapping.xml` file:

```XML
<ditaelement>        
    <name>element_name</name>    
    <class>element_class</class>    
    <componentpath>fmdita/components/dita/component_name</componentpath>    
    <type>COMPOSITE|STANDALONE</type>     
    <attributeprop>propname_a</attributeprop>      
    <textprop>propname_t</textprop>    
    <xmlprop>propname_x</xmlprop>     
    <xpath>xpath expression string</xpath>     
    <target>head|para</target>     
    <wrapelement>div</wrapelement>     
    <wrapclass>class_name</wrapclass>     
    <attributemap>         
        <attribute from="attrname"         to="propname"         ispath="true|false"         rel="source|target" />    
    </attributemap>    
    <skip>true|false</skip> 
</ditaelement>
```

The following table describes the elements in the DITA element schema:

|Element|Description|
|-------|-----------|
|`<ditaelement>`|The top-level node for each mapping element.|
|`<class>`|The class attribute of the target DITA element for which you are writing the component.<br> For example, the class attribute for the DITA topic is: <br> `- topic/topic`|
|`<componentpath>`|The CRXDE path of the mapped AEM component.|
|`<type>`|Possible values:<br> -   **COMPOSITE**: Process child elements as well <br> -   **STANDALONE**: Skips processing of child elements|
|`<attributeprop>`|Used for mapping serialized DITA attributes and values to AEM nodes as property. For example, if you have `<note type="Caution">` element and the component that is mapped for this element has `<attributeprop>attr_t</ attributeprop>`, then the node's attribute and value is serialized to `attr_t` property of the corresponding AEM node \( `attr_t->type="caution"`\).|
|`<textprop>propname_t</textprop>`|Save the `getTextContent()` output to property defined by `propname_t.` <br> **Note:** This is an optimized property.|
|`<xmlprop>propname_x </xmlprop>`|Save serialized XML of this node to property defined by `propname_x.<br> `**Note:** This is an optimized property.|
|`<xpath>`|If XPath element is provided in the element mapping, then along with element name and class the XPath condition should also be satisfied for the component mapping to be used.|
|`<target>`|Place for the DITA element in the crx repository at specified location.<br> Possible values: <br> - **head**: Under the head node <br> - **text**: Under the paragraph node|
|`<wrapelement>`|The HTML element to wrap the contents within.|
|`<wrapclass>`|The element value to the property `wrapclass.`|
|`<attributemap>`|Container node containing one or more `<attribute>` nodes.|
|`<attribute from="attrname" to="propname" ispath="true\|false" rel="source\|target" />`|Maps the DITA attributes to AEM properties: <br> -   **`from`**: DITA attribute name <br> -   **`to`**: AEM component property name <br> -   **`ispath`**: If the attribute is a path value \(for example: *image*\) <br> -   **`rel`**: If the path is the source or target <br> **Note:** If `attrname` starts with `%`, then map `attrname minus '%'` to prop ' `propname`'. |

**Additional notes**

-   If you plan to override the default element mapping, it is recommended that you do not make the changes in the default `elementmapping.xml` file. You should create a new mapping XML file and place the file at another location, preferably inside custom apps folder that you create.

-   In the `elementmapping.xml` file, there are many mapping entries referencing the fmdita/components/dita/wrapper component. Wrapper is a generic component that renders relatively simple DITA constructs using properties on their site node to generate relevant HTML. It uses the `wrapelement` property to generate enclosing tags and delegates the child rendering to the corresponding components. This is useful in cases where you only want a container component. Instead of creating a new component that renders a specific container tag like `div` or `p`, you can use the Wrapper component with the `wrapelement` and `wrapclass` properties to achieve the same effect.

-   It is not recommended to save large amounts of text in String JCR properties. The optimized property type calculation in output generation ensures that large text content is not saved as string type. Instead, when content larger than a certain threshold needs to be saved, the type of the property is changed to binary. By default, this threshold is configured to 512 bytes, but can be changed in the Configuration Manager \(*com.adobe.fmdita.config.ConfigManager*\) by changing the **Save as Binary Threshold** setting.

-   If you are planning to override some \(and not all\) of the element mappings, you do not have to replicate the entire `elementmapping.xml` file. You need to create a new XML mapping file and define only the elements that you are overriding.

-   After you have created the XML file in the custom location, update the `Override Element Mapping` setting in the `com.adobe.fmdita.config.ConfigManager` bundle.


