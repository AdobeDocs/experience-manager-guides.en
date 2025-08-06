---
title: Understanding review notifications
description: Learn about different types of review notifications and how they trigger during the different phases of review workflow in Experience Manager Guides.
feature: Reviewing 
role: User
---
# Understanding review notifications

Experience Manager Guides streamlines collaboration between Authors and Reviewers through a structured review workflow. As part of this workflow, notifications play a key role in keeping all participants of a review task informed and responsive to changes.

Whenever a review-related action is performed, such as task assignment, completion, or feedback updates, a notification is automatically sent to the involved users of the review task to draw their immediate attention. These notifications are delivered in two formats:

- **AEM notifications**: Displayed within the AEM interface.
- **Email notifications**: Sent directly to the user's inbox.

The below table provides an overview of the different types of review notifications, what actions trigger them, and how they appear across different formats:


| **Review action**                          | **Notification title (AEM)**                     | **Notification text (AEM)**                                | **Email subject**                                      | **Email notification Text**                                                                 |
|--------------------------------------------|--------------------------------------------------|-------------------------------------------------------------|--------------------------------------------------------|----------------------------------------------------------------------------------------------|
| Review Task Created                        | Review task assigned: **Homepage Review**        | Assigned by **Priya (Author)**                              | Review task assigned: **Homepage Review**              | **Priya (Author)** has created a review task **Homepage Review** in project **WebDocs Revamp** with due date **15 Aug 2025**. You have been assigned as a reviewer. |
| Feedback Submitted                         | Review feedback received for **Homepage Review** | Feedback from **John (Reviewer)**                           | Review feedback received for **Homepage Review**       | **John (Reviewer)** has submitted feedback for task **Homepage Review** in project **WebDocs Revamp**. Please review and make necessary updates well in advance of due date **15 Aug 2025**. |
| Re-review Requested                        | Re-review requested for **Homepage Review**      | Requested by **Priya (Author)**                             | Re-review requested for **Homepage Review** by **Priya** | **Priya (Author)** has updated the document for task **Homepage Review** based on your feedback and is requesting a re-review. Please review well in advance of due date **15 Aug 2025**. |
| Review Closed                              | Review task closed: **Homepage Review**          | Closed by **Priya (Author)**                                | Review task closed: **Homepage Review**                | The review task **Homepage Review** under project **WebDocs Revamp** has been closed by **Priya (Author)**. |
| Reviewer Removed                           | Unassigned from review task **Homepage Review**  | Unassigned by **Priya (Author)**                            | Unassigned from review task **Homepage Review**         | You have been unassigned from the review task **Homepage Review** under project **WebDocs Revamp** by **Priya (Author)**. |
| Tag Mention                                | Mentioned in review task comment for **Homepage Review** | Mentioned by **Priya (Author)**                      | Mentioned in review task comment for **Homepage Review** | You’ve been mentioned in a comment on task **Homepage Review** under **WebDocs Revamp** by **Priya (Author)**. |
| Content Updated During Review              | Topic updated in review task **Homepage Review** | Updated by **Priya (Author)**                               | Topic updated in review task **Homepage Review**        | **Priya (Author)** has updated the topic versions for review task **Homepage Review**. Please review well in advance of due date **15 Aug 2025**. |


In the above table, the **text in bold** represents sample values and is being driven by predefined variables that can be used in notifications.


For example: 

- **Homepage Review** is a sample task name.
- **Priya** (Author) and **John** (Reviewer) are sample user names.
- **WebDocs Revamp** is a sample project name.
- **15 Aug 2025** is a sample due date.

For a complete list of predefined variables, and review notification customization, view [Configure and customize workflows](../cs-install-guide/customize-workflows.md#customize-email-and-aem-notification-templates).




**Parent topic:**[Introduction to review](review.md)
