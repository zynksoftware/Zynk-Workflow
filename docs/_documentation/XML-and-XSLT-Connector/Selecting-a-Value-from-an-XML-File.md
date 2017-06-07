---
slug: selecting-a-value-from-an-xml-file
redirect_from: "/article/903-selecting-a-value-from-an-xml-file"
title: Selecting a Value from an XML File
---
This task will select a value from an XML file and store it a workflow variable.

## Settings
### Variable Name
_Optional_  
The name of the workflow variable to store the selected XML value in. If no variable is specified, the selected value will be made available to the next task in the workflow, via the 'Output from the previous task' option on any of the task's settings which accept a [Zynk Object](zynk-objects). 

### XML Input
_Required_  
The file to select the value from.

### XPath
_Required_  
Enter the XPath for the node(s) to get the value from.

### XPath Search Type 
_Required_  
Select the function to use against the node(s) returned by the XPath. The available options are: 

 * First - Returns the value of the first node in the XML file that matches the XPath.
 * Last - Returns the value of the last node in the XML file that matches the XPath.
 * Count - Returns a count of the nodes in the XML file that match the XPath.
 * Sum - Returns the sum of the values of the nodes in the XML file that match the XPath.

### Zynk Settings
See [Common Task Settings](common-task-settings)