---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides 4.6.0 Service Pack 4 release
description: Learn about the bug fixes in the  4.6.0 Service Pack 4 release of Adobe Experience Manager Guides
role: Leader
exl-id: ad69ea47-7880-43d1-8567-cd608fedb462
TQID: https://experienceleague.adobe.com/4ILARUO5umX41xE3Lcie-FsP396sgSqfbrWlMqdjsQ4
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
subfeature_v2:
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
    internal-label: Native PDF publishing
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
---
# Fixed issues in the 4.6.0 Service Pack 4 release (April 2025)


This article covers the bugs fixed in various areas of 4.6.0 Service Pack 4 release of Adobe Experience Manager Guides.

Learn about [upgrade instructions for the 4.6.0 Service Pack 4 release](upgrade-instructions-4-6-0-sp4.md).

## Authoring

- Dragging and dropping an image within a topic in **Author** view causes the image reference to break, leading to data loss. (25769)
- Dragging and dropping a `topicref` within a Map in **Author** view fails to perform the intended operation and removes the `topicref` next to the dragged `topicref`. (19460)
- Failing to close JCR session connections while updating or creating topics result in memory leaks and service downtime. (26282)

## Publishing

- Native PDF publishing continues indefinitely, if the DITA content has a weblink without having scope as `external`. (26434)
- When creating a new baseline with a large number of labels, it causes the labels loader to fail and prevents the labels from being fetched. (16232)
- Publishing of Native PDFs and AEM sites stalls and gets queued, when there are errors in the content. (26516)

## Known issues

Adobe has identified the following known issue for this release:

- Native PDF publishing on Windows encounters failures when DITA content contains an external link that does not include the `scope` attribute.
