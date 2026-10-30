---
title: Perform indexing to include all review tasks in Comments panel
description: Learn how to index existing review tasks so they appear alongside newer ones in the Comments panel's review task drop-down.
feature: Web Editor Configuration
role: Admin
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
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