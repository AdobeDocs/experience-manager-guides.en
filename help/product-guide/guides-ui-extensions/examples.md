---
title: Examples
description: List of customisation examples
exl-id: 40cdc703-7a78-4979-a7b5-1158558d4868
---
# Examples

In this package we have also provided some customisation examples (available at `guides_extension/src`) . Below is a brief description for each of them.

1. [Context Menu](./examples/file_options.ts)
In this example we have customised the `file_options` context menu, to remove the `Delete` and `Edit` options, and replace the `Duplicate` option with a `Download` option.

2. [Left Panel](./examples/left_panel_container.ts)
In this example we have customised the `left tab panel` to have another`tab` titled "TEST EXTENSION", and a corresponding `tab panel` which has a label: `Test Tab Panel`

3. [Right Panel](./examples/right_panel_container.ts)
In this example we have customised the `right tab panel` to have another `tab` titled "TEST EXTENSION", and a corresponding `tab panel` which has a label: `New Tab Panel`

4. [Repository Panel](./examples/repository_panel.ts)

5. [Toolbar](./examples/toolbar.ts)
In this example we have replaced the `Insert Element`, `Insert Paragraph`, `Insert Numbered List`, `Insert Bulleted List` buttons with a single `More Insert Options` button containing all of these.

[Review App Examples]

1. [Annotation Toolbox](./examples/review_app_examples/annotation_extension.ts)
In this example we have added another button to the annotation toolbox that opens the current review topic in AEM.

2. [Review Comment](./examples/review_app_examples/review_comment.ts)
In this example we have added replaced the user name with user info (consisiting full name and title of the commenter), added a unique comment ID, a mailTo icon, and added input fields for mentioning comment severity and rationale.
We have also added a `accept with modification` button on comments on the XMLEditor side that opens a dialogue.

3. [Comment Reply](./examples/review_app_examples/comment_reply.ts)
In this example we have added replaced the user name with user info (consisiting full name and title of the commenter), and added a mailTo icon in the comment header.

4. [Inline Review Panel](./examples/review_app_examples/inline_review_panel.ts)
In this file, we calculate and assign the unique comment ID, mentioned in the `Review Comment` and `Comment Reply` examples.
    - The `setCommentId` method sets the unique comment ID to each comment depending on the comment count.

    - The `setUserInfo` sets the value of userInfo, using the full name and title for each comment.

    - The `onNewCommentEvent` ensures the `setUserInfo` method is called for each new comment or reply.

    - The `updatedProcessComments` function runs for each new comment Event, and ensures that `setCommentId` is called if we get a new comment event.

5. [Topic Reviews Panel](./examples/review_app_examples/topic_reviews.ts): This file extends [Inline Review Panel](./examples/review_app_examples/inline_review_panel.ts) so that added customisations work on the Review App side as well.

6. [Accept with Modification Dialog](./examples/review_app_examples/accept_with_modification_dialog.ts)
This is an example of adding new widgets to the app. Here we have created a new dialogue, that has two input text fields: `Revised Text` and `Adjudicator Comment Rationale`

7. [Save Revision](./examples/save_revision.ts)
This is asn example of how to update an exisitng dialog. We add a button for publish in this. We allow modifying the content of the dialog. Refer to its json here: [`save_revision`](./jsons/dialogs/save_revision.json)

![Accept With Modification Dialog](./imgs/accept_with_modification_dialogue.png)

Here's the review panel before and after customisation:

![Review Panel;](./imgs/review_panel.png)
![Accept With Modification Dialog](./imgs/customised_review_panel.png)
