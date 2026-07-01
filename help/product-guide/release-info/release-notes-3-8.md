---
title: Release Notes for Adobe Experience Manager Guides 3.8 and 3.8.5
description: Top new features and enhancements in 3.8 and 3.8.5 releases of Adobe Experience Manager Guides (earlier known as XML Documentation solution).
---

# Release Notes | Adobe Experience Manager Guides 3.8

**Disclaimer**:

*Adobe Experience Manager Guides* was formerly branded as *XML Documentation for Adobe Experience Manager*. Please note certain references within the documentation may still refer to prior branding but are still applicable to the current offering.

This release notes lists the top new features and enhancements in 3.8.x release of XML Documentation for Adobe Experience Manager.

## New features and enhancements in 3.8.5 release

### Bug fixes

The bugs fixed in 3.8.5 release are listed below:

- Baseline support is missing for the PDF output through FrameMaker Publishing Server.
- The check-out and check-in API for FrameMaker or Oxygen is not working correctly if the folder level permissions have been setup for various groups in AEM.
- Content preview is not displayed from the Assets UI page.
- 'Source' button is not working on the Assets UI page.
- When an image is inserted through the Insert Image feature of the Web Editor, the relative path of the inserted image changes to its absolute path.
- The FMPS preset drop-down list is not displayed in the UI with the latest 3.8 release.
- Favorites panel is not shown when it contains a large number of assets in DAM and a new favorite item is added from the XML Web Editor.
- Internal redirect *sling:mapping* which redirects all links is not working and displays long URLs (with internal paths) instead of the short URLs for the web pages.
- In List View, the Modified column displays 'External user' instead of the username when assets are uploaded or imported from the Assets UI page (except via Package Manager).
- The title is not shown correctly in the Topics tab on Map Dashboard.
- On enabling the node flattening feature, some unwanted junk characters are getting stored in the HTML output.
- Changes in the folder profile from the user preferences are not reloaded automatically for an already open file, but the browser needs to be refreshed.
- The output generated via the Download Map option has some missing topics if there are some validation errors.

## New features and enhancements in 3.8 release

### File naming configuration updates

While creating DITA topics in XML Documentation solution, users are allowed to use special characters as part of file names. This resulted in encoded URLs on generation of AEM site pages. To avoid this conversion in URL, the 3.8 release of XML Documentation solutions allows an administrator to define a list of special characters other than the default valid file name configurations (a-z A-Z 0-9 - _). This implies that although you can configure a list of special characters in a file name including a space, it will get replaced with a hyphen (-). 

### AEM site page name generation changes

While authoring, it is possible to have the same file name for one or more files under different folders. During the AEM site publishing process, the page names were getting appended with a suffix when there is at least a duplicate file name. With the 3.8 release of XML Documentation solution, the AEM site page name generation process has been fixed. The suffix gets appended to the generated page name only if there is a duplicate file name. 

### New features and enhancements

There are a number of new features and enhancements introduced in the following areas of the product.

#### Web Editor

- You can now choose a label from a drop-down list while creating a version of a topic from the Web Editor.

  ![Labels in a dropdown list](assets/labels-drop-down-saving-topic-res.avif)

- The Review panel in the Web Editor has now been made more powerful that gives you the capability to revert a topic to a version that was shared for review. You can easily incorporate review comments in the reviewed version without having to remember which version of the topic was shared for review.

  ![Revert topic to review version](assets/revert-review-topic.avif)

- A new visual cue has been introduced to indicate whether you are working on the latest version of a topic or an earlier version.

  ![Version cue](assets/old-version-icon.avif)

- A new Version History feature has been introduced in this release. Use the Version History feature to:
  - View a list of all versions of the currently active topic along with labels added for each version.
  - Revert to a previous version of the topic.

  ![Version History](assets/version-history.avif)

- A new Version Label Management feature has been added that allows you to apply labels to the current or earlier versions of a topic.

  ![Version Label Management](assets/version-label-management.avif)

- Added a new feature: "Approve for Publish" with which an author can mark an asset as approved and further lock it for editing.
- While initiating a review process, you can now filter topics based on their state.

  ![Select review topics based on their State](assets/review-select-topic-on-state.avif)

- The `<navtitle>` in a map is auto-populated with a topic's title added to the map file. You can also refresh the `<navtitle>` easily from the Web Editor.
- Previewing a table with a large number of columns is now displayed within the page area.
- You can apply multiple output classes at one go from the Properties panel (multiselect).
- While Previewing a topic, you can also generate (an unconditional) PDF output of a single topic directly from the Web Editor.

  ![PDF output from Preview](assets/pdf-output-from-preview.avif)

- Block a publishing request, if the output generation of the same preset is in progress.
- Added ability for only a set of privileged users to delete assets that have active back-references.
- Added a feature to view or copy the XML code from the Source View from the Assets UI even if the file is checked out by another user.

  ![XML Source view](assets/xml-source-view-from-assets-ui.avif)

- Filename is now replaced with the file's title in the Save dialog box, Reusable Contents panel, and Find and Replace panel.

#### Publishing

- **Allow Configuration of Sanitization Rules for Generated Site Pages**: As an administrator, you can define the sanitization rules for the filenames of generated AEM Site or DITA-OT output. Whenever you generate an AEM Site output or output using DITA-OT, you can configure below rules to sanitize the output-generated URLs or filenames:
  - Convert all characters to lowercase.
  - Replace special characters with a separator.
  - Restrict a long filename to a predefined number of characters.

- Easily push output from your author instance to the publish instance by using the Bulk Activation Dashboard. You can work with a single map or a map collection and choose the output preset that you want to use for publishing.

  ![Bulk Publishing Dashboard](assets/bulk-publish-dashboard.avif)

#### Performance improvements

- Node flattening for AEM Sites output: earlier the site node structure of the AEM Sites output was too deep. Now, you have the control to flatten the node structure for better performance.
- Support for the latest release of FrameMaker Publishing Server summer 2020 release.
- The temporary files generated during translation are now removed, which improves the translation process.

#### Other enhancements

- The dependency of DAM Update Asset workflow while post-processing DITA content has been removed. If there are any custom process steps defined under DAM Update Asset workflow, you must update those to execute after post-processing is complete.
- The initiator of the translation process now gets a notification in their Inbox when the translation job is successfully created.

### Bug fixes

The bugs fixed in 3.8 release are listed below:

- Audio objects are not displayed in the HTML output.
- Force Delete window displayed upon deleting a DITA topic shows multiple 'Force Delete' buttons.
- Transfer baseline to language copies does not work for baseline created using server-side view.
- Sometimes, version 3.0 of a topic appears as 3 in the side-by-side view, not allowing review comments to import.
- Slow loading of Referenced content details on the Baselines tab for moved DITA map.
- Reverting to an earlier version does not work for non-dita assets.
- A lot of empty _text nodes are getting created with AEM Sites output generation.
- XML Editor - Link resolution in imagemaps after page generation is not working.
- Apply Labels from the Baselines tab doesn't add labels on the referenced content like images.
- SVG files are getting downloaded in incorrect format via the Download Map option.
- Not able to edit content fragment in a List View.
- Unable to check out and open files within Oxygen XML Author using the connector.
- The `<alt>` element text is not visible in the Authoring view.
- The image asset is always displayed as Out of Date even when translated copy exists.
- Custom map-template title is incorrect, and the thumbnail is not displayed.
- Applied Brand Mark Elements Not Displayed in the Authoring View of the Web Editor.
- Linked Footnotes are not visible in the content.
- Color coding in the Web Editor doesn't work with specialized conditional attributes.
- The drop-down list for @keyref is not user-friendly, deeming it almost unusable for customers with a large number of @keyref.
- The variable text referenced by @keyref is not rendered.
- Oxygen connector || "Edit in Oxygen" button now opens the file in edit mode even if the file is not checked out.
- Custom output-presets are not getting created with a custom map template.
- Microsoft Word (.docx) to DITA conversion is not creating jcr:content node and allowing special characters for folder names.
- Once a MAP is moved (having more than 150 references), the references break, and errors are observed while opening topics.
- An image's resolution is incorrectly calculated when the image's width is changed.
- When an image is added in a `<codeblock>`, unwanted whitespaces are found in the AEM Site output.

