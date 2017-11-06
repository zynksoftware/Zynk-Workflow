---
slug: merging-xml-files
redirect_from: "/article/356-merging-xml-files"
title: Merging XML Files
---
The XML Merge task can be used to combine multiple XML files together into a single file for batch processing.

A common usage scenario is in FTP based integrations where orders are written to individual files. These could first be downloaded using the [FTP Repeater](ftp-repeater) and [FTP Download](downloading-files-with-ftp) tasks, and then using XML Merge you can create a single file containing all the orders for use within your workflow.

## Settings
### Input Files
_Required_
The list of XML files to be merged together. The list can be entered manually using the 'Use a list' option. It can also be generated dynamically by adding a [List Files](list-files) task to the workflow just before this task, and selecting the 'Use the output from the previous task' option.

### Output File
_Required_
The XML file to output the result to.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Two sample input files are shown below, each including a single stock transaction. These will be merged into a single output file containing two stock transactions:

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

Sample output file, showing the two stock transactions merged into a single file:

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
