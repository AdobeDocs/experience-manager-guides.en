---
title: Customising
description: Customising the review app
role: User, Admin
exl-id: 9f6a4e9f-fc13-40b5-a30f-151c94faff81
TQID: https://experienceleague.adobe.com/s98wa8vFTKBHZ--qCeFjmynYwr3BRVOekxOlGJFIqds
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
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
---
# Customising the review app

To ease the customisation of the review app we have provided some hooks listed and explained below:

## Review-Comment

- id: `review_comment`
- hook: `this.next('updateExtraProps')`:

As discussed [here](../../aem_guides_framework/basic-customisation.md), any new attribute added during customisation goes under `this.model.extraProps`. The method `updateExtraProps` allows you to add attributes to a review comment, handling the updation and storage of the added attribute on the server as well.

### Usage Example

Say for example, you want to add fields `commentRationale` and `severity` to your comments.
Let us update the `commentRationale` to "This is an important sentence." and the `severity` to "CRITICAL".
This can be done using the syntax:

```typescript
  this.next('updateExtraProps', {
    'commentRationale': 'This is an important sentence.',
    'severity': 'CRITICAL'
  })
```

The above code snippet will handle the updation and saving of the values. The saved values can be rendered on the UI by defining the view.

```JSON
{
    "component" : "label",
    "label": "@extraProps.commentRationale"
}
```

## Inline review panel

- id: `inline_review_panel`

1. hook: `onNewCommentEvent`
The hook `onNewCommentEvent` allows you to throw an event or call a method on a new comment or reply event.
The args received in the `onNewCommentEvent` include:
    - events: the comment/reply event that was dispatched.
    - newComment: boolean
        If the event dispatched was a new comment event, i.e. `highlight`, `insertion`, `deletion`, `sticky note comment`
    - newReply: boolean
        If the event dispatched was a new reply event.

2. hook: `sendExtraProps`

This hook is beneficial if you want to extend an `event` and send `extraProps` from the inline review panel. We will explain the usage of these two hooks below.

### Inline Review Panel Example

Say we want to send an extraProp, `userInfo`, everytime a new comment or reply is dispatched. Now this will be done via the inline review panel, however we do not have the reference to the commentId of the newly generated comment, hence to achieve this we can write the following code.

```typescript
    onNewCommentEvent(args){
      const events = _.get(args, "events")
      const currTopicIndex = tcx.model.getValue(tcx.model.KEYS.REVIEW_CURR_TOPIC) || this.getValue('currTopicIndex') || "0"
      const event = _.get(_.get(events, currTopicIndex), '0')
      const newComment = _.get(args, 'newComment')
      const newReply = _.get(args, 'newReply')
      if ((newComment || newReply) && event) {
        this.next('setUserInfo', event)
      }
    },
```

In the above code snippet, we are checking if the dispatched event was a new comment or reply. In case of a new comment or reply, we are calling the method `setUserInfo`

```typescript
    const getUserInfo = (userId) => {
      return $.ajax({
        url: '/bin/dxml/xmleditor/userinfo',
        data: {
          username: userId,
        },
        success: (data) => {
          return data
        }
      })
    }

    setUserInfo(event) {
      getUserInfo(event.user).done(userData => {
        const extraProps = {
          "userFirstName": userData?.givenName || '',
          "userLastName": userData?.familyName || '',
          "userTitle": userData?.title || '',
          "userJobTitle": userData?.jobTitle || '',
          'userEmail': userData?.email || '',
        }
        const data = {... event, extraProps}
        this.next(
          'sendExtraProps',
          data
        )
      })
    },
```

In the above method, we are extending the event to send extraProps which include the user's first name, email, title etc. Extending the event this way ensures that the extraProps are sent with the correct commentId, ensuring that they are attached to the right comment.

The hook `updateExtraProps` inherently calls the hook `sendExtraProps`, so when to use what?

We use `updateExtraProps` in the `review_comment` controller, which already has the comment's `id` and hence you just need to mention the `extraProps.`

The `inline_review_panel` however does not have the access to the comment's id, hence anytime you need to dispatch an event from the inline review panel, the `sendExtraProps` will be handy.
