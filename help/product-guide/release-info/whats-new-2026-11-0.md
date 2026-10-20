# What's new in Adobe Experience Manager Guides 2026.11.0

## Create and Import skills in Guides AI

*Source: GUIDES-52400*

Adobe Experience Manager Guides adds Create and Import skills to Guides AI chat, which help contributors who are not DITA experts work with repository content. The skills offer these capabilities:

- Create generates DITA topics from a natural-language prompt, with an optional reference image and existing topics as style examples.
- Import converts a PDF, DOCX, or Markdown file into DITA, with a review step before topics are created.

The Guides AI panel also supports fullscreen mode and an active conversations section. Learn more in the Guides AI documentation.

## Help Assistant as a separate panel

*Source: GUIDES-55166*

Adobe Experience Manager Guides now offers the generative AI-powered Smart Help in its own Help Assistant panel, opened from a dedicated button. Authoring and help previously shared one AI panel with separate tabs. With the split, you open the panel that fits the task: the AI Assistant panel for authoring, or the Help Assistant panel for product guidance.

Administrators configure both panels in the workspace settings. In the **AI Assistant** section, they choose between the Guides AI panel and the standard AI authoring panel. A separate **AI help assistant** section includes a toggle that turns the Help Assistant panel on or off. Learn more in the Help Assistant documentation.

## Track changes panel in the new editor

*Source: GUIDES-38126*

The new editor in Adobe Experience Manager Guides now includes a Track Changes panel that lists every tracked change in a topic. You can accept or reject changes from the panel, and comments are tracked along with content edits. Changes by the same author next to each other are merged, which keeps the panel readable. The panel requires the track changes feature flag. Learn more in the Track Changes documentation.

## Explorer sorting in the Web Editor

*Source: GUIDES-41093*

The Explorer panel in the Web Editor now sorts files and folders by the display preference in your user preferences, either title or file name. Items appear in ascending order by default, and a sort button in Explorer switches the order to descending. This helps you browse for topics and maps without leaving the editor. Learn more in the Explorer documentation.

## Version labels and history for non-DITA files

*Source: GUIDES-38274*

Adobe Experience Manager Guides now lets you manage version labels and version history for images, multimedia, and other non-DITA files from the editor. When you open one of these files from the repository or Explorer, a toolbar offers these options:

- Version label, which assigns or changes labels the same way as for DITA topics.
- Version history, which compares versions, shows labels and comments, and reverts to an earlier version.

Because baselines select versions by label, this helps you align image versions with content releases. Files such as ZIP, PDF, and DOCX open with a preview when a rendition is available. Learn more in the version label documentation.

## Review initiators can add comments

*Source: GUIDES-38670*

Authors who start a review in Adobe Experience Manager Guides can now add comments and annotations to topics before they send the review. Reviewers see these comments with the same experience as reviewer comments. Initiators can comment across all selected topics and view the conditions applied to them. The review dashboard shows the comment count and the author name under the Reviewers column. Initiators have the reviewer experience, except that **Mark As Done** and **Delegate** are hidden. Learn more in the review documentation.

## Output History tab in Map Console

*Source: GUIDES-53702*

The Map Console in Adobe Experience Manager Guides now includes an Output History tab, so you can review output generation for your map without switching to the Map Dashboard. The tab lists each output with its status and supports these tasks:

- Search and filter outputs by status, preset type, or generation date
- Cancel an in-progress generation
- Open an output or view its log
- Delete a finished entry
- Export the history to a CSV file

Status updates appear when you refresh the view. Learn more in the Output History documentation.

## Output status colors in Map Console

*Source: GUIDES-15239 (can be merged into the Output History entry above)*

Outputs in the Map Console now show a status color that matches the Map Dashboard, including a yellow status when generation finishes with errors. This tells you when to check the log for warnings, such as a missing image, without opening every log. Learn more in the Output History documentation.

## Output History purge options

*Source: GUIDES-4365*

Output History purge settings in Adobe Experience Manager Guides now include two options:

- Keep only the most recent entries, based on a number you set
- Purge only the log file and keep the history entry for audit

Purging by age previously removed the entire entry, including its log. These options help you reduce repository size while keeping a record of past outputs. Learn more in the Output History documentation.

## Generated and Published History in Map Collections

*Source: GUIDES-49986*

Map Collections in Adobe Experience Manager Guides now show the generation and publishing status of each map. When you generate many maps at once, you can check progress from the Map Collections view instead of opening the Outputs tab of every map. This helps you spot failed maps sooner. The new Map Collections experience is on by default in this release. Learn more in the Map Collections documentation.

## GitLab support for Edge Delivery Services profiles

*Source: GUIDES-45440*

Publishing profiles for Edge Delivery Services now support GitLab repositories in addition to GitHub. You select GitLab as the server type, enter your GitLab OAuth credentials, and publish DITA content to an Edge Delivery Services site hosted in GitLab. Teams that must keep their code in GitLab no longer need to migrate to GitHub to publish from Adobe Experience Manager Guides. Learn more in the Edge Delivery Services documentation.

## Salesforce profiles support Proof Key for Code Exchange

*Source: GUIDES-55570*

Salesforce publish profiles in Adobe Experience Manager Guides now support Proof Key for Code Exchange (PKCE) during validation. Salesforce connected apps that require PKCE previously returned a missing code challenge error when you selected **Validate**. You can now validate the profile and publish to these organizations without changing the Salesforce security policy. Learn more in the Salesforce publishing documentation.

## Changed assets only in Salesforce publishing

*Source: GUIDES-37850*

Salesforce publishing in Adobe Experience Manager Guides now uploads a referenced asset only when it has changed since the last publish. Unchanged images, PDFs, Excel files, and ZIP archives keep their existing Salesforce version, and a changed asset updates its existing Salesforce file instead of creating a duplicate. The **Upload images** and **Upload linked documents** options are on by default for new presets. When several topics reference the same changed asset, Salesforce can still create extra versions of it. Learn more in the Salesforce publishing documentation.

## Categorized Salesforce publishing results

*Source: GUIDES-33718*

Salesforce publishing in Adobe Experience Manager Guides now returns a categorized result summary after each publish. Topics are grouped as follows:

- Published
- Excluded by conditions
- Failed, with the Salesforce error and the affected field

The summary also shows topic-level stages and a link to view the article in Salesforce. This helps authors find what failed without reading raw logs. Some errors, such as an archived article conflict, still show a generic message. Learn more in the Salesforce publishing documentation.

## Images from map metadata in Native PDF

*Source: GUIDES-23044*

Native PDF output now resolves an image defined in a DITA map, bookmap, or custom map metadata. You can use one PDF template for several maps and still show a different cover image for each. This reduces the number of templates you maintain. Learn more in the Native PDF documentation.

## Content Health checks for maps and baselines

*Source: GUIDES-13317, GUIDES-24312*

Adobe Experience Manager Guides adds a Content Health check at the map level, so you can find content problems before they affect generated output. The check covers:

- Baselines of the map
- Broken links
- Duplicate IDs
- DITA topic validation through Schematron rules

Content Health is on by default in this release. Learn more in the Content Health documentation.

## Upsert API enhancements

*Source: GUIDES-24015*

The Upsert API in Adobe Experience Manager Guides now creates or uploads an asset in a single call, so you no longer call create and update separately. Each request can include:

- A predefined GUID for the asset, instead of one generated from the file name
- Metadata applied when the asset is created
- A version label and comment, created with the asset

This helps when you import content from external systems. Learn more in the Upsert API documentation.
