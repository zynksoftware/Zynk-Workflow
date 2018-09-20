---
slug: exporting-stock-records-from-sage-50-uk
redirect_from: "/article/405-exporting-stock-records-from-sage-50-uk"
title: Exporting Stock Records from Sage 50 UK
---
This task will export product information from Sage 50 in Zynk XML format.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Attachment Search Pattern
_Required_  
File search pattern for attachment export e.g. *.PDF

### Export Attachments
_Required_  
Set to True if you want the attachments exported from Customers note: this will result in very large XML output files.

### Export Published Products
_Required_  
Set this value to True if you want to only export products marked as Publish. If set to False it will ignore the published flag and export all records.

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
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <Products>
        <Product>
            <UniqueId>FAX001</UniqueId>
            <Sku>FAX001</Sku>
            <Barcode />
            <Name>FX010 Plain Paper Fax</Name>
            <Description>FX010 Plain Paper Fax</Description>
            <LongDescription />
            <ImageUrl>fax001.jpg</ImageUrl>
            <ThumbnailUrl>fax001.jpg</ThumbnailUrl>
            <Custom1>Business Machines</Custom1>
            <Custom2>Faxes</Custom2>
            <Custom3 />
            <SalePrice>180</SalePrice>
            <UnitWeight>0</UnitWeight>
            <QtyInStock>0</QtyInStock>
            <QtyOnOrder>0</QtyOnOrder>
            <ReorderQty>1</ReorderQty>
            <ReorderLvl>0</ReorderLvl>
            <TaxCode>1</TaxCode>
            <GroupCode>9</GroupCode>
            <Department>1</Department>
            <UnitOfSale>Each</UnitOfSale>
            <NominalCode>4000</NominalCode>
            <Publish>true</Publish>
            <ProductLevel>0</ProductLevel>
            <SpecialOffer>false</SpecialOffer>
            <QtyAllocated>0</QtyAllocated>
            <ImageName>fax001.jpg</ImageName>
            <LastCostPrice>150</LastCostPrice>
            <QtyLastOrder>0</QtyLastOrder>
            <AverageCostPrice>150</AverageCostPrice>
            <StandardCostPrice xsi:nil="true" />
            <RRPPrice xsi:nil="true" />
            <Attachments />
            <DateModified xsi:nil="true" />
            <InactiveDate xsi:nil="true" />
            <Dimensions />
            <ProductBoms />
            <RelatedProducts />
            <AlternativeProducts />
            <SupplierAccountRef>WAL001</SupplierAccountRef>
            <SupplierDepartment>1</SupplierDepartment>
            <ProductQtyBreaks />
            <CommodityCode />
            <IntrastatCommodityCode />
            <PurchaseNominalCode>5000</PurchaseNominalCode>
            <Memo />
            <SupplierPartNo>000006876</SupplierPartNo>
            <Location>Supplied Direct</Location>
            <Locations />
            <AllowSalesOrder xsi:nil="true" />
            <Attributes />
            <UnitsOfMeasure />
            <UseDescriptionOnDocs>false</UseDescriptionOnDocs>
            <ItemType>NonStock</ItemType>
            <FulfilmentMethod xsi:nil="true" />
            <ProductSuppliers />
            <CustomFields />
            <AnalysisCodes />
            <SearchCategories />
        </Product>
    </Products>
</Company>
```