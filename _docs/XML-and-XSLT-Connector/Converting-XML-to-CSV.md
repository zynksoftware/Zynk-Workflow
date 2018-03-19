---
slug: converting-xml-to-csv
redirect_from: "/article/359-converting-xml-to-csv"
title: Converting XML to CSV
---
The XML to CSV task will convert an XML file to CSV format.

## Settings
### Delimiter
_Optional_  
The character to use as a delimiter in the output file. This should be used if any data from the XML file contains the character used as the separator, and would typically be a quotation mark. Leave blank to not use a delimiter.

### Input File
_Required_  
The XML file to convert to CSV format.

### Mapping Fields
_Optional_  
This can be used to customise how the XML file is converted to CSV format. See [Converting XML Files To CSV](converting-xml-files-to-csv)

### Output File
_Required_  
The file to output the result to.

### Quotation Characters
_Optional_
The delimeter to use for the created CSV file. This is not required, but recommended if your data contains special characters, such as the character chosen for your separator. Defaults to a " around each value.

### Separator
_Required_  
The character to use as a separator. This will usually be a comma.

### XPath
_Required_  
The XPath Query to get each row of data from the input XML file.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
A sample input file is shown below, which is to be converted to CSV format. In this case, the XPath setting should be set to `Company/StockTransactions/StockTransaction`.

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <StockTransactions>
        <StockTransaction>
            <UniqueId>1</UniqueId>
            <StockTransactionType>AdjustmentIn</StockTransactionType>
            <StockCode>BOARD001</StockCode>
            <StockTransactionDate>2006-12-31T00:00:00</StockTransactionDate>
            <Reference>STK TAKE</Reference>
            <Details>Whiteboard - Drywipe (900 x 1200)</Details>
            <Qty>2</Qty>
            <CostPrice>15</CostPrice>
            <SalesPrice>0</SalesPrice>
            <StockTransactionNumber>1</StockTransactionNumber>
        </StockTransaction>
    </StockTransactions>
</Company>
```

The output file will be as follows, when Mapping Fields is set to use the default mapping.

```csv
UniqueId,StockTransactionType,StockCode,StockTransactionDate,Reference,Details,Qty,CostPrice,SalesPrice,StockTransactionNumber
1,AdjustmentIn,BOARD001,2006-12-31T00:00:00,STK TAKE,Whiteboard - Drywipe (900 x 1200),2,15,0,1
```
