---
title: Release Notes | Fixed issues in Adobe Experience Manager Guides, 2024.2.0 release
description: Learn about the bug fixes in the 2024.2.0 release of Adobe Experience Manager Guides as a Cloud Service.
exl-id: fae1ff07-6232-4e9a-a89e-5e760e807b9d
TQID: https://experienceleague.adobe.com/z-L0sZ2HH720nI3LyDjiIqujxSBP-QLdPqvEInNNRnE
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
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
    internal-label: Native PDF publishing
  - id: f89f75b0-cf2e-4e96-aec8-fe8c39cbd0ef
    internal-label: Web Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
---
# Fixed issues in the 2024.2.0 release 

This article covers the bugs fixed in various areas of 2024.2.0 release of Adobe Experience Manager Guides as a Cloud Service.

For more information about the new features and enhancements, view [What's new in the 2024.2.0 release](whats-new-2024-2-0.md).

Learn about [upgrade instructions for the 2024.2.0 release](upgrade-instructions-2024-2-0.md).



## Authoring

- Spell check in the Editor does not allow the selection of suggestions. (15045)
- The global navigation button is not working, and the dashboard fails to load. (14968)
- In the Web Editor, the download map feature fails to trigger a pop-up notification when it is ready to download. (14626)
- In the Web Editor, the download map feature fails to download a map with baseline. (14622)
- Invalid DTD Error in the October 2023 release of Experience Manager Guides as a Cloud Service. (14482)
- Dragging a glossary topic from the repository into a glossary map creates `topicref`. (10767)
- The preview screen for snippets is frozen. (14840)
- Labels from the `labels.json` file appear in random order in the Web Editor. (10508)

## Publishing

- In Native PDF publishing, custom attributes within condition presets are not working for Native PDF publishing. (14943)
- In Native PDF publishing, key references are not getting resolved for December 2023 release  of Adobe Experience Manager Guides. (15085)
- AEM Sites publishing fails and causes scope errors for files having `xref` to the DITA file that start with “HTTP”. (15154)
- Unable to add a custom template from the **Outputs** tab in the Editor. (14846)
- **AEM Site** preset is not working due to an empty template path. (14804)
- AEM Site regeneration fails for DITA maps with topics that contain MathML equations. (14790)
- In Native PDF publishing, PDF generation throwing errors in getting dependencies for `Node.js` publishing. (14445)
- AEM preset doesn't allow the selection of a template outside the `/content` hierarchy in the Web Editor. (14260)
- In the AEM Sites output,  the style or the line breaks were lost for the `<lines>` element having sub-elements. (12542)
- Custom metadata is not available in the final output. (12116)
- In Native PDF publishing, the DITA map metadata properties cannot be used to populate the metadata for PDF file output. (15159)



## Management

- **Baseline Filter** files are not working with File Name in the Web Editor. (13486)
- Disabling the indexing the parent DITA map to get a better performance may impact the functionality of certain features.(12213)


## Review

- Right-click context menu is not working for **Accept** or **Reject** track changes. (14607)
- Toggle to close DITA topics in the Review Screen is not working in the December 2023 release  of Adobe Experience Manager Guides. (14537)
- Customizing email templates for review workflow doesn't work with overlay. (13954)

## Known Issue

Adobe has identified the following known issue for the 2024.2.0 release:

- Version 1.0 isn't displayed on the UI for the duplicated DITA file.
- Propagation of asset metadata does not work for the 2024.2.0 release with microservice enabled for any preset.
