---
title: Remove 'Delete' option from file context menu in webeditor for specific users
description: Learn how customize webeditor by removing 'Delete' option from file context menu for specific users/groups
exl-id: 31b4dd53-3938-42e1-bbc6-64806d668696
TQID: https://experienceleague.adobe.com/dzbMsXUoEibR5QxKB-Z-h4qGnQaX2NmIYLTtxVJHE-A
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
---
# Remove 'Delete' option from file context menu in webeditor

In this article we will learn how hide the 'Delete' option from file context menu in AEM Guides Editor for specific users or groups. For other customizations on file context menu options, please check Guides Extension framwork. More details can be found [here](https://github.com/adobe/guides-extension/tree/main).

As you can see from below snippet, the file context menu has 'Delete'option available for this specific user.

![File contextmenu with Delete](../../../assets/authoring/file-contextmenu-Delete.png)

Now, let us see how we can hide the 'Delete' option for this user.

## Implementation Steps:

- Navigate to Tools > Security > Permissions from AEM home page.
- Choose the group or user from the search box.
- Click on 'Add ACE' from top right corner.
- Choose the folder path.
- Include privileges "jcr:removeChildNodes" and "jcr:removeNode".
- Choose 'Permission Type' as 'deny' and click on 'Add' as shown below.

![User Permission Deny ACE](../../../assets/authoring/permission-ACE-Delete.png)

![Access control List in permissions](../../../assets/authoring/delete-acl.png)

### Testing

- Login to AEM as the user for which the ACE's has been added.
- Open web-editor.
- Go to repository view and choose the folder for which the ACE's have been added.
- Open the file context menu.
- 'Delete' option will not appear in the context menu.

The file context menu will now look like this:

![File contextmenu without Delete](../../../assets/authoring/file-contextmenu-Delete-removed.png)

```
Please note that these steps would also remove 'move' and 'rename' options from the Editor as they are also tied to delete process at the backend.
```
