---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2025.06.0 release
description: Learn about the bug fixes in the 2025.06.0 release of Adobe Experience Manager Guides as a Cloud Service.

---
# Fixed issues in the 2025.06.0 release 

This article covers the bugs fixed in various areas of the 2025.06.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2025.06.0 release](whats-new-2025-06-0.md).

Learn about [upgrade instructions for the 2025.06.0 release](upgrade-instructions-2025-06-0.md).

## Authoring

- When opening a DITA map with the unified shell enabled, the editor refreshes intermittently. (26919)
- Failing to close JCR session connections while updating or creating topics result in memory leaks and service downtime. (26282)

## Publishing

- Native PDF publishing continues indefinitely, if the DITA content has a weblink without having scope as external. (26434) 
- Publishing of Native PDFs and AEM sites stalls and gets queued, when there are errors in the content. (26516)
- 

## Review

- Updating the details of a review task in the Review dashboard does not confirm whether the update was successful or unsuccessful. (8051) 

## Known Issues

Adobe has identified the following known issues for the 2025.04.0 release:

- The reference count in the Baseline UI does not update upon editing the Baseline. It only updates when the changes are saved. (28015)
- When multiple tabs are open in the Editor, performing an **Undo** operation in the **Source** view of a file reverts the last edit but also switches to the previously opened tab. (27891)
- The **AEM Spell Check** option appears in the **Menu** dropdown list, even when the **Browser spell check** option is enabled in the Editor settings. (27993)
- An additional version is created and shown in the **Version History** panel when you edit an image in the Assets UI and save it. (28001) 
- An empty line is automatically inserted when pasting new content into a new line within a `codeblock` element.(27842)
- Switching between presets that use the same Baseline deactivates the **Save** button for the current preset. (28025) 
- A topic within a DITA map fails to publish in the AEM Sites output when it is being used as both `keydef` and `topicref` within its submaps. (22269)
- In AEM Sites output, images break when Baseline is not applied while publishing. (28043)
- An application error occurs when multiple topics of a map are edited and then closed using the **Close all** option, with the **Ask on save version on close** setting enabled.(27931)
