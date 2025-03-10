---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 4.6.0 Service Pack 4 release
description: Learn about the bug fixes in the  4.6.0 Service Pack 4 release of Adobe Experience Manager Guides
role: Leader

---
# Fixed issues in the 4.6.0 Service Pack 4 release (March 2025)


This article covers the bugs fixed in various areas of 4.6.0 Service Pack 4 release of Adobe Experience Manager Guides.

Learn about [upgrade instructions for the 4.6.0 Service Pack 4 release](upgrade-instructions-4-6-0-sp4.md).

## Authoring

- Dragging and dropping an image within a topic in **Author** view causes the image reference to break, leading to data loss. (25769)
- Dragging and dropping a `topicref` in **Author** view fails to perform the intended operation and removes the `topicref` next to the dragged `topicref`. (19460)
- Failing to close JCR session connections while updating or creating topics resulting in memory leaks and service downtime. (26282)

## Publishing

- Native PDF publishing continues indefinitely, if the DITA content has a weblink without having scope=`external`. (26434)
- When creating a new baseline with a large number of labels, it causes the labels loader to fail and prevents the labels from being fetched. (16232)
- For Native PDF and AEM site publishing, the publishing process does not progress and times out with the timeout information in the logs. (26516)
