---
slug: converting-csv-to-xml
redirect_from: "/article/195-converting-csv-to-xml"
title: Converting CSV to XML
---


This task will convert the specified CSV Input into XML data and save to the location specified in the Output File setting.


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
The absolute or relative file path on the local computer or network to the CSV file or the actual CSV data you would like to repeat/loop over. See the [Zynk Objects](zynk-objects) article if you require more information on how the Zynk Object file value works. Defaulted to Output from previous task.

### Separator	
_Required_  
The column separator used in the Input, for a CSV file this will be a comma, for tab delimited use \t.  Please see the [CSV](csv) article if you are unsure what value to use.
Defaulted to `,`

### Export As Elements	
_Required_  
Set to true to output the value of each column as an XML element node, or false to output them as XML attributes. 
Defaulted to true. 

### Output
_Required_
The absolute or relative file path on the local computer or network to save the converted XML file to. 
See the [Zynk Objects](zynk-objects) article if you require more information on how the Zynk Object file value works.
Defaulted to `csv_to_xml.xml` in the current working directory. 

### Root
_Required_
The name to use for the root XML element in the generated Output File.  
Defaulted to Root 

### Row
_Required_  
The XML element name to use for each row in the generated Output File. 
Defaulted to Row 

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples


Sample input file, which includes a header row:

```csv
AccountReference,CompanyName,Balance
A1D001,A1 Design Services,0
BBS001,Bobs Building Supplies,4309.77
```

Sample output file, when the File Includes Headers setting is set to true, Root is set to Accounts, and Row is set to Account:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Accounts>
  <Account>
    <AccountReference>A1D001</AccountReference>
    <CompanyName>A1 Design Services</CompanyName>
    <Balance>0</Balance>
  </Account>
  <Account>
    <AccountReference>BBS001</AccountReference>
    <CompanyName>Bobs Building Supplies</CompanyName>
    <Balance>4309.77</Balance>
  </Account>
</Accounts>
```

Sample input file, which does not include a header row:

```csv
ZYNK0001,Zynk Software Ltd,0
JIMSWIM,Jims Swim School,2000.00
```

Sample output file, when the Include Headers setting is set to false, the Column Name Prefix is set to F and Export As Elements is set to false, Root is set to Root, and Row is set to Row:

```xml
<?xml version="1.0" encoding="utf-8"?>
<Root>
  <Row F1="ZYNK0001" F2="Zynk Software Ltd" F3="0" />
  <Row F1="JIMSWIM" F2="Jims Swim School" F3="2000.00" />
</Root>
```