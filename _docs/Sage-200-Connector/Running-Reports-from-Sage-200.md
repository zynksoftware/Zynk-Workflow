---
slug: running-reports-from-sage-200
redirect_from: "/article/965-running-reports-from-sage-200"
title: Running Reports from Sage 200
---
The Export Report task will generate a report using a report file from Sage 200. The report can be generated in PDF, HTML and many other formats.

Please note that this task is only available in the connectors for Sage 200 v9 (2013) and above.

## Export Report
### Criteria
_Optional_  
A list of variables containing the criteria values to use when running the report. If the report you're running allows you to specify criteria, you can enter each value as a separate variable.  The variable name must match the criteria name, as shown in the Sage Report Designer, under Variables > CRITERIA. If the criteria allows multiple values to be provided, these can be entered by selecting the 'List' data type for the variable value.

### Output File
_Required_  
The file to save the generated report to (e.g report.pdf).

### Output Type
_Required_  
Choose an output format for the report from the list:	

 * XML
 * PDF
 * HTML
 * XLS
 * XSLX
 * TXT
 * CSV

### Report File
_Required_  
The Sage .report file to use to generate the invoices e.g. `C:\Sage\reporting\default\reports\sales\Sales Ledger List of Accounts.report`

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
There are currently no examples available for this task.