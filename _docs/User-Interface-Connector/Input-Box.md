---
slug: input-box
redirect_from: "/article/330-input-box"
title: Input Box
---
The Input Box task will display a dialog box that allows you to accept user input. The return value of the Input Box can be passed to the next task in the workflow, by selecting the 'Use the output from the previous task' option on one of its settings, or can be written to a workflow variable.

## Settings
### Input Type
_Required_  
Select the type of value the user should provide. The available options are as follows:	  

 * Integer - A whole number.
 * Double - A double precision decimal number.
 * FloatingPoint - A decimal number.
 * Character - A single character.
 * String - A piece of text.
 * DateTime - A date and time.
 * ZynkObject - Can be a file, folder, list, variable or script.

### Variable
_Optional_  
Enter the name of the workflow variable to save the user input to.

### Window Title
_Optional_  
Used to customise the title displayed in the dialog box shown to the user.

### Zynk Settings
See [Common Task Settings](common-task-settings)