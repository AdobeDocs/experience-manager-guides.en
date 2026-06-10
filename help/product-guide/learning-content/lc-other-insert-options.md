---
title: Other options in the Insert menu
description: Learn about the insert menu options you can use in the Learning content.
feature: Authoring
role: User
exl-id: 8c12ed9b-6309-40bf-b264-a2323cd6f4b3
TQID: https://experienceleague.adobe.com/SWlP2-iWhN1x25K9s-mrMcfUTy5Fxv7TVWg6G2ucufc
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
    internal-label: Authoring
subfeature_v2:
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
    internal-label: Editor
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Other options in the Insert menu  

The other options available in the Insert menu in the Editor toolbar include:

- **Block quotes:** Adds block quotes along with citations to your content. 

    ![](assets/block-quote-learning-content.png){width="650"}

- **Code blocks:** Adds a code block to your content.

    ![](assets/code-block-learning-content.png){width="650"}
 
- **Iframes:** Inserts an iframe to the content to embed external web pages or interactive resources. You can configure the iframe properties using the **Content properties** panel, including the source URL, width, height, alignment, and the title. You can view the content added in the iframe by switching to the **Preview** mode as shown below. 

    **Author** view:

    ![](assets/iframe-learning-content.png){width="650"}


    **Preview** mode:

    ![](assets/iframe-learning-content-preview.png){width="650"}

- **H5P:** Adds interactive H5P package to your learning content. To add H5P content, place your cursor at the desired location and select **H5P** from the Insert menu. In the Insert H5P dialog, provide a reference to the H5P file you want to add to the learning content. 

    ![](assets/insert-h5p-lc.png)

    If you prefer to use the H5P content from your system, then first [upload the file in DAM](../user-guide/authoring-upload-existing-files.md) using the **Upload assets** option, and then have it part of Repository view/Assets. 
    
    ![](assets/upload-assets-option.png)

    Once done, review the H5P content in the Preview mode and published output. 

    >[!NOTE]
    >
    > Editing or creating H5P content is not supported within Adobe Experience Manager Guides. Prepare your H5P package externally before uploading.

    
- **MathML equation:** Inserts MathML equations to your content. You can create a MathML equation and select **Insert** to add it to your document. 

    ![](./assets/insert-mathml.png){width="350"}

    The equation is inserted with light gray background. At any time you can update an equation by right-clicking on an existing equation and selecting **Edit Math equation** from the context menu. For details on validating MathML equations in Experience Manager Guides, view [Validation of equations in the MathML editor](../user-guide/web-editor-other-features.md#validation-of-equations-in-the-mathml-editor).

- **Knowledge check:** Allows you to add questions in available formats (Single Correct, Multiple Correct, True/False, Match the Following, or insert from the question bank) to your topic for review and to confirm understanding without grading. These questions mirror standard formats and exclude scoring, making them ideal for self-assessment and suitable as part of course content or a topic before a quiz or assessment later, if available. 

    ![](assets/knowledge-check-topic.png){width="650"}


    You can configure correct answers and other required fields through the **Content properties** panel. For more details, view [Question types](./quiz-insert-questions.md). You can add various question types using the knowledge check options as shown below.

    Additionally, you can enable the **Require knowledge check to proceed** option to ensure learners attempt a designated knowledge check before advancing to subsequent course content. This capability helps reinforce key learning objectives by preventing learners from skipping critical assessment checkpoints. The feature is supported when **Learners must progress through content in a sequential order** setting is enabled while configuring the SCORM preset output, ensuring the course progression follows the intended learning path.

    ![](assets/knowledge-check-content-properties.png){width="650"}  

- **Input field:** Adds a text input field along with a button to your content. You can use this combination to capture user input and trigger specific actions. A play button is added to the content as shown below. 

    ![](assets/button-learning-content.png){width="650"}

- **More options:** You have additional options to enhance your learning content, including inserting a horizontal line, line break, text box, positioned text box, and embedded HTML. 

    ![](assets/more-options-learning-content.png){width="650"}
