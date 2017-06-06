---
slug: exporting-tax-rates-from-sage-50-uk
redirect_from: "/article/408-exporting-tax-rates-from-sage-50-uk"
title: Exporting Tax Rates from Sage 50 UK
---
This task will export tax rates from Sage 50 in the Zynk XML format.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Export Settings
_Required_  

 * **Date Modified** - Only records modified after this date will be exported. The date will update automatically each time the task runs.
 * **Export Modified, New or All Records** - Used to choose which records should be included in the export. Note that the 'Modified' setting will also export any new records.

### Query Settings
_Optional_  

 * **Columns** - Allows you to specify additional columns to include in the export.  Additional fields will be exported in the CustomFields section in the XML.  Be sure to include the table name for each of the additional columns provided eg. `[STOCK].[QTY_LAST_STOCK_TAKE]`.  If the table that the column you are trying to retrieve is not used by the standard export, you will need to add the table to Joins.
 * **Joins** - Allows data to be exported from other tables in the Sage database. Required when exporting data from tables not included in the standard export.
 * **Where Clauses** - Allows filters to be set to limit the data that is exported.

### Query Timeout
_Optional_  
The maximum amount of time (in seconds) the query should be allowed to run.

### Output File
_Required_  
The name of the file to export to. Data is exported in Zynk XML format

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file:

```xml
<?xml version="1.0"?>
<Company>
    <TaxRates>
        <TaxRate>
            <UniqueId>0</UniqueId>
            <Reference>0</Reference>
            <Description>Zero rated</Description>
            <Rate>0</Rate>
        </TaxRate>
        <TaxRate>
            <UniqueId>1</UniqueId>
            <Reference>1</Reference>
            <Description>Standard rate</Description>
            <Rate>20</Rate>
        </TaxRate>
        <TaxRate>
            <UniqueId>2</UniqueId>
            <Reference>2</Reference>
            <Description>Exempt transactions</Description>
            <Rate>0</Rate>
        </TaxRate>
        <TaxRate>
            <UniqueId>3</UniqueId>
            <Reference>3</Reference>
            <Description />
            <Rate>0</Rate>
        </TaxRate>
        <TaxRate>
            <UniqueId>4</UniqueId>
            <Reference>4</Reference>
            <Description>Sale of goods to VAT registered customers in EC</Description>
            <Rate>0</Rate>
        </TaxRate>
        <TaxRate>
            <UniqueId>5</UniqueId>
            <Reference>5</Reference>
            <Description>Lower Rate</Description>
            <Rate>5</Rate>
        </TaxRate>
        <TaxRate>
            <UniqueId>6</UniqueId>
            <Reference>6</Reference>
            <Description />
            <Rate>0</Rate>
        </TaxRate>
        <TaxRate>
            <UniqueId>7</UniqueId>
            <Reference>7</Reference>
            <Description>Zero rated purchases of goods from suppliers in EC</Description>
            <Rate>0</Rate>
        </TaxRate>
        <TaxRate>
            <UniqueId>8</UniqueId>
            <Reference>8</Reference>
            <Description>Standard rated purchases of goods from suppliers in EC</Description>
            <Rate>0</Rate>
        </TaxRate>
        <TaxRate>
            <UniqueId>9</UniqueId>
            <Reference>9</Reference>
            <Description>Non-Vatable Tax Code</Description>
            <Rate>0</Rate>
        </TaxRate>
    </TaxRates>
</Company>
```