---
slug: exporting-items-from-xero
redirect_from: "/article/347-downloading-items-from-xero"
title: Exporting Items from Xero
---


This task will download products from Xero in XML format.


### Connection 
_Required_  
The Xero connection use when running this task.

### Output File
_Required_  
The file to save results from this task. The results are returned as an array of the object as detailed in the example below.

### Filter
_Optional_  
Specify criteria to filter the accounts on e.g. 	`Type == "BANK" AND Name.Contains("Business")`

### Zynk Settings
See [Common Task Settings](common-task-settings)



## Examples


Sample output file showing an item:


```xml
    <?xml version="1.0"?>
    <ArrayOfXeroItem>
      <XeroItem>
        <Id>5b27339e-ecc8-40b6-ace3-0f25bdf5fd63</Id>
        <Code>BOOK</Code>
        <Description>Fish out of Water: Finding Your Brand'</Description>
        <PurchaseDetails>
          <UnitPrice>15.9500</UnitPrice>
          <AccountCode>300</AccountCode>
          <TaxType>INPUT2</TaxType>
        </PurchaseDetails>
        <SalesDetails>
          <UnitPrice>19.9500</UnitPrice>
          <AccountCode>200</AccountCode>
          <TaxType>OUTPUT2</TaxType>
        </SalesDetails>
      </XeroItem>
    </ArrayOfXeroItem>
```