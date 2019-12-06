---
slug: export-inventory-from-peoplevox
title: Export Inventory from Peoplevox
---

This task will export inventory information from Peoplevox in XML format. The output is built up from a number of reports from Peoplevox to give an overall stock position per site. You can control the level of detail in output using the task settings.

## Settings
### Peoplevox Connection
_Required_  
The connection to the Peoplevox instance to use.  See the [Connecting to Peoplevox](connecting-to-peoplevox) if you require more information on how to create/manage connections.

### API Call Delay
_Required_  
The number of seconds to wait between sending requests to the Peoplevox API, used when making multiple paged requests to export data.  Defaults to 1.

### Items Per Page
_Required_  
The number of items to retreive per request made to Peoplevox.  Zynk will make as many requests as required to download all data matching the filters set on the task.  The maxumum this can be is 1000, anything higher will be reset to 1000.  Defaults to `20`.

### Output File
_Required_  
The name or full path to the file the returned data will be saved to.  Defaults to `peoplevox_export_inventory.xml`, which will be created in the working directory of the Workflow.

### Search Clauses
_Optional_  
You can add search clauses to limit the data that is returned from the report, for more information see [Peoplevox Search Clauses](peoplevox-search-clauses).

### Timeout (In Minutes)
_Required_  
Maximum amount of time in minutes that Zynk will wait for a response per call made.  Defaults to `10`.

## Peoplevox Settings
### Export Item Inventory Changes
_Required_  
Optionally export inventory changes for each item type from the past 30 days. Defaults to `false`.

### Export Item Inventory Summary 
_Required_  
Optionally export the inventory summary for each item site location in the output. Defaults to `false`.

### Export Item Inventory Summary All Sites
_Required_  
Optionally include the inventory summary all sites report for each item in the output. Defaults to `false`.

### Export Item Types
_Required_  
Optionally export the item type data associated with each inventory item. Defaults to `false`.

## Zynk Settings
See [Common Task Settings](common-task-settings)

## Example XML
Example output file.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Inventory xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <InventoryItem>
    <ItemCode>101365</ItemCode>
    <ItemName>Mini Clipboard Calculator</ItemName>
    <TotalAllocated>0</TotalAllocated>
    <TotalAvailable>0</TotalAvailable>
    <TotalOnHand>0</TotalOnHand>
    <Sites>
      <InventorySite>
        <Name>PrimarySite</Name>
        <Reference>PrimarySite</Reference>
        <Allocated>0</Allocated>
        <Available>0</Available>
        <OnHand>0</OnHand>
      </InventorySite>
      <InventorySite>
        <Name>SystemSite</Name>
        <Reference>SystemSite</Reference>
        <Allocated>0</Allocated>
        <Available>0</Available>
        <OnHand>0</OnHand>
      </InventorySite>
      <InventorySite>
        <Name>Test Site</Name>
        <Reference>TestSite</Reference>
        <Allocated>0</Allocated>
        <Available>0</Available>
        <OnHand>0</OnHand>
      </InventorySite>
    </Sites>
    <ItemTypes />
  </InventoryItem>
</Inventory>
```
