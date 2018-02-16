---
slug: if-xml-contains
redirect_from: "/article/902-if-xml-contains"
title: If XML Contains
---
This task will check if an XML file contains the value specified, and run a series of sub-tasks depending on the result. Sub-tasks can be added by dragging tasks from the Task Library and onto the If XML Contains task in the workflow.

## Settings
### Equal To
_Required_  
Set to true to run the sub-tasks if the file contains the value specified, or set to false to run the sub-tasks if the file does not contain the value specified.

### Match Value
_Optional_  
The value to look for in the XML file. 

### Value Match Type
_Required_  
Select the type of match to perform against the input file. The available options are: 

 * Exists - Checks the node specified by the XPath exists in the XML file. The match value is ignored when this option is selected.
 * NotExists - Checks the node specified by the XPath does not exists in the XML file. The match value is ignored when this option is selected.
 * Equals - Checks whether the value of the node specified by the XPath is equal to the match value.
 * Contains - Checks whether the value of the node specified by the XPath contains the match value.
 * GreaterThan - Checks whether the value of the node specified by the XPath is greater than the match value.
 * GreaterThanOrEqual - Checks whether the value of the node specified by the XPath is greater than or equal to the match value.
 * LessThan - Checks whether the value of the node specified by the XPath is less than the match value.
 * LessThanOrEqual - Checks whether the value of the node specified by the XPath is less than or equal to the match value.

### XML Input
_Required_   
The file to perform the check against.

### XPath
_Required_  
Enter the XPath for the node(s) to match against.

### XPath Search Type 
_Required_  
Select the function to use against the node(s) returned by the XPath. The available options are: 

### Zynk Settings
See [Common Task Settings](common-task-settings)