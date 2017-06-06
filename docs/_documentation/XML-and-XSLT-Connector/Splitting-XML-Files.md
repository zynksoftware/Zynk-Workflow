---
slug: splitting-xml-files
redirect_from: "/article/358-splitting-xml-files"
title: Splitting XML Files
---
The XML Split task will take a large XML file and split it into smaller XML files using a specific XPath Query and specifying the number of records to output, whilst maintaining the same XML document structure. This is generally used when the external system you are integrating with is unable to accept large sets of data.

The collection of output files produced by this task can be processed using the [File Repeater](file-repeater) task.

## Settings
### Input File
_Required_  
The XML file to be processed.


### Output Folder
_Required_  
The XML file to be processed.
The output folder for the split XML files. The output files are named using the format: `inputfile\_1.xml`, `inputfile\_2.xml`, where `inputfile` is the name of the input file.

### Record Limit
_Required_  
The maximum number of records each XML file should contain. Defaults to `1`. Only integer values greater than or equal to 1 will be accepted.

### XPath Query
_Required_  
The XPath query that specifies each row of data that needs to be split e.g. `Company/Products/Product`

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
A sample input file is shown below, containing two stock transactions to be split into separate files. To achieve this, the XPath Query setting should be set to `Company/StockTransactions/StockTransaction`, and the Record Limit should be set to `1`.

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
        <StockTransaction>
            <UniqueId>2</UniqueId>
            <StockTransactionType>AdjustmentIn</StockTransactionType>
            <StockCode>BOARD002</StockCode>
            <StockTransactionDate>2006-12-31T00:00:00</StockTransactionDate>
            <Reference>STK TAKE</Reference>
            <Details>Whiteboard - Drywipe (1000 x 1500)</Details>
            <Qty>2</Qty>
            <CostPrice>17</CostPrice>
            <SalesPrice>0</SalesPrice>
            <StockTransactionNumber>2</StockTransactionNumber>
        </StockTransaction>
    </StockTransactions>
</Company>
```

Two output files will be created, as shown below, each including a single stock transaction:

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

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <StockTransactions>
        <StockTransaction>
            <UniqueId>2</UniqueId>
            <StockTransactionType>AdjustmentIn</StockTransactionType>
            <StockCode>BOARD002</StockCode>
            <StockTransactionDate>2006-12-31T00:00:00</StockTransactionDate>
            <Reference>STK TAKE</Reference>
            <Details>Whiteboard - Drywipe (1000 x 1500)</Details>
            <Qty>2</Qty>
            <CostPrice>17</CostPrice>
            <SalesPrice>0</SalesPrice>
            <StockTransactionNumber>2</StockTransactionNumber>
        </StockTransaction>
    </StockTransactions>
</Company>
```