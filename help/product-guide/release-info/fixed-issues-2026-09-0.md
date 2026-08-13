# Fixed issues in the 2026.09.0 release

This article covers the bugs fixed in various areas of the 2026.09.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2026.09.0 release]().

Learn about [upgrade instructions for the 2026.09.0 release]().

## Editor 2.0

- Copying a table from Author mode and pasting it into Author mode removes attributes such as `colwidth` and any other attributes defined on `colspec`, causing the column width settings to be lost. (GUIDES-52916)
- Whitespace entered immediately before an inline tag within a table cell `<entry>` is deleted. (GUIDES-49144)

## Authoring

This section covers the bugs fixed in the Authoring that are common to both Editor 1.0 and Editor 2.0.

- Inserting a root map-defined keyword from a referencing topic inserts an empty keyword element instead of displaying the keyword selection dialog. (GUIDES-48304)
- Saving a topic when Schematron validation is configured with an empty rule file shows an inaccurate, generic error message. (GUIDES-48106)
- Schematron rules using a text-node context does not trigger validation. (GUIDES-14500)
- Inserting a cross-reference using the **Web link** option adds a `scope=local` link and modifies the `href` value, instead of inserting an `scope=external` as expected. (GUIDES-48457)
- Saving a referencing map results in a broken reference instead of resolving to the correct map when one author moves the referenced map while another author is concurrently adding a reference to it in an unsaved map. (GUIDES-47467)

## Asset management

- The asset status API does not return the correct status for assets whose path contains a comma. (GUIDES-49065)
- The DITA element filter in the Assets Admin Search Rail does not apply the entered value, so search results are not filtered. (GUIDES-48450)
- The version purge utility fails to complete in several scenarios, including certain file types, assets with missing metadata, and large reports, instead of completing the purge and generating an accurate report. (GUIDES-43453)
- Renaming an asset to another unique identifier through the move operation causes the identifier shown in the Editor and in the Assets UI to no longer match the identifier stored with the asset. (GUIDES-43006)

## Publishing

- When you generate AEM Sites (with composite component mapping) output with a baseline targeting an older version, the page content correctly shows that older version, but the page metadata shows the current version instead. (GUIDES-49325)
- When pages are replicated using bulk activation, replication tracking properties are set only on the root page and not on child pages, making it difficult to determine what content changed since the last replication. (GUIDES-37871)
- When the **Label** field in the Create/Edit Baseline dialog receives focus for the first time, pasting or typing the first character does not filter the autocomplete suggestions correctly, and the field displays all suggestions instead of the filtered results.(GUIDES-50143)
- Branch filtering generates extra pages for unwanted topics used as `keydef` (which are marked `resource-only ="true"` by DITA-OT). (GUIDES-19701)
- The Map Collection enables the **Publish** option for presets that have not yet been generated. (GUIDES-50510)
- The Publishing history section does not display placeholder text when a newly created map collection has no publishing records. (GUIDES-50366)
- Applying an ICC color profile on a Native PDF preset causes output generation to fail, and CMYK colors do not render correctly even when a direct profile path is used. (GUIDES-47137) 
- The bleed setting configured on a Native PDF preset is not reflected in the generated output. (GUIDES-47034) 
- The **Text before break** field for table continuation only renders the localized string and does not substitute the page number placeholder. (GUIDES-32872) 
- The ICC profile browser incorrectly displays DITA files instead of showing only ICC files. (GUIDES-25017) 
- Draft comments are not being rendered in the Native PDF output. (GUIDES-47044) 
- A draft comment placed inside a `title` element appears unexpectedly in published output. (GUIDES-10686) 

## Translation

- Starting a translation using an XLIFF project creates an empty project that never moves to an in-progress state. (GUIDES-51759)
- Moving content from one language folder to another using the assets move operation prevents authors from selecting that content for translation in the Translation panel. (GUIDES-49386)
- Adding a translation sync to an existing project while another language sync for the same project is still in progress can prevent the system from creating jobs for some requested languages, without indicating that those languages were dropped. (GUIDES-49354)

## Baseline

- After an author selects and saves a baseline for publishing on a preset in the Map Dashboard or Map Console, refreshing the page does not retain the selected baseline, and the UI incorrectly displays *No baseline used*. (GUIDES-52690)

## Review

- Opening the Review panel or applying a project filter takes some time to load the task list. (GUIDES-48893) 

## Learning content

- When a new learning topic is created using a HTML or learning template with a custom header, the topic title doesn’t appear in the custom header (GUIDES-52343)
- The calculated accuracy percentage for a course quiz differs slightly from the expected value. (GUIDES-52346)
- For a course, when attempting a quiz, the marks scored differs slightly from the expected calculated score. (GUIDES-52345)