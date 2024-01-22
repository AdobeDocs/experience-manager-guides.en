---
title: Release Notes | Upgrade instructions and fixed issues in Adobe Experience Manager Guides 4.4.0 release
description: Learn about the bug fixes and how to upgrade to  4.4.0 release of Adobe Experience Manager Guides
---
# 4.4.0 release of Adobe Experience Manager Guides (February 2024)

This release note covers the upgrade instructions, compatibility matrix, and issues fixed in version 4.4.0 of Adobe Experience Manager Guides (later referred as *Experience Manager Guides*).

For more information about the new features and enhancements, see [What's new in 4.4.0 release of Adobe Experience Manager Guides](./whats-new-4.4.md).

## Upgrade to 4.4.0 release of Experience Manager Guides


You can easily upgrade your current version of  Guides to version 4.4.0. Before you proceed with upgrading to version 4.4.0 of Experience Manager Guides, you must consider the following points:


- If you are using version 4.3.1, 4.3.0, or 4.2.1.3, then you can directly upgrade to version 4.4.0.
- If you are using version 4.2, 4.1, or 4.1.x then you need to upgrade to version 4.3.1, 4.3.0, or 4.2.1.3 before upgrading to version 4.4.0.
- If you are using version 4.0 you need to upgrade to version 4.2 before upgrading to version 4.3.x.
- If you are using version 3.8.5, you need to upgrade to version 4.0 before upgrading to version 4.2.
- If you are on a version prior to 3.8.5, refer to the Upgrade Experience Manager Guides section in the product-specific installation guide.



>[!NOTE]
>
>You must install AEM service pack before upgrading Experience Manager Guides version.

For details, see [Upgrade instructions](../install-guide/upgrade-xml-documentation.md).

## Compatibility matrix

This section lists the compatibility matrix for the software applications supported by Experience Manager Guides 4.4.0 release. 

### Adobe Experience Manager

**4.4.0 Non-UUID**
Version 6.5 Service Pack 19, 18, 17

**4.4.0 UUID**
Version 6.5 Service Pack 19, 18, 17

For more details, see the *Technical requirements* section in the Install and configure Adobe Experience Manager Guides guide.

### FrameMaker and FrameMaker Publishing Server

|Release| FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
|4.4.0 (Non-UUID)| 2022 or higher |2020.2 or higher* | 2022 or higher | 2020.3 or higher |
|4.4.0 (UUID) | 2022 or higher | 2020.2 or higher*  | 2022 or higher | 2020.4 or higher |
| | | | |

*Baseline and conditions created in AEM are supported in FMPS releases starting from 2020.2.

### Oxygen Connector

| Release | Oxygen Connector Windows | Oxygen Connector Mac | Edit in Oxygen Windows | Edit in Oxygen Mac |  
| --- | --- | --- |--- |--- |
| 4.4.0 (Non-UUID)|  2.3-regular-5| 2.3-regular-5 |  1.6 | 1.6  |
| 4.4.0 (UUID) | 3.2-uuid-5|3.2-uuid-5 |2.3 | 2.3  |
|  |  |   |  



### Knowledge base template version

|Components package name| Components version | Template version|
|---|---|---|
|Experience Manager Guides Components Content Package for Cloud Service|dxml-components.all-1.2.2| aem-site-template-dxml.all-1.0.15|

## Fixed issues

The bugs fixed in various areas are listed below:

### Authoring

- Spell check in the Editor does not allow the selection of suggestions. (15045)
- The global navigation button is not working, and the dashboard fails to load. (14968)
- In the Web Editor, the download map feature fails to trigger a pop-up notification when it is ready to download. (14626)
- In the Web Editor, the download map feature fails to download a map with baseline. (14622)
- Invalid DTD Error in the Experience Manager Guides as a Cloud Service version 2310. (14482)
- The title in the Web Editor tab gets truncated after a dot(.) character. (14372)
- Error messaging for duplicate map names in Assets UI isn't updated. (14320)
- An error occurs in version creation logic during drag-and-drop of assets. (14291)
- Reusable content skips the element IDs. (14213)
- The setting control to hide **Language Variables** panel under **Output** tab is missing. (14194)
- The Web Editor throws application errors when adding a new reference or topic using a specialized schema in the **Layout** view. (14094)
- The space after conref `<ph>` element disappears on saving the topic. (13642)
- An application error occurs when trying to save DITA files before the post-processing is complete. (13571)
- An anchor link to `<dlentry>` or `<dt>` element fails to display the link text. (13543)
- The **Favorites** collection in the Web Editor fails to load. (13495)
- If the title of a topic contains a slash `/`, the tab in the Web Editor only shows the letters coming after it. (13455)
- The image preview doesn't disappear after displaying the preview in the Web Editor. (13454)
- Citations display non-clickable links when created with a unique ID with spaces. (13447)
- On closing a topic after editing it, you are redirected to the AEM Home page instead of returning to the folder view. (13306)
- Insert keyword pop-up does not appear when using root map-defined keys in other topics. (12950)
- Close icons are not visible when very tall graphics are previewed in the **Version History** panel. (12867)
- Unable to modify the timezone of **Version Created On** column for the Baselines. (12711)
- Zip files are not recognized in the Web Editor, and you cannot drag and drop them. (12709)
- The **Version History** panel in the Assets UI shows an incorrect timestamp for the **Current** field. (12624)
- In the **Layout** view for a Bookmap, using **Move Right** to make a selected chapter a sub-element does not work. (12567)
- Delay occurs in the post-processing of files that have been copied and pasted into the cloud services. (12457)
- Creating a DITA file from a template with a filename starting with numeric characters results in a namespace error. (12188)
- The rootmap setting persists in the Web Editor even if the user has not set it explicitly from the **User Preferences**. (11551)
- The content with some attributes applied is not being highlighted in **Author** or **Preview** mode. (11063)
- In the Web Editor, the **Key References** window opens when inserting the `varname` tag. (10940) 
- Dragging a glossary topic from the repository into a glossary map creates `topicref`. (10767)
- XML Editor's Preview window is truncated in Google Chrome and Microsoft Edge browsers. (10755)
- The Web Editor lacks the ability to wrap an element inside the possible parent elements. (8791)
- The Web Editor gets uninstalled after reinstallation of Adobe Experience Manager Guides version 4.3.1. (14519)
- The installer of version 4.3.1 encounters a filter conflict, resulting in the overriding of `apps/cq/core/content/projects/properties`. (14517)
- A self-reference link appears under the list of **Broken Links** in Reports. (13539)

### Publishing

- In Native PDF publishing, Custom attributes within condition presets are not working for Native PDF publishing. (14943)
- Unable to add a custom template from the **Outputs** tab in the Editor. (14846)
- **AEM Site** preset is not working due to an empty template path. (14804)
- Topics containing MathML equations causing errors in DITA map. (14790)
- In Native PDF publishing, PDF generation throwing errors in getting dependencies for `Node.js` publishing. (14445)
- **AEM Site** preset doesn't allow the selection of a template outside the `/content` hierarchy in the Web Editor. (14260)
- The functionality to publish as content fragment is not working for files listed in search results. (14090)
- Fmdita components have a hardcoded path of `delegator.jsp`, preventing the overlay of AEM Sites components. (13993)
- The tagged view of PDF reactor in Native PDF publishing output isn't working as expected. (13622)
- In Native PDF publishing, the background color selection on the **Template** layout requires a page reload when reverting to `None`. (13621)
- AEM Site publishing encounters an issue when committing to the datastore for large maps with scope peer links. (13531)
- Issue occurs in committing to datastore for a large DITA map with scope peer links in AEM Site publishing. (13530)
- Incorrect icon and tooltip are displayed for  **Edit content** option in the **Page Layouts** toolbar of the Templates used in Native PDF publishing. (13492)
- Unable to activate a site using Experience Manager Guides **Bulk Publish Dashboard**. (13439)
- In Native PDF publishing, accessibility is compromised as images in header and footer doesn't display alt text. (12829)
-  In the AEM Sites output,  the style or the line breaks were lost for the `<lines>` element having sub-elements.(12542)
- Duplicating page layout in Native PDF doesn't work with no extension added automatically. (12534)
- The localization of the element labels isn't functioning properly in the AEM Sites output. (12144)
- Custom metadata is not available in the final output. (12116)
- `fmdita rewriter` conflicts with the user's rewriter config and leads to the display of long URLs instead of the links. (12076)
- Missing **ditaval** option in folder profile level output presets created via Web Editor UI. (11903)
- In the **AEM Site**  preset, the option to **Generate separate PDF for every topic** is non-functional. (11555)
- Native PDF publishing lacks the support for CMYK color space conversion. (10754)
- (14492) On upgrading to version 4.3.1,  some exceptions occur in the Native PDF node.
- When generating the PDF output with Native PDF publishing, the file name is truncated after a period. (13620)
- Dynamic baseline calls are using the name instead of title, which results in the failure of Export DITA map API. (14268)

### Management

- Content reference is broken on copy-pasting the DITA files having self-reference links without GUID. (13540)
- AEM cloud environments encounter MongoWrite exceptions due to large-sized nodes. (13509)
- **Baseline Filter** files are not working with File Name in the Web Editor. (13486)
- In the Web Editor, the baseline shows the title for the previous version instead of the selected version of the DITA file. (13444)
- Disabling the indexing the parent DITA map to get a better performance may impact the functionality of certain features.(12213)
- Condition presets for large DITA maps aren't getting created. (10936)
- Unable to edit the presets for the collection's first maps while editing a map collection. (10649)
- Labels from the `labels.json` file appear in random order in the Web Editor. (10508)

### Review

- The preview screen for snippets is frozen. (14840)
- Right-click context menu is not working for **Accept** or **Reject** track changes. (14607)
- Toggle to close DITA topics in the Review Screen is not working in the version 4.3.1 of Adobe Experience Manager Guides. (14537)
- Side by side review panels of the previous and the current versions in the Web Editor are not correct in the Experience Manager Guides as a Cloud Service version 2310. (14156)
- Customizing email templates for review workflow doesn't work with overlay. (13954)
- The **Close** button on the Review page in the Experience Manager Guides takes the users to the AEM Homepage. (13535)
- Broken characters appear while creating the snippets in the Korean language. (13489)
- Korean attachments in the Experience Manager Guides Review screen aren't clickable. (13436)
- Map title gets cut off in the review and collaboration screen, with no option to view the full title. (13012)

### Translation

- The **Accept/Reject** buttons erroneously appear for auto-approved human translation. (14318)
- Internationalization (i18n) issues occur during the transformation of non-English DITA files to AEM pages. (14286)
- Auto approve isn't working sometimes, and exceptions occur if an incorrect value is set on **Translation Status**. (13607)
- The baseline exported from the Translation dashboard fails and doesn't open in the target language. (12993)
- Translated contents fail to sync from temporary translation projects, and DITA XML editor translation wizard incorrectly shows **In progress** status for approved jobs. (9938)

### Accessibility

- Unable to navigate through the author canvas user interface, as the focus becomes trapped in the Web Editor. (13517)


## Known Issue

Adobe has identified the following known issue for the 4.4.0 release:

- Version 1.0 isn't displayed on the UI for the duplicated DITA file.