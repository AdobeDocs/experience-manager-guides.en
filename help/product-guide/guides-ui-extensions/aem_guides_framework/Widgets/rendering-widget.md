---
title: Rendering widgets
description: How rendering works in JUI Widgets
role: User, Admin
exl-id: 381cc7b9-c957-40be-9db4-8347eefe2fa7
TQID: https://experienceleague.adobe.com/-VznRFHuyxLqumy55MssEvPMMHIIt2BelCe7C6zBqR8
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
# Rendering widgets

We can render a widget by referencing it using its `id`

To render th widget `widget_languages` anywhere in the app we can use the simple syntax:

```json
{
    "component": "widget",
    "id": "widget_languages"
}
```

Widgets can also be used to render complex items, say I want to render the list of contributors to each file.
Here, the widget can be constructed as:

```js title="fileContributorsWidget.js"

const widgetJSON =  {
    component: "div", 
    id: "file_contributors", 
    items: [ // adding components to the widget
        {
            component: "div",
            items: [
                {
                    component: "icon",
                    icon: "file"
                },
                {
                    component: "label",
                    label: "@fileName"
                }
            ]
        },
        {
            component: "list",
            data: "@contributors",
            itemConfig: {
                component: "label"
            }
        }
    ]
},
```

Now to render a list of contributors for each file, we write the list as:

```js title="fileContributorsList.js"
const listJSON = {
    component: "list"
    data: "@files"
    itemConfig: {
        component: "widget",
        id: "file_contributors"
    }
}
```

Here `@files` is a list of file objects containg fields

```typescript
- fileName: string
- contributors: Array<String>
```
