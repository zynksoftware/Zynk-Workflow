---
slug: message-box
redirect_from: "/article/332-message-box"
title: Message Box
---
The Message Box task will display a Message Box on the screen with the value contained within the Input - be that a Text value, a Variable or a File. This is useful for debugging Workflows. The buttons displayed on the message box can be changed, and a series of sub-tasks can be added to this task and ran depending on which button was clicked.

## Settings
### Equal To
_Required_  
Set to true to run the sub-tasks if the user clicks OK/Yes, or false to run the sub-tasks when the user clicks Cancel/No.

### Caption
_Required_  
The text to display at the top of the message box.

### Default Answer
_Required_  
The answer that should be returned if Zynk is running in the background and cannot display the message box on screen.

### Input
_Required_  
The message to display in the message box.

### Message Box Buttons
_Required_  
The buttons to display on the message box. The following options are available:	
 * OK - Only an OK button will be shown on the message box.
 * OKCancel - OK and Cancel buttons will be shown on the message box.
 * YesNo - Yes and No buttons will be shown on the message box.

### Zynk Settings
See [Common Task Settings](common-task-settings)