---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2026.06.0 release
description: Learn about the bug fixes in the 2026.06.0 release of Adobe Experience Manager Guides as a Cloud Service.

---
# Fixed issues in the 2026.06.0 release 

This article covers the bugs fixed in various areas of the 2026.06.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2026.06.0 release](whats-new-2026-06-0.md).

Learn about [upgrade instructions for the 2026.06.0 release](upgrade-instructions-2026-06-0.md).

## Authoring

- Copying and pasting `<keywords>` inside `<topicmeta>` within `<keydef>` or `<topicref>` inserts unintended foreign tags. (GUIDES-45800)
- Images with dimensions specified using units (for example, mm) are not rendered with the expected size, causing them to display using their original dimensions. (GUIDES-46275)
- When editing image dimensions with unit-based values (for example, in, mm, or px) in Author mode, the width and height fields keep increasing unexpectedly when switching between them multiple times. (GUIDES-45929)

## Asset Management

- When selecting a large number of folders (more than 30) in the Bulk move tool, the selected folders list expands without scrolling support, causing destination fields and action buttons to become inaccessible within the dialog. (GUIDES-45805)
- When a map contains an external `topicref` pointing to a non-DITA resource (such as `.html` or `.htm`), its preview is not displayed in the Assets UI. (GUIDES-45409)
- Copying an asset from the Assets UI triggers a DXML Reprocessing Failure notification even though the copy operation completes successfully. (GUIDES-45012)
- When opening the Filter Panel in the Assets left rail within a folder, the search field and facets remain disabled until the panel is closed and reopened. (GUIDES-42652)
- Automatic bulk asset processing triggers processing of unsupported and intermediate assets, resulting in failures for content fragments and unintended processing of untranslated assets created by the Translation V2 workflow. (GUIDES-42582)

## Publishing

- When working with PLT and CSS files in PDF templates, the Generate IDs option is available in the right-click context menu despite not being applicable to these file types. (GUIDES-45254)
- When reopening a newly created Native AEM Site preset after a browser refresh, the Save button appears enabled even though no changes have been made to the preset. (GUIDES-45171)
- When duplicating a Native PDF preset that is marked as the default, the duplicated preset is also marked as the default, resulting in multiple presets being designated as default. (GUIDES-44786)
- Applying the output class attribute to MathML expressions is not propagated to the merged HTML and PDF output. (GUIDES-44393)
- Bulk activation of AEM Sites output generated using the new AEM Sites template fails, preventing successful replication of the generated content to the publish instance. (GUIDES-44049)
- A jackson-databind vulnerability was identified in the DITA-OT package bundled with AEM Guides. (GUIDES-43081)
- Opening a Native AEM Sites output from a Map Collection results in a resource not found error, preventing access to the generated output. (GUIDES-42065)
- When generating Native PDF output for a DITA map containing `<reltable>`, the related topic links defined in the `<reltable>` are not rendered, resulting in missing "Related" sections in the generated PDF. (GUIDES-38333)
- When a sub-map is referenced with `processing-role="resource-only"`, orphan pages are generated in the output despite the sub-map not being intended for output generation. (GUIDES-37650)
- When generating Native PDF output for certain content, only the first page is rendered in the PDF despite the intermediate HTML containing the complete content across multiple pages. (GUIDES-28270)
- For Native PDF output, page numbers are read immediately after the logo instead of being read after the main content. (GUIDES-27790)
- When generating PDF output with a color bar, the color bar is not rendered at full width, and overlapping of the middle sections causes some color blocks to be hidden. (GUIDES-15505)
- The CSS `:is()` pseudo-class selector is not applied in Native PDF output, resulting in styling differences compared to browser rendering. (GUIDES-11328)

## Translation

- Applying a baseline to a map with many assets delays loading of the translation report for the selected language, sometimes leading to request timeout before the report renders. (GUIDES-45508)
- Language groups configured under Translation tab within Workspace settings are not retained when selected languages are of hyphenated or underscore locale formats. (GUIDES-37843)

## Review

- The Version history icon in the Review UI does not display a tooltip in the Left panel adjacent to the topic name. (GUIDES-45511)
- On certain screen resolutions, the document view of the Review UI displays a horizontal scrollbar, causing content with long paragraphs to extend beyond the visible area and impacting readability during review. (GUIDES-44082)
- When editing an active review task, removing and re-adding the same topic before saving the changes results in the loss of previously assigned reviewer information. (GUIDES-38774)

## Map collections

- When a map with a long name is added to a map collection, the map collection UI is rendered in a distorted layout. (GUIDES-42062)

## Learning

- While publishing, short answer questions are not rendered with the expected styling. (GUIDES-46478)
- Subtitle (VTT) files are not visible in Repository or Explorer view after upload, despite being expected to appear with a generic file icon. (GUIDES-46014)
- When inserting questions using the Insert from Question Bank option, the Insert from Question Bank dialog flickers or resizes unexpectedly upon opening. (GUIDES-45524)
- When selecting a SCORM output template after its title has been modified, an application error is encountered, preventing the template from being selected. (GUIDES-45521)
- When inserting questions using the Insert from Question Bank option, an error occurs if the question title contains an image. (GUIDES-45383)
- Publishing SCORM output from Safari browser results in the package being downloaded as a folder instead of a ZIP file, along with rendering and functionality issues in the generated content. (GUIDES-45119)
- When generating PDF output for courses containing videos, the video content is not rendered and only the file path is displayed instead of a representative placeholder image such as a video thumbnail or poster image. (GUIDES-45117)
- A delay is observed before the Next button becomes enabled for courses, impacting the learner navigation experience. (GUIDES-45113)
- When adding questions to a quiz using the Insert from Question Bank option, short answer questions are not listed despite having a valid Question ID. (GUIDES-44942)
- When transferring large SCORM ZIP files from the microservice to AEM, the upload back to Guides fails. (GUIDES-44554)
- When loading video content in HTML preview, the source path includes an appended rendition path instead of retaining the original file path, preventing the video from rendering correctly. (GUIDES-41776)

## New Editor

- When accessing the Review Task page in the New Editor, page breaks between topics are not displayed, resulting in the continuous rendering of content sections. (GUIDES-46777)
- When accessing the top toolbar in the New Editor, the Citations and Snippets options are not available, preventing insertion of citations and snippets through the toolbar. (GUIDES-46538)
- In the New Editor side-by-side mode for the Review of a topic, the review comments in the right panel are slightly left-shifted, resulting in misalignment. (GUIDES-46061)
- When applying a scale attribute to a table in the New Editor, the table is not rendered at the configured size in Author and Preview modes. (GUIDES-45984)
- Pasting images from external sources does not insert them into the topic. (GUIDES-45983)
- In the New Editor, key references in titles derived from a keyword map are not resolved in the TOC and topic tabs after saving or refreshing the content. (GUIDES-45799)
- On Windows, copying and pasting a table row adds unwanted attributes to the table, resulting in markup errors and preventing the document from being saved. (GUIDES-45784)
- When content is copied from a map or topic using the Copy option in the context menu and then pasted, unexpected extra `<data>` tags are inserted into the pasted content. (GUIDES-45703)
- When navigating through a table with tag view enabled, pressing the Up Arrow key from a cell below a collapsed entry tag skips the collapsed tag and moves the cursor to a higher cell than expected. (GUIDES-45408)
- When performing an action from the table contextual toolbar, the toolbar closes unexpectedly, interrupting subsequent table operations. (GUIDES-45405)
- Copy-pasting content in the same topic into an invalid location in the Editor inserts an unintended foreign tag. (GUIDES-45378)
- When using the Copy Path or Copy UUID options for an image, the copied value returns the rendition path instead of the original asset path. (GUIDES-45278)
- When deleting an XML comment using the Backspace key, the comment tag is not removed after its content is deleted, and the deletion operation continues into the preceding element. (GUIDES-45240)
- When working with MathML content in the New Editor, the Edit MathML option is available and allows modifications even when the content is in read-only mode or checked out by another user. (GUIDES-45172)
- Cursor moves to an arbitrary position instead of inside the newly added tags after using Insert After or Insert Before from Outline View and Breadcrumb. (GUIDES-45147)
- When a conref is applied to a paragraph within a list item, the conref icon overlaps the `<p>` tag instead of maintaining the expected spacing. (GUIDES-45131)
- Opening a review task in the Editor using Side-by-Side view for the commented version displays the version as None instead of the associated version. (GUIDES-45127)
- When moving content selected from within a `cmd` element that includes a nested `ph` tag into a paragraph, the entire parent element hierarchy is retained instead of inserting only the selected content. (GUIDES-28191)
- When dragging a partial selection from a `cmd` element, the content cannot be dropped between existing text or at the end of another `cmd` element. (GUIDES-44883)
