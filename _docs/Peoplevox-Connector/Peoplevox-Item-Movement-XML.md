---
slug: peoplevox-item-movement-xml
title: Peoplevox Item Movement XML
---

Zynk will export the data from the "Item movement history" report in XML format.  All columns documented below will appear in the output file. 

## Tasks

 * [Export Item Movements from Peoplevox](export-item-movements-from-peoplevox)

## Fields
### Item Code  

| Type | Example | XML |
| --- | --- | --- |
| string | TEST01 | `<Item_code>TEST01</Item_code>` |

### Item Name  

| Type | Example | XML |
| --- | --- | --- |
| string | This is a test item. | `<Item_name>This is a test item.</Item_name>` |

### Item Barcode  

| Type | Example | XML |
| --- | --- | --- |
| string | 5016447208891 | `<Item_barcode>5016447208891</Item_barcode>` |

### Date Timestamp  

| Type | Example | XML |
| --- | --- | --- |
| string | '05/07/2017 10:05' | `<Date_timestamp>'05/07/2017 10:05'</Date_timestamp>` |

### User  

| Type | Example | XML |
| --- | --- | --- |
| string | Joe Harrison | `<User>Joe Harrison</User>` |

### From  

| Type | Example | XML |
| --- | --- | --- |
| string | XYZ | `<From>XYZ</From>` |

### To  

| Type | Example | XML |
| --- | --- | --- |
| string | ABC | `<To>ABC</To>` |

### Quantity  

| Type | Example | XML |
| --- | --- | --- |
| string | 5 | `<Quantity>5</Quantity>` |

### Comments  

| Type | Example | XML |
| --- | --- | --- |
| string | Despatched | `<Comments>Despatched</Comments>` |

### Sales Order Number  

| Type | Example | XML |
| --- | --- | --- |
| string | 1234 | `<Sales_order_number>1234</Sales_order_number>` |

### From Container  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<From_Container />` |

### To Container  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<To_Container />` |

### History Id  

| Type | Example | XML |
| --- | --- | --- |
| string | 160738 | `<History_Id>160738</History_Id>` |

### Site Reference  

| Type | Example | XML |
| --- | --- | --- |
| string | PrimarySite | `<Site_reference>PrimarySite</Site_reference>` |

### Buy Price  

| Type | Example | XML |
| --- | --- | --- |
| string | 0.35 | `<Buy_Price>0.35</Buy_Price>` |

### Manufacturer Item No  

| Type | Example | XML |
| --- | --- | --- |
| string | H03M020 | `<Manufacturer_item_no>H03M020</Manufacturer_item_no>` |

### Item Group Name  

| Type | Example | XML |
| --- | --- | --- |
| string | Item group | `<Item_group_name>Item group</Item_group_name>` |

### Attribute 1  

| Type | Example | XML |
| --- | --- | --- |
| string | Whitefurze | `<Attribute_1>Whitefurze</Attribute_1>` |

### Attribute 2  

| Type | Example | XML |
| --- | --- | --- |
| string | n/a | `<Attribute_2>n/a</Attribute_2>` |

### Attribute 3  

| Type | Example | XML |
| --- | --- | --- |
| string | Clear | `<Attribute_3>Clear</Attribute_3>` |

### Attribute 4  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute_4 />` |

### Attribute 5  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute_5 />` |

### Attribute 6  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute_6 />` |

### Attribute 7  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute_7 />` |

### Attribute 8  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute_8 />` |

### Attribute 9  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute_9 />` |

### Attribute 10  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute_10 />` |

### Attribute 11  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute_11 />` |

### Attribute 12  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute_12 />` |

### Attribute 13  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute_13 />` |

### Attribute 14  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute_14 />` |

### Attribute 15  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute_15 />` |

### Register Reason  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Register_Reason />` |

## Example XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<ItemMovementHistory 
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
  xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <ItemMovement>
    <Item_code>TEST01</Item_code>
    <Item_name>This is a test item.</Item_name>
    <Item_barcode>5016447208891</Item_barcode>
    <Date_timestamp>'05/07/2017 10:05'</Date_timestamp>
    <User>Joe Harrison</User>
    <From>XYZ</From>
    <To>ABC</To>
    <Quantity>5</Quantity>
    <Comments>Despatched</Comments>
    <Sales_order_number>1234</Sales_order_number>
    <From_Container />
    <To_Container />
    <History_Id>160738</History_Id>
    <Site_reference>PrimarySite</Site_reference>
    <Buy_Price>0.35</Buy_Price>
    <Manufacturer_item_no>H03M020</Manufacturer_item_no>
    <Item_group_name>Item group</Item_group_name>
    <Attribute_1>Whitefurze</Attribute_1>
    <Attribute_2>n/a</Attribute_2>
    <Attribute_3>Clear</Attribute_3>
    <Attribute_4 />
    <Attribute_5 />
    <Attribute_6 />
    <Attribute_7 />
    <Attribute_8 />
    <Attribute_9 />
    <Attribute_10 />
    <Attribute_11 />
    <Attribute_12 />
    <Attribute_13 />
    <Attribute_14 />
    <Attribute_15 />
    <Register_Reason />
  </ItemMovement>
</ItemMovementHistory>
```
