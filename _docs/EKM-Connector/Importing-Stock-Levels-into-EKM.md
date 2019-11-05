---
slug: importing-stock-levels-into-ekm
title: Importing Stock into EKM
---
This task will update the stock level of products in EKM.

## Settings
### Connection
_Required_  
The EKM connection to use. See the [Connecting to EKM](connecting-to-ekm) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of the XML file to save any records which fail to import into EKM. Defaults to 'ekm_import_stock_levels_fail.xml'.

### Input File
_Required_  
The name of the XML file containing the records to import into EKM. Defaults to 'ekm_import_stock_levels.xml'.

### Success File
_Required_  
The name of the XML file to save any records which successfully imported into EKM. Defaults to 'ekm_import_stock_levels_success.xml'.

### Prevent Reprocessing
_Required_  
When set to true this will prevent the task from processing a record with the same `<ExternalId>` value as a previously imported record.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Samples
Sample input file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<ProductStocks>
  <ProductStock>
    <Product>
      <!-- At least one of the following elements must be provided to identify which product to update -->
      <Id>1</Id>
      <ProductCode>PEN001</ProductCode>
    </Product>
    <Stock>50</Stock>
    <TotalProductStock>50</TotalProductStock>
  </ProductStock>
</ProductStocks>
```