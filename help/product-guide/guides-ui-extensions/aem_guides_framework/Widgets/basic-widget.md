---
title: Widgets
description: Understanding Widgets
role: User, Admin
exl-id: 96e960df-d595-4d58-8ad4-27057f857bac
TQID: https://experienceleague.adobe.com/SssVShlzFB3kjQCV-cNAOZVYb0TYSQ1CjtWoax2Q-LU
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Widgets

Multiple basic components, as discussed in the Components section can be combined to make a widget. 
Widgets can be used to make a new "more complex" component, or give structure to items of a component.

Let's dive into the concept of a widget!

We will start by making a simple widget to display a list of languages.

```js title="basicWidget.js"

const widgetJSON =  {
    "component": "div", 
    "id": "widget_languages", 
    "items": [ // adding components to the widget
        {
            "component": "div",
            "items": [
                {
                    "component": "icon",
                    "icon": "info"
                },
                {
                    "component": "label",
                    "label": "List of some languages"
                }
            ]
        },
        {
            "component": "list",
            "data": "@languages"
        }
    ]
},
```

Here, `@languages` is an array defined in the model of `widget_languages` as: ["English", "French", "Hindi", "Spanish", "Urdu"]

The rendered basic widget will look like this:

![basic_widget](imgs/basic_widget.png "Basic widget")
