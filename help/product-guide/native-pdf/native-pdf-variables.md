---
title: Native PDF | Use variable sets in the PDF output
description: Use variables in the PDF output and output templates
---
# Variable sets in the PDF output

A variable is a name-value pair of data that serves as a reusable piece of information. This makes your content portable and easy to update. When you modify a variable or its value, every occurrence of that variable or value is updated across the project.

Adobe Experience Manager Guides supports variable sets, which lets you assign your variables alternate values. For example, a company can sell two products, A and B. It has different specifications for each of them. These specifications could include product ID, icon, and release date. There can be other differences in branding.

Using variable sets, you define a different set of values for your variables. When you generate the output, you choose the appropriate variable set and produce the required output.

## Create a new variable

A variable is a text phrase to which you assign a value. Follow these steps to create a variable for a variable set in your current DITA map:

 ![Create a new variable](assets/add-variable.png){width="800" align="left"}

 *Create varaibles for a variable set.*


1. In the Web Editor, go to the **Output** tab.
1. Select **Variables** <img alt= "variable icon" src="./assets/variables-icon.svg" width="25"> in the left panel.
1. Select Edit    to open the  **Variables** editor. 
1. Select a variable set from the **Variable sets** dropdown.
1. The variables in the selected variable set are listed alphabetically. The values are displayed according to the chosen variable set. For example, if you select the *Adobe-set1* variable set, “2311” is displayed as a value for the VersionNumber variable.
1. From the **Variable sets** dropdown, select the desired set in which you want to add a variable.

 >[!NOTE] 
 >
 >Every variable is added to all variable sets.

If you select **(Default)** from the dropdown and create variables, those default values are added to all variable sets. When you edit the values for the variables in specific variable sets, it overrides the default values.

1 Enter the variable name in the **Name** column and its value in the **Value** column.
 >[!TIP]
 >
 >You can use any HTML content as a variable value to display the variable value in specific formatting. For example, you can add `<b>` tag to the variable value to display the value **ProductA**  in bold. You can also add images from the repository as values. 
1. Select **Add variable** <img alt= "Add icon" src="./assets/add-icon.svg" width="25"> to add a new variable to the selected variable set. Adding a variable to one set automatically adds it to all sets. You cannot create a variable with the same name as an existing variable. An error is displayed.

>[!NOTE]
>
>If you don’t select **Add variable** <img alt= "Add icon" src="./assets/add-icon.svg" width="25">, the variable is not created and added to the list.

## Configure variable sets

You need to configure variable sets before adding any variables to them. 

 ![configure variable set](assets/configure-variable-set.png){width="550" align="left"}

1. Select **Settings**  <img alt= "Settings icon" src="./assets/settings-icon.svg" width="25"> to open the **Configure variable sets** dialog box. 
 
1. Enter the variable set name in the **Name** column. 
1. Select select **Add variable** <img alt= "Add icon" src="./assets/add-icon.svg" width="25"> to add a new variable set. The variable sets in the selected DITA map are listed alphabetically.
1. You can select **Delete** to remove a variable set.

All variable sets in a DITA map have the same variables but can have different values. 
You can define the default values for the variables in a variable set by selecting **(Default)** from the dropdown and then defining the values.
You can also change the variable values as required and save the variable set.

### Edit a variable

You can edit a variable in two ways:

#### From the **Variables** panel on the left side

1. Select a variable in the **Variables** panel. 
1. Hover over the variable to view the **Options** menu for it and then select the **Edit** option.
1. In the **Edit Variable** dialog box, you can edit the default value of the selected variable.
1. Click **Done**.

#### From the Variables Editor 

1. Select **Variables** <img alt= "variable icon" src="./assets/variables-icon.svg" width="25"> in the left panel.
1. Select **Edit** <img alt= "Edit pencil icon" src="./assets/edit_pencil_icon.svg" width="25">  to open the **Variables** editor.
1. Select a variable set from the **Variable sets** dropdown.
1. In the **Variables** editor, you can edit the value of the selected variable.

When you edit the values for the variables in specific variable sets, it overrides the default values and changes the values of the selected variable set.

You need to save any changes you make from the Variables editor to view them in the Variables panel on the left side. 

### Reset the value of a variable

If you have edited the value, you can also reset a variable to the default value. 
Reset <img alt= "reset icon" src="./assets/application-variable-revert.svg" width="25"> appears for a variable with a changed value.

 >[!NOTE]
 >
 > If you edit any variable value, Adobe Experience Manager Guides simultaneously updates all the references wherever applicable. 


### Delete a variable

You can delete a variable in two ways:

#### From the **Variables** panel on the left side

1. Select a variable in the **Variables** panel. 
1. Hover over the variable to view the **Options** menu for it and then select the **Delete** option.

#### From the Variables Editor 

1. Select a variable set from the dropdown in the **Variables** editor. 
1. Hover over the variable in the list to view the **Options** menu for it and then select **Delete** option.

The variable is deleted from all the variable sets.

### Search and preview a variable

You can search and preview the value of a variable. Enter a string in the search box of the **Variables** panel. It searches both based on the variable name and its value. 
You can preview a variable in two ways:

#### From the **Variables** panel on the left side


1. Select a variable in the **Variables** panel. 
1. Hover over the variable to view the **Options** menu for it and then select the **Preview** option.

  The preview of the variable  displays the default value. For example, if you have defined the default value of the ProductName variable as “Adobe Experience Manager Guides”, it displays this value in the preview.

 ![variable preview from the variables panel](assets/variables-panel-preview.png){width="550" align="left"}

 *Preview the default value for a variable.*
 
#### From the Variables Editor 

1. Select a variable set from the dropdown in the **Variables** editor. 
1. Hover over the variable in the list to view the **Options** menu for it and then select **Preview**.
The preview of the variable  displays the value you have defined in the selected variable set.
 
For example, for the variable set *Adobe-Set1*, you have defined the value of the ProductName variable as “ProductA”, then it displays this value in the preview.

 ![variable preview from the variables editor](assets/variables-editor-preview.png){width="550" align="left"}

*Preview the value that you have defined in the selected variable set.*

### Duplicate a variable

You can duplicate a variable and modify the value according to your requirements. 

1. Select a variable set from the dropdown in the **Variables** editor. 
1. Hover over the variable in the list to view the **Options** menu for it and then select  **Duplicate**.

The default name of the variable is `<selected variable name>` (like “sample”). You can change the name according to your requirements.


## Use variables in the Native PDF templates

You can add variables while you generate the output of your product documents to make them portable and easy to update. You can insert these variables within the page layout that appears across the different pages in your documents. For example, you can add the variable ProductName  that appears in the page layout’s header area (or any other part like the footer or body).



To insert a variable like your ProductName in the header area, perform the following steps:
1. Open the required page layout for editing.

    >[!NOTE]
    >
    > View [Customize a page layout](../native-pdf/components-pdf-template.md#customize-a-page-layout-customize-page-layout) section for opening a page layout for customization or editing.
1. Select the header to make it active to insert a variable.

### Insert a variable

   You can insert the variable in two ways:

#### From the **Variables** panel on the left side

   Drag a variable from the **Variables** panel and drop it on the header area.


#### From the toolbar

1. Select **Insert Variable/Fields** <img alt= "variable icon" src="./assets/variables-icon.svg" width="25">.   
1. In the **Variable** dialog box, select the name of the variable to insert it in the header area.
1. You can also enter the search string in the text box. The variable names containing the given string are filtered and displayed in the list. The selected variable is inserted in the header area. You can view the default value of the variable.
1. To replace a variable, double-click the variable value and select another variable from the **Variable** dialog box. The variable is replaced. 


## Generate PDF output with a variable set

You can generate the PDF output with the values of different variable sets. 
Before generating the layout, choose a variable set from an output preset's **Variable set** drop-down list.
 
 ![variable set dropdown](assets/output-preset-variable-dropdown.png){width="550" align="left"}

*Select a variable set from the dropdown in the output preset that you want to use to generate the PDF output.*

Depending on your chosen variable set, you'll get an output corresponding to the variable values defined in the variable set. For example, if you select the variable set *Adobe-set1*, your output displays the variables' values as defined in this set.   
 
  ![PDF output with variables](assets/variable-pdf-output.png){width="550" align="left" border="2px"}

*Generate the PDF output using variables in the page layout.*

You can also quickly update the values for any variable set whenever required and regenerate the output. For example, if you need to update the details for a version, you can update the value of the version in the VersionNumber variable and regenerate the output.


