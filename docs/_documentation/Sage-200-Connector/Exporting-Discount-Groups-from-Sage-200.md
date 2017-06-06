---
slug: exporting-discount-groups-from-sage-200
redirect_from: "/article/426-exporting-discount-groups-from-sage-200"
title: Exporting Discount Groups from Sage 200
---
This task will export all or modified discount groups from Sage 200 in [Sage 200 XML](sage-200-xml).

## Settings
### Sage 200 Connection
_Required_  
The Sage 200 connection to use.  See the [Connecting to Sage 200](connecting-to-sage-200) article if you require more information on how to create/manage connections

### Export All Records
_Required_  
Set to true to export all discount groups from Sage, or false to only export modified discount groups.

### Op Lock
_Required_  
The oplock value to use when exporting modified discount groups.

### Query Timeout
_Required_  
The maximum amount of time (in seconds) the query should be allowed to run.

### Output File
_Required_  
The file to save the exported records to, in Zynk XML format.

### Filter
_Optional_  
Specify criteria to use to filter the exported records.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample output file:

```xml
<?xml version="1.0"?>
<Company>
  <DiscountGroups>
    <DiscountGroup>
      <Id>20627</Id>
      <Reference>Trade</Reference>
      <Description>Trade Discount Group</Description>
      <Discounts>
        <Discount>
          <Type>ProductGroup</Type>
          <Code>DISCGROUP</Code>
          <Description>Group with qty breaks</Description>
          <DiscountType>QtyBreak</DiscountType>
          <Name>QTY BREAKS</Name>
          <ProductGroup>DISCGROUP</ProductGroup>
          <Unit />
          <AdjustmentType>Percentage</AdjustmentType>
          <ProductQtyBreaks>
            <ProductQtyBreak>
              <Quantity>5</Quantity>
              <Value>5</Value>
              <ModifierType>Discount</ModifierType>
            </ProductQtyBreak>
            <ProductQtyBreak>
              <Quantity>20</Quantity>
              <Value>10</Value>
              <ModifierType>Discount</ModifierType>
            </ProductQtyBreak>
            <ProductQtyBreak>
              <Quantity>50</Quantity>
              <Value>15</Value>
              <ModifierType>Discount</ModifierType>
            </ProductQtyBreak>
          </ProductQtyBreaks>
        </Discount>
      </Discounts>
    </DiscountGroup>
  </DiscountGroups>
</Company>
```