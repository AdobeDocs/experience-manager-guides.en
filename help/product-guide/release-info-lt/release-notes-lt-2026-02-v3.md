---
title: Release Notes | What's New in February 2026 release of Product Training and Learning content
description: Learn about the new and enhanced features in the February 2026 release of Product Training and Learning content
role: Leader
hidefromtoc: yes

---
# February 2026 release of Product Training and Learning content  

This release note covers the new and enhanced features introduced in February 2026 release of Product Training and Learning content. In addition, all the reported issues and bugs have been resolved in this release, ensuring improved stability and performance.

## New enhancements

- **Support for subtitles**: You can now add subtitles to quizzes and topics using the new **Add Subtitle** option in **File Properties**, making learning content more descriptive and accessible.
- **Enable or disable negative scoring**: While configuring quizzes, you can now choose to enable or disable negative scoring. This flexibility allows you to enforce a minimum score of zero, even when negative marking is applied.
- **Delete widgets easily**: In addition to deleting quiz questions, you can now delete widgets—such as accordions, flip cards, and tabs—using the **right‑click > Delete** option, simplifying content management.
- **Pin answer choices**: You can now pin specific answer choices so their order remains unchanged, even when answers are randomized during SCORM output generation. This is especially useful for options like *All of the above* or *None of the above*.
- **Numerical question type**: A new numerical question type allows you to create quiz questions that accept numeric answers with validation and configurable error margins. This is ideal for math, science, and technical content where minor variations due to rounding or unit conversions are expected.
- **Sequential attempt for quiz questions**: A new setting for SCORM output lets you enforce sequential quiz attempts. When enabled, learners must answer each question before moving to the next. Navigation is restricted until the current question is completed, ensuring a guided and consistent learning experience.


## Fixed Issues

The following issues have been resolved in the February 2026 release of Product Training and Learning content.

- When publishing the SCORM output and deploying it on ALM, the L2 Quiz report shows incorrect total and maximum scores for quiz that use multiple attempts and randomized question bank selection. (GUIDES-38855)

- When selecting a new language from language variables in Experience Manager Guides, the UI continues to display other languages and not the selected language. (GUIDES-38854) 

- When any course is generated on the IBM cloud server, an unintended white space appears below the IBM copyright footer due to the `coralui3.css` stylesheet, causing layout inconsistency. (GUIDES-38853)

- When Learning course with an accordion is navigated using the keyboard, the + sign or the tab title is not highlighted, preventing visual identification of the active element. (GUIDES-38852)

- For courses generated using the IBM SCORM carbon template or the default template, when accessed on a mobile device in landscape mode, the Table of Contents (Course Menu) fails to display module links preventing navigation. (GUIDES-38851)

- When replicating the hierarchy for a course in Experience Manager Guides, creating a Learning object requires first creating a Learning group, as object‑level additions are not supported. (GUIDES-38849)

- Attempts to access the dropdown options in a Match the following question of a quiz using the keyboard fails as the options do not respond to tab or arrow key preventing navigation. (GUIDES-38985)

- When the Experience Manager Guides API is used to automate SCORM generation, intermittent failures occur in the API response resulting in inconsistent SCORM build automation. (GUIDES-38846)

- Applying a heading style preset causes the selected text to disappear, likely due to the font color changing to white, making the text un-selectable and not visible. (GUIDES-39981)

- When using Experience Manager Guides on Mozilla Firefox, the Flip card displays the front‑side text in reverse on the back side after flipping. (GUIDES-39983)

- When you click the Table of Contents (TOC) in the left pane for the course, the course continues to show a completion status even if the quiz has been failed. (GUIDES-40398)

- Attempting Match the Following question in a quiz incorrectly in ALM, results in the selected options not appearing in the report. (GUIDES-38640)

- When generating the PDF output, the applied authoring styles are not preserved, resulting in inconsistencies in design.(GUIDES-38642)

