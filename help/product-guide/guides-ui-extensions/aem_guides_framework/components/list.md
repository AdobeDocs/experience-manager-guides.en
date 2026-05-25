---
title: List
description: List
role: User, Admin
exl-id: 333b5e24-efba-4a51-8f68-83b5d1d7daec
TQID: https://experienceleague.adobe.com/2mjVuKodk-Jn7tGoiF1fNpCnTd1VqK57oATMiN2gd0o
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
# List

To display a list, we use the component list.

```js title="list.js"

const listJSON =  {
    "component": "list", //tells the component name
    "data": "@languages", // an array of list items
},

```

Here, language is a simple array of strings. `languages = ["English", "Hindi", "French"]`
In case we want to render a list of objects, we can specify the structure using item config.

```js title="list.js"

const listJSON =  {
    "component": "list", //tells the component name
    "data": "@projects", // an array of list items
    "itemConfig": { // used to define the structure of the list items.
    "component": "widget",
    "id": "checkbox_label"
    }
},

```

Usually itemConfig is a `widget`. To learn more about widgets go to [Widgets](../Widgets/basic-widget.md)

The rendered list will look like this:

![list](./imgs/list.png "List")
