---
slug: csv-repeater
redirect_from: "/article/194-csv-repeater"
title: CSV Repeater
---
This task will loop or iterate through all records contained within the specified CSV Input, running the sub-tasks contained within this task for each record that is processed. 
To add sub-tasks, drag and drop tasks from the task library onto this task. The sub-tasks are displayed as child nodes of the CSV Repeater task.

## Settings

### Column Name Prefix
_Required (If Headers not specified)_  
The prefix that will be used with the Column Index for auto generated Column names (only applicable if Headers are not specified). Column names are used when generating the Context Variables. Defaulted to F.

### Delimiter
_Optional_  
The column delimiter used in the Input. This is often a quotation mark. Please see the [CSV](csv) article if you are unsure what value to use. Defaulted to double quotes e.g. "

### Encoding Type	
_Required_  
The encoding to use when parsing the Input. 
Defaulted to UTF8.

### Include Headers
_Required_  
Set this to true to interpret the first row of the Input as column names. Column names are used when generating the Context Variables.  Defaulted to true.

### Input
_Required_  
The absolute or relative file path on the local computer or network to the CSV file or the actual CSV data you would like to repeat/loop over. See the Zynk Objects article if you require more information on how the Zynk Object file value works. Defaulted to Output from previous task.

### Separator	
_Required_  
The column separator used in the Input, for a CSV file this will be a comma, for tab delimited use \t.  Please see the [CSV](csv) article if you are unsure what value to use.
Defaulted to `,`

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Context Variables
For every record in the Input CSV, the columns are available to each sub-task as a current variable. If the Include Headers setting is set to true, the variable names will correspond to the values in the first row of the Input. Otherwise, the variables will be named based on the Column Name Prefix setting and the column's index e.g. F1, F2, F3 etc.

The sub-tasks can access the values of the variables using razor, so they can be used in templates, or within task settings that support [Zynk Objects](zynk-objects) using the 'Use Razor Engine' option. For example `@(Context.Current["F1"])` would be used to access the first value in a row when Include Headers is set to false.  
  
See [Accessing Variables in Tasks](accessing-variables-in-tasks) for more information on using context variables.

## Examples
Sample input file, which includes a header row:

```csv
AccountReference,CompanyName,Balance
A1D001,A1 Design Services,0
BBS001,Bobs Building Supplies,4309.77
```

Given this input file, and with the Include Headers setting set to true, the sub-tasks would be ran twice (as there are two rows in the file, excluding the header), and the following variables would be available to them:  

| CSV Row Number | Variable Name | Value | Razor Code to Access the Value |
| --- | --- | --- | --- |
| 1 | AccountReference | A1D001 | @(Context.Current["AccountReference"]) |  
| 1 | CompanyName | A1 Design Services | @(Context.Current["CompanyName"]) |  
| 1 | Balance | 0 | 	@(Context.Current["Balance"]) |  
| 2 | AccountReference | BBS001 | @(Context.Current["AccountReference"]) |  
| 2 | CompanyName | Bobs Building Supplies | @(Context.Current["CompanyName"]) |  
| 2 | Balance | 4309.77 | @(Context.Current["Balance"]) |  

Sample input file, which does not include a header row:

```csv
ZYNK0001,Zynk Software Ltd,0
JIMSWIM,Jims Swim School,2000.00
```

Given this input file, with the Include Headers setting set to false and the Column Name Prefix set to 'F', the sub-tasks would be ran twice (as there are two rows in the file), and the following variables would be available to them:

| CSV Row Number | Variable Name | Value | Razor Code to Access the Value |
| --- | --- | --- | --- |
| 	1 | 	F1 | 	ZYNK0001 | 	@(Context.Current["F1"]) |
| 	1 | 	F2 | 	Zynk Software Ltd | 	@(Context.Current["F2"]) |
| 	1 | 	F3 | 	0 | 	@(Context.Current["F3"]) |
| 	2 | 	F1 | 	JIMSWIM | 	@(Context.Current["F1"]) |
| 	2 | 	F2 | 	Jims Swim School | 	@(Context.Current["F2"]) |
| 	2 | 	F3 | 	2000.00 | 	@(Context.Current["F3"]) |