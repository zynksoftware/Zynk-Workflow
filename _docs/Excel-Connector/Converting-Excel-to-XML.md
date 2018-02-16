---
slug: converting-excel-to-xml
redirect_from: "/article/562-converting-excel-to-xml"
title: Converting Excel to XML
---
This task will convert an Excel spreadsheet into an XML file. The file generated can then be used as the input to other tasks, for example an [XSLT Transform](xslt-transform) could be used to convert the XML to the Zynk XML format, ready for import into Sage.

## Settings
### Include Headers
_Required_  
Set this to true if the input file contains a header row. This will stop the row being included in the output file and name the XML nodes according to the column headers.  This will be defaulted to true.	  

### Input File
_Required_  
An absolute or relative file path on the local computer or network to the Excel file to convert.  See the [Zynk Objects](zynk-objects) article if you require more information on how the Zynk Object file value works.  This will be defaulted to the 'Output from the previous task'

### Worksheet Name
_Required_  
The name of the worksheet in the Excel file that needs to be converted.

### Output File
_Required_  
An absolute or relative file path on the local computer or network to save the converted XML file to.  See the [Zynk Objects](zynk-objects) article if you require more information on how the Zynk Object file value works.  This will be defaulted to `excel_to_xml.xml` in the current working directory.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Sample Output

```xml
<?xml version="1.0" standalone="yes" ?> 
<DocumentElement>
  <Sheet1>
    <SKU>20000</SKU> 
    <Sage_Category>Connect</Sage_Category> 
    <Short_Name>Sage 50 Connector</Short_Name> 
    <Full_Name>Connect - Sage 50 Connector</Full_Name> 
    <Nominal_Code>4200</Nominal_Code> 
  </Sheet1>
  <Sheet1>
    <SKU>20001</SKU> 
    <Sage_Category>Connect</Sage_Category> 
    <Short_Name>Sage 200 Connector</Short_Name> 
    <Full_Name>Connect - Sage 200 Connector</Full_Name> 
    <Nominal_Code>4200</Nominal_Code> 
  </Sheet1>
</DocumentElement>	
```

## Examples
There are currently no examples available for this task.