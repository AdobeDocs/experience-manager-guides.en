---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2024.10.0 release
description: Learn about the bug fixes in the 2024.10.0 release of Adobe Experience Manager Guides as a Cloud Service.

---
# Fixed issues in the 2025.02.0 release 

This article covers the bugs fixed in various areas of the 2025.02.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2025.02.0 release](whats-new-2025-02-0.md).

Learn about [upgrade instructions for the 2025.02.0 release](upgrade-instructions-2025-02-0.md).


## Authoring

- When updating conditions from the folder profile, all the condition groups are lost and the conditions become flattened. (23526)
- Changing the header rows value for a table in the **Content properties** panel does not apply the updated value. (23213)
- For subsequent Guides document state transitions, a page refresh is required. (19421)
- When adding topics in DITA map using **Topic reference** element dialog in the **Author** view, the selected topics are inserted in reverse order of being selected. (8031)
- The topic title and DITA icon are not aligned in the **Create Review** UI. (11670)
- The setting **Sanitize page names & filenames for AEM Sites & other output formats** is applicable to all the output formats. (7651)
- When deleting folders containing large number of data, the operation fails. (17107)
- When you cancel/delete the translation job or delete the project, the translation dashboard shows **In progress** status. (18417)
- When you enable unified shell for a cloud instance, the topic preview does not open from map dashboard. (18826)
- When switching between **Author** view and **Source** view, the leading spaces in `<pre>` or `<codeblock>` elements get deleted and the file gets saved with this deletion. (19987)
- The table header rows count is non-configurable by the users. (19955)
- When you increment the version of a file that is recently changed to **Done** state, the document state reverts to **Draft** on using **Save as new version** and the **Done** state is lost in the **Version History**. (20006)
- If an external link contains a UUID, it goes in post processing and converts the external link to UUID link thereby breaking the link on web editor and also on the publishing sites. (22574)
- When list items are moved outside the para tag, the list item contents are lost. (22764)
- When adding topics in DITA map using **Topic reference** element dialog in the **Author** view, the selected topics are inserted in reverse order of being selected. (22858)
- When adding new topic references in DITA map using **Topic reference** element dialog in the **Layout** view, the added references are shown as broken link. (22859)
- For a simple table in a topic, the **Rename** element is not visible. (22860)
- When you insert an `xref` that utilizes key-based referencing with link text, the link text fails to display in Experience Manager Guides. (18775)
- Dragging and dropping an image within a topic in **Author** view causes the image reference to break, leading to data loss. (25769)
- Multiple images cannot be selected from the **Repository** for addition to a topic. (25104)
- When pasting an image into a topic that is copied from any tool, the image fails to paste, and no new asset is created. (24983)
- Dragging a `topicref` over another (in **Author** or **Layout** view) prompts a confirmation for replacement instead of nesting, and selecting **No** on the confirmation dialog still causes content to be replaced, leading to data loss. (18602)
- You can't add multiple shortcuts to a single event, nor can you attach an argument to an event when triggering it from a shortcut. (19066)

## Publishing

- Publishing to Salesforce fails when content contains non-breaking spaces. (23664)
- For topics having errors like broken links, the Salesforce publishing fails and progress bar is shown indefinitely. (22985)
- For Salesforce publishing, all the uploaded images have metadata displayed in the article. (21764)
- Native pdf publishing fails for **PDF/X-4** conformance option with an error stating that **PDF/X-4 documents require a non-empty title**. (16904)
- `<keyref>` for cross-references in Native PDF fails, when placeholder text is used. (19365)
- Native PDF generation fails for content with **chunk attribute** set to **to-content**. (21772)
- When generating a Native PDF output, the `ditavalref` element is not supported. (16320)
- When editing large CSS file in the Native PDF CSS editor, a significant lag is observed. (16915)
- For HTML5 based publishing, DITA-OT flag generate.copy.outer gets applied automatically. (24299)
- The `xref` converts to relative link even when the **scope** of link is set to **external**. (23059)
- In the template settings, the ICC file path does not work when browsing the internal DAM path in **File** field and the **Name** field has no validation. (14741)
- When generating multiple DITA maps using the same folder profile preset, the publishing fails. (18800)
- For topics having a multi valued metadata/property when passed to DITA OT, the publishing fails. (19001) 
- For a map containing topic references under `<topichead>` with a valid `<navtitle>`, the generated TOC does not show the `<navtitle>` as setup in the `<topichead>`, rather shows the filename or title of the `<topichead>` underneath it. (19735)
- When choosing **Edit properties**, the baseline dialog does not show the previously saved criteria for dynamic baseline. (23964)
- For content state which reaches end state the baseline skips indirect reference. (19148)


## Management

- There is a memory leakage, when working with **Collections** in the Editor. (18488)
- The CSS style in the **Force delete** dialog box is misaligned. (21933) 
- When any JSON is updated in the folder profile for XML Editor Configuration, the save operation disrupts the XML Editor Configuration. (22414)
- When uploading any non-DITA files (like PDF, image etc.), a Null Pointer exception gets logged in. (5432)
- When duplicating any folder profile, its admin user list also gets copied from the original folder profile. (19067)
- When moving large folders (containing a large volume of DITA content, up to 200,000 items) within the Digital Asset Management (DAM) system, an error occurs. (20107)
- When using dynamic title with `<conkeyref>`, it does not resolve properly in **Guides Report Topic list**. (20144)
- Editing the **Folder Profile** or refreshing the **Folder Profile** page (with unified shell and SSO login enabled), results in blank UI. (22212)

## Translation

- When you send two versions of the same topic for translation and the second version is approved before the first version, the first version gets lost. (22200)


## API's

- For Java-based APIs, attempt to work with the baseline result in an error. (19385)


## Review

- When selecting multiple topics for review in a map, the email notification that reviewer receives indicates that all topics in the map are available for review, rather than just the selected ones. (23214)
