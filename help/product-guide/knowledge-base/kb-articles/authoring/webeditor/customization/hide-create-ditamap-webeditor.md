---
title: Hide Create DitaMap option from Folder context menu options for specific users or groups.
description: Learn how to customize webeditor by hiding 'DitaMap' option from folder context menu for specific users/groups
exl-id: 796bfe3a-3950-4ade-9215-c33534791055
---
# Show/Hide 'Create DitaMAP' from folder context menu in webeditor

In this article, we will learn how to customize the Guides Web Editor to hide or show the "Create DitaMap" option in folder context menu on the basis on user/group permissions.
In this use-case we will hide this option for all non-author users.

## Pre-requisites

We will be leveraging the AEM Guides Extension package which allows you to customize the UI of your app as per you requirements.
Please go through this [documentation](https://github.com/adobe/guides-extension/tree/main) to get more insights on how Guides Extension Framework works.

Now lets get started and learn how to customize the folder context menu to hide this option for all non-author users.

As you can see from below snippet, the "create DitaMap" option is visible for an author user.

![Show create DitaMap option](../../../assets/authoring/ditamap-show-author.png)

Let us now see how we can hide this option using Guides Extension Framework.

## Implementation Steps

The implementation is broken in below parts:

- **Changes in Folder_options controller**

  Each context menu has a controller id associated with it. This controller handles the on-event functionality for the various context menu options.

  In this example, we will customize the folder context menu to hide the "Create DitaMap" option for non-authors. For this, we will make changes to the folder_options.ts file present under /src in guides extension framework repository.

  We are using "viewState" as "REPLACE" to hide this option from context menu.
  We are calling a new widget in this folder_options through the key 'id'.

```typescript
const folderOptions = {
  id: "folder_options",
  contextMenuWidget: "repository_panel",
  view: {
    items: [
      {
        component: "widget",
        id: "customditamap",
        target: {
          key: "displayName",
          value: "DITA Map",
          viewState: VIEW_STATE.REPLACE,
        },
      },
    ],
  },
};
```

- **Creation of a new widget to handle the logic**

  A new widget creation (customoptions.ts) is needed to write the logic to hide this option for non-author users only. To achieve this we have used the 'show' key which acts as a toggle in our JSON structure.

  You can write your own external servlet to check the group details. This way, you can customize folder menu options for your custom group as well.
  In this example, We have leveraged the OOTB AEM 'rolesapi' call to fetch the user details and set the response in 'isAuthor' as shown in above snippets.

```typescript
const folderOptions = {
  id: "customditamap",
  view: {
    component: "button",
    quiet: true,
    icon: "breakdownAdd",
    label: "DITA Map",
    "on-click": "createNewDitaMap",
    show: "@extraProps.isAuthor",
  },
};
```

Through this, we are able to hide the button with label as "Dita Map" based on the value of 'show'.

We have added a controller to set the 'isAuthor' attribute in the model, this can be done using the following syntax in the controller.

```typescript
this.model.extraProps.set("key", value);
```

Here the key is 'isAuthor' and the value is the response from the rolesapi call.
We have also defined 'createNewDitaMap' event to enable the create DitaMap option (for author users).

```typescript
controller: {
    init: function () {
      this.model.extraProps.set("isAuthor", false);

      rolesApiResponse.then((result) => {
        console.log(result);
        this.model.extraProps.set(
          "isAuthor",
          result["/content/dam"].roles.authors
        );

        console.log("testresult" + result["/content/dam"].roles.authors);
      });
    },
    createNewDitaMap() {
      repositoryController && repositoryController.next("create_new.map");
    },
  },
```

- **Adding the customized code**

  Import the folder_options.ts and customoptions.ts to the index.ts file under /src.

## Testing

- Login to AEM with a user who is not a part of authors group. The Create DitaMap option would be hidden on any folder's context menu as shown below.
  This use-case has been added to GIT, please find related resources below.

![Hide create DitaMap option](../../../assets/authoring/ditamap-hide-non-author.png)

### Related resources

- **Extension Framework base repository** - [GIT](https://github.com/adobe/guides-extension/tree/main)

- **Documentation** - [on Experience League](../../../../../guides-ui-extensions/aem_guides_framework/basic-customisation.md)

- **Documented common use cases** - [on Experience League](../../../../../guides-ui-extensions/aem_guides_framework/jui-framework.md)

- **Public repository with samples** - [on GIT](https://github.com/adobe/guides-extension/tree/sc-expert-session). Refer branch sc-expert-session

```

```
