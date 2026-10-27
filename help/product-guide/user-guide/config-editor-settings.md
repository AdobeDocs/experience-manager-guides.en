---
title: Editor settings
description: Learn how to configure Editor settings in AEM Guides.
feature: Web Editor
role: User
---
# Editor settings

>[!NOTE]
>
> This article only applies to the New Editor. To enable this capability in your environment, contact the AEM Guides Customer Success team.

The Editor settings provides a centralized configuration panel that allows you to customize Editor behavior at an individual author level. It provide greater flexibility, consistency, and control during the authoring process.

This centralized settings panel enables you to manage key Editor preferences from a single location, reducing the need for scattered or manual configurations. The Editor settings can be accessed from the **More actions** on the Tab bar.

![Editor settings](./images/conf-editor-settings.png){width="650"}

## Supported configuration options

Editor settings allow you to customize various options, including Track Changes, Show Tags, Quick Insert Menu, and more, based on your preferences.

![Editor settings](./images/editor-settings-dialog.png){width="350"}

### Track changes

>[!NOTE]
>
>- This feature is enabled by default, to disable it contact the AEM Guides Customer Success team.
>- When working with tables, the insertion of a row or column is tracked, but the deletion of a row or column is not tracked within the Track changes panel.

Enable **Track changes** mode to record the edits made to a topic. Once it is enabled, every insertion and deletion is captured as you work, and all changes are listed in the **Track changes** panel. Consecutive edits made at the same position are grouped and displayed as a single change in the **Track changes** panel.

Deleted content appears with strikethrough, while inserted content appears in green text. In addition, change bars appear along the edge of the topic page, with red bars indicating deleted content and green bars indicating added content. If a line contains both additions and deletions, both change bars are displayed.

When multiple users work on the same topic, Track changes allows them to view each other's edits. Once the content is ready to be finalized, users can review the tracked changes and accept or reject them.

![Editor settings](./images/track-changes-all.png){width="350"}

**Show tracked deletions inline**

Controls how deleted content is displayed in the Editor while Track changes is on. When enabled, deleted content remains visible inline, at its original position, as strikethrough text. When disabled, the deleted content is not shown. Instead, a pencil icon appears at the location where the content was removed, giving you a cleaner view of your topic. Select the pencil icon to go to the corresponding deleted content in the Tracked changes panel.

![Editor settings track changes](./images/deletion-inline-off.png){width="350"}

**Accept or reject tracked changes**

To review the changes, select the **Track changes** icon in the Right panel to open the Tracked changes panel and perform the following steps:

1. Select a tracked change in the panel. The changed content is selected in the document.
1. Accept the change by selecting the **Accept change** icon, or reject it by selecting the **Reject Change** icon.

    ![Tracked changes panel](./images/track-changes-individual.png){width="650"}

1. To accept or reject all changes with a single click, select **Accept all changes** or **Reject all changes** from the top of the panel. 

    ![Tracked changes panel](./images/track-changes-all-comment.png){width="650"}


### Non breaking spaces

Enable this option to show an indicator for the non-breaking spaces while editing it in the Editor. It is visible only in the Author view for DITA topic and DITA maps.

### XML comments

Enables authors to view, edit, and insert XML comments directly in Author mode, for better visibility within the content. When enabled, authors can view, insert, edit, and delete XML comments directly within the content in the Author mode itself, making it easier to add contextual notes for collaborators. When disabled, XML comments are hidden in Author mode and cannot be inserted or modified from Author mode, ensuring a cleaner authoring experience for users who do not require them. You can continue to view and author XML comments in source mode using the `<!-- test comment -->` syntax.

>[!NOTE]
>
> For XML comments, **Track changes** records only the insertion or deletion of the entire comment. Edits made within an existing XML comment are not recorded.

![Config XML comments](./images/config-xml-comments.png){width="650"}

### Tags

Controls the visibility of tags in the Editor. When enabled, structural tags are displayed within the content, allowing authors to view and manage the underlying DITA structure. When disabled, these tags are hidden to provide a cleaner and more focused authoring experience.

![Config tags](./images/config-tags.png){width="650"}

When **Show tags** settings is enabled, you can also enable **Display attributes** to view and validate the attributes associated with an element. When an element has more than three attributes associated with them, a count indicator appears. Hovering over the indicator displays the complete list of attributes applied to that element.

    ![Config tags with attributes](./images/config-tags-attributes.png) {width="650"}

### Quick insert menu in editor

Enables adding elements directly while editing in Author mode at the cursor position without navigating to the toolbar. Frequently used elements can also be configured in the **Favorites** for quicker access. The quick insert menu is available directly in the Editor when you press **Control + /** on Windows or **Command + /** on macOS the cursor position.

![Quick insert menu in editor](./images/quick-insert-menu-in-editor.png){width="650"}

You can search for and add elements to your Favorites, remove any previously added elements, and rearrange them using simple drag-and-drop. Favorites include your most frequently used elements, and the order you set here is reflected in the Quick Insert menu when accessed from the editor. 

Here's a short video on how to work with the Quick insert menu in the New Editor.

>[!VIDEO](https://video.tv.adobe.com/v/3491343)


