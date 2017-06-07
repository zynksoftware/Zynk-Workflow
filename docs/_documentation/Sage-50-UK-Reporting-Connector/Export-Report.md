---
slug: exporting-reports-from-sage-50-uk
redirect_from: "/article/698-export-report"
title: Export Report
---
This task will generate a report using a layout file in Sage 50. The report can be generated in PDF, HTML and other formats supported by the Report Designer.

## Settings
### Criteria
_Optional_  
This should contain a list of variables with the criteria values to use when running the report. If the report you're running allows you to specify criteria, you can enter each value as a separate variable. 

For example, if the report allows you to specify a particular sales order, you can enter this by creating a variable with the name 'ORDER_NUMBER', and setting the value to your chosen sales order number. Note that the variable name must be the ODBC field name. 

This can be viewed from the Sage 50 Report Designer, under Variables > CRITERIA.If the criteria allows multiple values to be provided, these can be  entered by selecting the 'List' data type for the variable value.

### Output File
_Required_  
The file to save the generated report to e.g. monthly_profit_and_loss.pdf

### Output Type
_Required_  
Choose an output format for the report from the list:	
 * xml
 * pdf
 * html
 * xls
 * xlsx
 * txt
 * csv

### Report File
_Required_  
The actual Sage .report/.layout file to use to generate the report or invoices (e.g. C:\ProgramData\Sage\Accounts\2013\Company.000\Layouts\INVPRCA4.layout)

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
There are currently no examples available for this task.
