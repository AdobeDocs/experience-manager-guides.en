---
title: Topbar and Toolbar
description: Customising topbar and toolbar
role: User, Admin
exl-id: 7065c9b8-67ac-4f6d-8124-daa547f2dc3b
---
# Customising topbar and toolbar

To customise the `topbar` and `toolbar`, we will be using the ids: `topbar` or `toolbar`, and follow the same view, controller structure.

Below is a trivial example of toolbar customisation. Here, we have removed the `Insert Numbered List` button, and replaced the `Insert Paragraph` button with our own component using a customised on-click handler.

For accessing functionality exposed under `proxy` object we will need to acces it using `this.proxy.getValue` lets say for fetching a value.

```js title = toolbar_customisation.js
const toolbarExtend = {
    id: "toolbar",
    view: {
        items: [
            {
                component: "div",
                target: {
                    key:"title",value: "Insert Numbered List",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
            {
                {
                    "component": "button",
                    "icon": "textParagraph",
                    "variant": "action",
                    "quiet": true,
                    "title": "Insert Paragraph",
                    "on-click": "INSERT_P"
                },

                target: {
                    key:"title",value: "Insert Paragraph",                    
                    viewState: VIEW_STATE.REPLACE
                }
            },
        ]
    },
    controller: {
        init: function() {
            console.log(this.proxy.getValue("canUndo"))
            this.proxy.subscribeAppEvent({
              key: "editor.preview_rendered",
              next: async function (e) {
                console.log(this.proxy.getValue("canUndo"))
              }.bind(this)
            })
        },
        INSERT_P(){
            this.next("AUTHOR_INSERT_ELEMENT",  "p" )
        }
    }
}
```
