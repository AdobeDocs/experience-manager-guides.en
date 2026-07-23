---
title: Perform indexing to include all review tasks in Comments panel
description: Learn how to index existing review tasks so they appear alongside newer ones in the Comments panel's review task drop-down.
feature: Web Editor Configuration
role: Admin
level: Experienced

---
# Perform indexing to include all review tasks for a topic in the Comments panel

The [View all review tasks for a topic](../user-guide/review-address-review-comments.md#view-all-review-tasks-for-a-topic) feature, available in the Comments panel, allows authors to select any review task (open or closed) associated with the currently-open topic, without switching review projects. When enabled, the **Comments** panel in the Editor includes a drop-down listing every review task the topic is part of, along with each task's state and the project it belongs to.

By default, when this feature is enabled on an instance, review tasks are indexed as they are created, so they're automatically available in this drop-down.

However, if the feature is disabled at the time Experience Manager Guides is deployed on an instance, review tasks created while it remains disabled are not indexed. As an Administrator, if you enable the feature after such review tasks already exist, those tasks do not appear in the drop-down until they are indexed. To make them available, you must run a one-time script to index the existing review tasks.

Run the following cURL command once to index existing review tasks:

```bash
curl --location 'http://<host>:<port>/bin/guides/script/start' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Basic <base64-encoded-credentials>' \
--header 'Cookie: cq-authoring-mode=TOUCH' \
--data-urlencode 'jobType=review-topic-guids-migration'
```