---
slug: converting-excel-to-csv
redirect_from: "/article/229-converting-excel-to-csv"
title: Converting Excel to CSV
---
This task will convert an Excel spreadsheet into a CSV file and should only be used for flat data rather than hierarchical data.

## Settings
### End Line
_Required_  
Can be used to specify the last line to read from the Excel file, use -1 for the entire worksheet.  This will be defaulted to -1.

### Include Headers
_Required_  
Set to true if the converted CSV file should contain headers from the Excel file.  Set to false to omit headers.  This will be defaulted to true.

### Input File
_Required_  
An absolute or relative file path on the local computer or network to the Excel file to convert.  See [Zynk Objects](zynk-objects) if you require more information on how the Zynk Object file value works.  This will be defaulted to the 'Output from the previous task'

### Start Line
_Required_  
Can be used to specify the first line to read from the Excel file, use 0 to start from the beginning of the worksheet.  This will be defaulted to 0.

### Worksheet Name
_Required_  
The name of the worksheet in the Excel file that needs to be converted.

### Output File
_Required_  
An absolute or relative file path on the local computer or network to save the converted CSV file to.  See [Zynk Objects](zynk-objects) article if you require more information on how the Zynk Object file value works.  This will be defaulted to `excel_to_csv.csv` in the current working directory.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file, when Include Headers is set to true:

```csv
"SKU","Sage_Category","Short_Name","Full_Name","Nominal_Code", 
"20000","Connect ","Sage 50 Connector ","Connect - Sage 50 Connector ","4200", 
"20001","Connect ","Sage 200 Connector ","Connect - Sage 200 Connector ","4200"
```

Sample output file, when Include Headers is set to false:

```csv
"20000","Connect ","Sage 50 Connector ","Connect - Sage 50 Connector ","4200", 
"20001","Connect ","Sage 200 Connector ","Connect - Sage 200 Connector ","4200"
```