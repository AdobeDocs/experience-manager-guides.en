---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2026.06.0 release
description: Learn about the bug fixes in the 2026.06.0 release of Adobe Experience Manager Guides as a Cloud Service.

---
# Fixed issues in the 2026.06.0 release 

This article covers the bugs fixed in various areas of the 2026.06.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2026.06.0 release](whats-new-2026-06-0.md).

Learn about [upgrade instructions for the 2026.06.0 release](upgrade-instructions-2026-06-0.md).

## Authoring

- When toggling focus between the **Width** and **Height** fields in the image properties dialog using unit-based sizes such as `in`, `mm`, or `px`, the values keep incrementally increasing instead of remaining stable. (GUIDES-45929)

## Editor 2.0

- Copying and pasting `<keywords>` inside `<topicmeta>` within a `<keydef>` or `<topicref>` results in the keywords being inserted inside unwanted foreign tags. (GUIDES-45800)
- Image dimensions specified with units such as `mm` are not rendered correctly, causing images to be displayed at their original size instead of the specified dimensions. (GUIDES-46275)
- When performing a drag-and-drop with Tag view enabled, selecting content along with partial XML or DITA  tags leaves behind unwanted orphan tags, resulting in incorrect content or view. (GUIDES-28191)
- In the Tag view of a table, pressing the up arrow key when the cursor is positioned at the cell directly below a collapsed entry tag skips over the collapsed tag and moves the cursor to beginning of the document. (GUIDES-45408)
- Performing any operation from the table contextual toolbar closes the toolbar unexpectedly, interrupting subsequent table operations. (GUIDES-45405)
- After using **Insert After** or **Insert Before** from the Outline view or breadcrumb, the cursor moves to an arbitrary position instead of inside the newly added tag. (GUIDES-45147)
- When the **Edit MathML** option is incorrectly displayed in read-only mode or when a file is checked out by another user, it allows users to update MathML content even though the file should not be editable. (GUIDES-45172)
- When deleting an XML comment using the backspace key, the comment tag is not removed after its content is deleted, and the deletion operation continues into the preceding element. (GUIDES-45240)
- Using the **Copy Path** or **Copy UUID** option for images, returns the full rendition path instead of the original asset path. (GUIDES-45278)
- Copy-pasting content in the same topic into an invalid location in the Editor inserts an unintended `<foreign>` tag. (GUIDES-45378)
- On Windows, copying and pasting a table row adds unexpected attributes such as `data-pm-slice` to the table element, causing markup errors that prevent the document from being saved. (GUIDES-45784)
- Using the **Copy** option from the context menu in a map or topic and then pasting the content inserts extra `<data>` tags in the pasted output. (GUIDES-45703)
- When dragging a partial selection from a `cmd` element, the content cannot be dropped between existing text or at the end of another `cmd` element. (GUIDES-44883)
- When applying a `scale` attribute to a table, the table is not rendered at the configured size in Author and Preview modes. (GUIDES-45984)
- Pasting images copied from external sources such as Paint or the Snipping Tool does not insert the image into the topic. (GUIDES-45983)
- The `keyref` used in a topic title derived from a keyword map does not appear in the TOC or topic tab after saving, even after a browser refresh. (GUIDES-45799)
- Opening a review task in the Editor using Side-by-Side view for the commented version, displays the version as None instead of the associated version for the topic. (GUIDES-45127)
- When accessing the Review task page, page breaks between topics are not displayed, resulting in the continuous rendering of content sections. (GUIDES-46777)
- The review page styling is not consistent with the New Editor experience, resulting in an inconsistent visual experience (GUIDES-46061)

## Asset management

- When a map contains an external `topicref` pointing to a non-DITA resource (such as `.html`), its preview is not displayed in the Assets UI. (GUIDES-45409)
- The Bulk Move Tool dialog overflows and lacks a scrollbar when a large number of source folders are selected, making the destination path field and action buttons inaccessible to mouse-only users. (GUIDES-45805)
- When asset is copied from Assets UI, we are getting a notification for `DXML reprocessing failure`. This notification is misleading and contributes to inbox clutter since the copy was successful. (GUIDES-45012)
- When opening the Filter panel in the Assets left-rail within a folder, the search field and facets remain disabled until the Panel is closed and reopened. (GUIDES-42652)
- Content fragments and intermediate translation assets created during translation workflows are unintentionally processed by the scheduled asset processing job, causing exceptions in logs and incorrect processing of assets that are not yet ready. (GUIDES-42582)

## Publishing

- When working with `.plt` and `.css` files in PDF templates, the **Generate IDs** option is available in the right-click context menu despite not being applicable to these file types. (GUIDES-45254)
- The **Save** button is incorrectly enabled by default when reopening a newly created Native AEM Sites preset after a browser refresh, even when no changes have been made. (GUIDES-45171)
- When duplicating a Native PDF preset that is marked as the default, the duplicate is also set as the default preset. Only one preset should be designated as the default at a time. (GUIDES-44786)
- The `outputclass` attribute is not propagated to the generated HTML or Native PDF output, preventing custom classes applied to MathML equations from affecting the rendered output. (GUIDES-44393)
- Bulk activation of AEM Sites output generated using the new AEM Sites template was failing, preventing successful replication to the publish instance. (GUIDES-44049)
- Vulnerable `jackson-databind` JARs (version 2.9.8) bundled with AEM Guides in the DITA-OT package is identified. (GUIDES-43081)
- Opening any Native AEM Sites output from a Map Collection results in an error stating that the resource is not found, preventing access to the generated output. (GUIDES-42065)
- The `<reltable>` element in a DITA map is ignored during Native PDF generation, causing "Related concepts", "Related tasks", and similar auto-generated cross-reference sections to be missing from the output. (GUIDES-38333)
- When publishing a DITA map with `processing-role=resource-only` elements on AEM Sites (with legacy component mapping), orphan site pages are generated for those elements in additional scenarios such as `topicgroup` elements and specific content configurations. (GUIDES-37650)
- When a map with a long name is added to a Map Collection, the map collection UI is rendered in a distorted layout. This issue has been resolved with the New maps collection. (GUIDES-42062)
- Publishing with the Native PDF engine v1: 
    - When generating Native PDF output for certain content, only the first page is rendered in the PDF despite the intermediate HTML containing the complete content across multiple pages. (GUIDES-28270)
    - The reading order of content in Native PDF output with accessibility settings enabled is incorrect. Page numbers from footers are read before the main content instead of at the end. (GUIDES-27790)
    - The color bar in Native PDF output does not stretch across the full page width and overlaps when the page size is customized, causing some color boxes to be hidden. (GUIDES-15505)
    - The CSS `:is()` pseudo-class selector is not honored in Native PDF output, resulting in styling differences compared to browser rendering. (GUIDES-11328)

    >[!NOTE]
    >
    > The aforementioned issues have been resolved with the Native PDF engine v2. For details, view [Work with Native PDF engine v2](../web-editor/pdf-engine-v2.md).

## Translation

- Applying a baseline to a map with many assets delays loading of the translation report for the selected language, sometimes leading to request timeout before the report renders. (GUIDES-45508)
- Language groups in Translation tab under Workspace Settings are not retained when the selected language folder uses a hyphenated locale code (for example, `da-DK`) instead of an underscore format (`da_dk`). (GUIDES-37843)

## Review

- The tooltip for the **Version History** icon is missing in the left panel of the Review UI adjacent to the topic name. (GUIDES-45511)
- When editing an active review task, if a topic that is already part of the review is removed and then re-added without selecting **Update**, the reviewer information for that topic is lost. (GUIDES-38774)
- The content pane in the Review UI displays a horizontal scrollbar on certain screen resolutions, including the recommended 1600px resolution, causing review comments to be hidden when the content extends beyond the pane width. (GUIDES-44082)

## Learning content

- When adding questions to a quiz using the Insert from question bank option, short answer questions are not listed despite having a valid Question ID. (GUIDES-44942)
- When inserting questions using the Insert from question bank option, the Insert from Question Bank dialog flickers or resizes unexpectedly upon opening. (GUIDES-45524)
- When inserting questions using the Insert from question bank option, an error occurs if the question title contains an image. (GUIDES-45383)
- Selecting a SCORM output template results in an application error when the template title has been modified. (GUIDES-45521)
- Subtitle (`.vtt`) files are not visible in the Repository or Explorer view after being uploaded to a folder. (GUIDES-46014)
- When loading video content in HTML preview, the source (`src`) path includes an appended rendition path instead of retaining the original file path, preventing the video from rendering correctly. (GUIDES-41776)
- Publishing SCORM output from Safari browser results in the package being downloaded as a folder instead of a zip file, along with rendering and functionality issues in the generated content (for example, stretched content, non working accordion and more). (GUIDES-45119)
- A delay is observed before the Next button becomes enabled for courses, impacting the learner navigation experience. (GUIDES-45113)
- Short answer question styling is rendered incorrectly in publishing output despite displaying correctly in preview. (GUIDES-46478)
- When generating PDF output for courses containing videos, the video content is not rendered and only the file path is displayed instead of a placeholder image such as a video thumbnail or poster image. This issue has been resolved by enabling **Embed multimedia files** option in the Native PDF output preset.(GUIDES-45117)
- CSS pseudo-classes and elements are rendered in white in the Guide's Editor, making them invisible or difficult to read against the editor background. (GUIDES-45116)

## Known issues

Adobe has identified the following known issues for the 2026.06.0 release:

## Editor 2.0

- Switching between Source and Author modes causes content inconsistencies, with portions of the topic disappearing or not being reflected across modes. (GUIDES-47432)

- When working in Outline view with **Track changes** enabled, rejecting a change removes the entire content within the tag instead of only rejecting the specific modified content. (GUIDES-48319)

- The **Export as PDF** button in the Preview mode does not perform any action when the editor toolbar is customized using `editor_toolbar.json` in a folder profile. (GUIDES-47525)

- While performing deletion operations, some minor inconsistencies in cursor movement and navigation can occur across image maps, structured elements, inline formatting tags, and non-mergeable blocks, occasionally resulting in unexpected cursor or deletion behavior. (GUIDES-46756)

- Using `Ctrl+click` on a broken link in a Map editor triggers an application error. (GUIDES-45544)

- Pressing backspace at the beginning of a paragraph immediately following read-only content (such as a `conref` paragraph) can unexpectedly delete or merge the editable paragraph, leading to unexpected deletion of the editable paragraph. (GUIDES-45049)

- When condition indicators are applied to elements such as `bodydiv`, the indicators overflow into adjacent tags in Full Tags View, resulting in incorrect visual rendering. (GUIDES-44971)

- When working in the Editor, you are unable to select `keyrefs` or keys derived from maps (including glossary entries within maps referenced in `term` or `abbreviated-form` elements), resulting in a degraded authoring experience. (GUIDES-45790) <br> **Workaround**: You can change the value of `keyref` from the Right panel using the attributes values.

- In the Outline view, re-enabling **Show text** after closing and reopening a topic does not display text alongside element tags. (GUIDES-48320) <br> **Workaround**: Enable the **Show text** option and then reopen the topic. After reopening, the text is displayed correctly alongside the element tags.

- When an inline tag is renamed using the **Rename element** option, the breadcrumb does not update immediately and reflects the change only after the cursor is moved into the tag or the view mode is changed. (GUIDES-44993) <br> **Workaround**: Refresh the browser after renaming the inline tag to update the breadcrumb.

- When a MathML equation is inserted as a `conref`, it does not render correctly. (GUIDES-46601) <br> **Workaround**: Wrap the MathML equation inside a `<p>` element and use that `<p>` element as the conref source.

## Review

- When a review task is reassigned to a user outside the project team, the user can perform review actions despite lacking project membership, while reviewer visibility, review status tracking, and delegation notifications do not function correctly. (GUIDES-46602)

## Publishing

- When publishing content with DITAVAL filtering that excludes all bulleted list items through conditional profiling, the output incorrectly retains an empty bullet marker instead of removing the entire list structure. (GUIDES-47238)

- When publishing a Native AEM Site output with a new baseline, the Topic List appears blank and fails to display the topics included in the selected baseline. (GUIDES-46480) <br> **Workaround**: Publish the Native AEM Site output using the old baseline, which can be configured through the configuration manager.





