---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2025.02.0 release
description: Learn about the bug fixes in the 2025.02.0 release of Adobe Experience Manager Guides as a Cloud Service.

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
- When switching between **Author** view and **Source** view, the leading spaces in `<pre>` or `<codeblock>` elements get deleted and the file gets saved with this deletion. (19987)
- The Document State marked as **Done** reverts to **Draft** before saving a new version, resulting in the **Done** state not persisting in any document versions. (20006)
- When list items are moved outside the para tag, the list item contents are lost. (22764)
- When adding topics in DITA map using **Topic reference** element dialog in the **Author** view, the selected topics are inserted in reverse order of being selected. (22858)
- When adding new topic references in DITA map using **Topic reference** element dialog in the **Layout** view, the added references are shown as broken links. (22859)
- When you right-click on the `<simpletable>` tag within a topic, the **Rename** option does not display. (22860)
- When you insert an `xref` that utilizes key-based referencing with link text, the link text fails to display in Experience Manager Guides. (18775)
- Dragging and dropping an image within a topic in **Author** view causes the image reference to break, leading to data loss. (25769)
- When searching files in the repository using **Search & filter** functionality, multiple files cannot be selected. (25104)
- When copying an image from any external product (for example, MS PowerPoint) and pasting it into Guides, the functionality to upload the asset on the fly for use in the file breaks. (24983)
- Dragging a `topicref` over another (in **Author** or **Layout** view) prompts a confirmation for replacement instead of nesting, and selecting **No** on the confirmation dialog still causes content to be replaced, leading to data loss. (18602)
- You can't add multiple shortcuts to a single event, nor can you add an argument to an event when triggering it from a shortcut. (19066)

## Publishing

- Publishing to Salesforce fails when content contains non-breaking spaces. (23664)
- For maps having broken links, the Salesforce publishing fails and progress bar is shown indefinitely. (24963)
- For topics having errors like broken links, the Salesforce publishing fails and progress bar is shown indefinitely. (22985)
- Native pdf publishing fails for **PDF/X-4** conformance option with an error stating that **PDF/X-4 documents require a non-empty title**. (16904)
- When placeholder text is used,  cross-references using `<keyref>` in Native PDF fails to resolve. (19365)
- Native PDF generation fails for content with **chunk attribute** set to **to-content**. (21772)
- When generating a Native PDF output, the `ditavalref` element is not supported. (16320)
- When editing large CSS file in the Native PDF CSS editor, a significant lag is observed. (16915)
- For HTML5 based publishing, DITA-OT flag generate.copy.outer gets applied automatically. (24299)
- The cross reference converts to relative link even when the **scope** of link is set to **external**. (23059)
- When an ICC file is available at an internal path, it cannot be selected in **Print** settings for Native PDF preset. (14741)
- When multiple publishing requests are initiated for different maps using the same folder profile preset, publishing fails. (18800)
- For topics having a multi valued metadata/property when passed to DITA OT, the publishing fails. (19001) 
- The **Edit properties** dialog for a baseline does not show the previously saved criteria for dynamic baseline.  (23964)
- The baseline does not include indirect references when content is in the final document state. (19148)
- The setting **Sanitize page names & filenames for AEM Sites & other output formats** is applicable to all the output formats. (7651)
- If an external link contains a UUID, it goes in post processing and converts the external link to UUID link thereby breaking the link on web editor and also on the publishing sites. (22574)


## Management

- Resource leaks occur due to Unclosed **ResourceResolver** errors in logs. (18488)
- The title and icon of the **Force delete** dialog box are misaligned in the Assets UI. (21933) 
- When any JSON is updated in the folder profile for XML Editor Configuration, the save operation disrupts the XML Editor Configuration. (22414)
- When duplicating any folder profile, its admin user list also gets copied from the original folder profile. (19067)
- When moving large folders (containing a large volume of DITA content, up to 200,000 items) from Assets UI within the Digital Asset Management (DAM) system, an error occurs. (20107)
- When using dynamic title with `<conkeyref>`, it does not resolve properly in **Guides Report Topic list**. (20144)
- Editing the **Folder** profile with unified shell enabled, leads to blank UI. (22212)
- When deleting folders containing large number of files, the operation fails. (17107)
- When you cancel/delete the translation job or delete the project, the translation dashboard shows **In progress** status. (18417)
- When you enable unified shell for a cloud instance, the topic preview does not open from map dashboard. (18826)
- When you send two versions of an untranslated topic simultaneously using non-legacy translation and approve the second version before the first, the translation project with the first version gets broken. (22200)


## Review

- When selecting multiple topics for review in a map, the email notification that reviewer receives indicates that all topics in the map are available for review, rather than just the selected ones. (23214)
- The topic title and icon are misaligned in the review creation interface. (11670)


## API's

- When creating a **Baseline** using the Guides API by triggering **BaslinUtlis** service, an error occurs. (19385)

## Known issues

Adobe has identified the following known issues for the 2025.02.0 release:

- Using images as variables in the PDF template cover page is not resolving correctly in the PDF output.
- Using **Locate in repository** for a topic does not scroll to the precise location of the topic.
- Sorting by title in the **Topic list** reports is not functioning when using `<conref>` or `<conkeyref>` in the title.
- Switching the folder profile does not immediately reflect changes on the UI without refreshing the browser.
- Extension framework is not functioning.
- Selective publishing is not supported when there is a TOC change in the map.
- Publishing a map containing external links and cross-references with Markdown fails on Windows server.
- Converting a bulleted list to a numbered list still displays the bullet in the Editor.
- Content is not being published for the Native AEM site when it involves a Markdown file.



