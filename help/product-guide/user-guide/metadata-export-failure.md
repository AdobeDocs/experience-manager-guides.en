---
title:  Metadata export fails with "String is too long" exception in Experience Manager Guides
description: Understand why metadata export can fail for Guides content in the Assets UI.
feature: Authoring, Publishing
role: User
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
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
---
# Why does metadata export for a folder fail with "String is too long" exception?

When you [export metadata](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/assets/using/metadata#export-metadata) for a folder from the Assets UI, the export job can fail with `String is too long` exception. This typically happens when the folder contains Experience Manager Guides specific properties that store non-string values, such as `baselineObj`.

**Why does this happen?**

Some properties stored under an asset's metadata node are used internally by Experience Manager Guides and contain data, such as JSON objects, rather than plain string values. When exporting metadata for a folder, if **Properties to be exported** is set to **All**, the export job attempts to convert every property to a string, and it fails on properties that hold this kind of data.

**How is this prevented?**

To avoid this failure, the following properties are excluded from metadata export by default in the **Asset Metadata Exporter Configuration**:

- `baseline`
- `namedoutputs`
- `conditionpresets`
- `nextgenbaselinestore`

**Can I still export these properties?**

Yes. If you need one or more of these properties in the export, you can edit the **Asset Metadata Exporter Configuration** and remove them from the exclusion list.

Removing a property from the exclusion list does not guarantee that the export will succeed. Depending on the size and content of the underlying data, the job may still fail with the same exception. If you run into this after re-enabling a property, add it back to the exclusion list to restore the default, reliable export behavior.
