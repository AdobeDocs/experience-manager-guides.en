---
title: Native PDF Publish Feature | Apply custom style on TOC entries and topic content
description: Learn how to create use styleheets and create styles for your content.
exl-id: f65c9683-a1fc-432a-854b-83e8f39d7dae
feature: Output Generation
role: Admin
level: Experienced
TQID: https://experienceleague.adobe.com/cqknNhuPThhuNTsLZzwnrUzPJguIPs4J-3rX6PVR2V8
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Apply custom style on TOC entries and topic content 

At times, you might want to apply custom styling on the TOC entries or a particular topic. This can be achieved by associating an `outputclass` attribute with the supported map elements such as `<topicref>`, `<topichead>`, and `<topicgroup>`. Also, in case you want to apply a custom format to an entire topic, then that can also be achieved by extending the attribute's style definition in the CSS.

## Style a topic referenced through `<topicref>`

You can apply an `outputclass` on a `<topicref>` element to style the TOC entry, the topic title, or the full topic content in the generated PDF.

Let's take an example of a new topic that you want to send for review. For easy identification of the updated topic, you need to add an `outputclass` attribute to the `<topicref>` element in your DITA map and then define a custom styling for the same in the CSS.

In the following example, the *History of flights* topic has been assigned an `outputclass` attribute with the value of `new-topic`. 

<img src="./assets/new-topic-attribute-in-map.png" width=500>

The class definition of the `new-topic` in a CSS can let you define the style for the following items: 

* The main entry in the TOC or mini-TOC
* The title of the topic in the main content
* The entire content of the topic, including the title

Let's see how each of these scenarios can be defined in the CSS. In the following CSS definition of the `new-topic` class, the text color has been changed.

```css
.new-topic {
  color:#CC5309
}
```

This definition controls the color of the text in the TOC and the topic's title. The following PDF output shows the different color applied on the TOC entry:

<img src="./assets/pdf-output-toc-entry.jpg" width=500>

The topic's title is also styled using the same color. 

<img src="./assets/pdf-output-topic-title.jpg" width=500>

If you want the TOC entry and the topic's title to have different styles, then you can define them separately as shown below:

```css
...
/*for styling TOC entry */
.new-topic {
  color:#CC3509
}

/* for styling topic's title */
.new-topic.title {
  color:#092ACC
}
...
```

Finally, you can also apply styles on the entire content within the topic. For this, you need to add a suffix "`-content`" to the class name. In the following example, a change bar has been added on the entire content of the topic:

```css
...
/* for styling the topic's content */
.new-topic-content {
  -ro-change-bar-color:#A609CC;
}
...
```

Using the above styling attributes, a change bar is added to the left of the *History of flight* topic, as shown below:

<img src="./assets/pdf-output-topic-content.jpg" width=500>

## Apply styles to topichead elements

You can use the `outputclass` attribute on a `<topichead>` element to apply custom styles to the generated TOC.

For example, if you define the following `topichead` in your DITA map:

```xml
<topichead navtitle="Getting Started" outputclass="new-topichead">
    ...
</topichead>
```

The `new-topichead` class is added to the heading generated for the topichead in the TOC. You can use this class to apply custom styles to the topichead heading.

```css
.new-topichead {
    color: blue;
    font-style: italic;
}
```

To apply styles to the child topic references associated with the topichead, append the `-content` suffix to the output class name.

For example, the following HTML is generated for the topic group associated with the topichead:

```css
.new-topichead-content {
    border-left: 2px solid #cccccc;
    padding-left: 8px;
}
```


In this example, the custom style is applied to:

* The topichead heading using the `new-topichead` class.
* The child topic references associated with the topichead using the `new-topichead-content` class.


## Remove empty rows from the TOC

If you have not defined the title for any topics, empty rows appear in the TOC for such topics. 

To remove the empty rows from the TOC and the mini TOC, add the following style in the `layout.css`:

```css
.toc-body a:empty,
.chaptoc-body a:empty {
    display: none;
} 
```

