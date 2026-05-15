---
title: Button
description: Button
role: User, Admin
exl-id: 40e3f254-f94e-4f43-8ff5-2e6e1eb1cb6f
TQID: https://experienceleague.adobe.com/pmhyi9TN4gFF0opdy2SsTEUr4l1uLZMwhIwmUPMJSA0
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
# Button

To display a button we use the component, button.
 The button component in JUI represents an html `<button/>`.

```js title="buttonJSON.js"
const buttonJSON = {
  "component": "button",//tells the component name
  "label": "Yes, login",//tells the text for the button
  "variant": "cta",//tells the variants for the button which  provides default styles
  "on-click": "done",//tells what function to run after user clicks the button
};

```

This will produce a button with a label of `Yes, login`. The other properties includes but are not limited to variant,label,on-click.
> **_NOTE:_**  The `on-<events>` is the syntax for invoking the commands in the controllers.

The rendered button will look like this:

![button](imgs/yes_login_button.png "Button")
