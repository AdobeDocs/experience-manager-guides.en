---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2026.03.0 release
description: Learn about the bug fixes in the 2026.03.0 release of Adobe Experience Manager Guides as a Cloud Service.
---
# Fixed issues in the 2026.03.0 release 

This article covers the bugs fixed in various areas of the 2026.03.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2026.03.0 release](whats-new-2026-03-0.md).

Learn about [upgrade instructions for the 2026.03.0 release](upgrade-instructions-2026-03-0.md).

## Authoring

- When editing a Schematron (*.sch) file and using the Find and replace feature,  the Find and replace panel appears partially off-screen at the bottom, preventing access to its input fields and controls. (GUIDES-38412)

## Publishing

- When the same topic is reused across multiple maps with different conditional presets, publishing the latest map to Salesforce overwrites the topic content, resulting in incorrect data being displayed to users of previously published maps. (GUIDES-37806)
- When publishing a Native PDF for a map that includes conditional processing or certain nested maps, the `dc:title` defined in the map fails to appear on the PDF cover, resulting in a missing cover title. (GUIDES-37733)
- Generating AEM site output (using composite component mapping) for a map with the `map\_title` variable in the output path fails and results in an error. (GUIDES-36968)
- When an output path with a trailing slash is specified in the PDF output preset, the UI automatically appends an additional trailing slash, resulting in a double‑slash path that causes the PDF upload to fail. (GUIDES-34932)
- Publishing AEM Sites pages generated from DITA content through Quick Publish or Manage Publication unintentionally publishes the associated DITA assets. (GUIDES-27967)
- When publishing a map to AEM Sites (using legacy component mapping), cross-references (`xrefs`) with scope=peer that target sub-elements of a topic (such as paragraphs) in a different map do not resolve to the specific element ID and instead resolve only to the parent topic, causing the page to load at the start of the topic rather than scrolling to the intended section. (GUIDES-21802)
- In an On‑Premise setup, enabling **Use automatic hyphenation** in the Native PDF output preset is not applied during PDF generation, resulting in missing hyphenation for multi-line paragraphs in the generated output. (GUIDES-19703)

## Translation

- When an image initially managed as a language‑specific asset with a specific version (for example, under `/en/`) is moved out to a global folder with an updated version and baseline export is performed, the new baseline continues to reference outdated language‑specific versions of that image, leading to a failed baseline export. (GUIDES-39394)

## Baseline 

- When creating a dynamic baseline, the editor sometimes becomes unresponsive due to multiple concurrent API requests, causing all other operations to halt. (GUIDES-39504)

## Learning

- Attempting Match the following question type in a quiz incorrectly in ALM, results in the selected options not appearing in the report. (GUIDES-38640)
- GUIDES-40883

## Reports

- GUIDES-39385

## Review

- GUIDES-37781

