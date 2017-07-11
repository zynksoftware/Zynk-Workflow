---
slug: peoplevox-item-availability-xml
title: Peoplevox Item Availability XML
---

Zynk will export the data from the "Item availability latest reconciliation" report in XML format.  All columns documented below will appear in the output file. 

## Tasks

 * [Export Item Availability from Peoplevox](export-item-availability-from-peoplevox)

## Fields
### Item Code  

| Type | Example | XML |
| --- | --- | --- |
| string | ABBUILTIN/15/0/2 | `<Item_code>ABBUILTIN/15/0/2</Item_code>` |

### Name  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Name />` |

### Barcode  

| Type | Example | XML |
| --- | --- | --- |
| string | 800811232 | `<Barcode>800811232</Barcode>` |

### On Hand  

| Type | Example | XML |
| --- | --- | --- |
| string | 0 | `<On_hand>0</On_hand>` |

### Activity  

| Type | Example | XML |
| --- | --- | --- |
| string | Sales order allocation | `<Activity>Sales order allocation</Activity>` |

### Reason  

| Type | Example | XML |
| --- | --- | --- |
| string | Sales order Allocation | `<Reason>Sales order Allocation</Reason>` |

### User  

| Type | Example | XML |
| --- | --- | --- |
| string | admin | `<User>admin</User>` |

### Date Time  

| Type | Example | XML |
| --- | --- | --- |
| string | '03/07/2017 10:52' | `<Date_time>'03/07/2017 10:52'</Date_time>` |

### Default Economic Order Quantity  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Default_economic_order_quantity />` |

### Default Lead Time  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Default_lead_time />` |

### Default Suppliers Part Number  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Default_suppliers_part_number />` |

### Has Serial Number  

| Type | Example | XML |
| --- | --- | --- |
| string | False | `<Has_serial_number>False</Has_serial_number>` |

### Use Manufacturers Serial Number  

| Type | Example | XML |
| --- | --- | --- |
| string | False | `<Use_manufacturers_serial_number>False</Use_manufacturers_serial_number>` |

### Reorder Point  
 
| Type | Example | XML |
| --- | --- | --- |
| string | 0 | `<Reorder_point>0</Reorder_point>` |

### Shelf Life  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Shelf_life />` |

### Default Number of Items per Container  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Default_number_of_items_per_container />` |

### Default Number of items per Outercase  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Default_number_of_items_per_outercase />` |

### Buy Price  

| Type | Example | XML |
| --- | --- | --- |
| string | 0.00 | `<Buy_price>0.00</Buy_price>` |

### Wholesale Price  

| Type | Example | XML |
| --- | --- | --- |
| string | 0.00 | `<Wholesale_price>0.00</Wholesale_price>` |

### Retail Price  

| Type | Example | XML |
| --- | --- | --- |
| string | 0.00 | `<Retail_price>0.00</Retail_price>` |

### Weight  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Weight />` |

### Height  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Height />` |

### Width  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Width />` |

### Depth  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Depth />` |

### Item Type Group  

| Type | Example | XML |
| --- | --- | --- |
| string | Item group | `<Item_type_group>Item group</Item_type_group>` |

### Tags  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Tags />` |

### Allocated  

| Type | Example | XML |
| --- | --- | --- |
| string | 10 | `<Allocated>10</Allocated>` |

### On Order  

| Type | Example | XML |
| --- | --- | --- |
| string | 0 | `<On_order>0</On_order>` |

### Attribute 1  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute1 />` |

### Attribute 2  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute2 />` |

### Attribute 3  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute3 />` |

### Attribute 4  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `Attribute4 />` |

### Attribute 5  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute5 />` |

### Attribute 6  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute6 />` |

### Attribute 7  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute7 />` |

### Attribute 8  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute8 />` |

### Attribute 9  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute9 />` |

### Attribute 10  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute10 />` |

### Attribute 11  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute11 />` |

### Attribute 12  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute12 />` |

### Attribute 13  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute13 />` |

### Attribute 14  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute14 />` |

### Attribute 15  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Attribute15 />` |

## Example XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<Items 
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
  xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Item>
    <Item_code>ABBUILTIN/15/0/2</Item_code>
    <Name />
    <Barcode>800811232</Barcode>
    <On_hand>0</On_hand>
    <Activity>Sales order allocation</Activity>
    <Reason>Sales order Allocation</Reason>
    <User>admin</User>
    <Date_time>'03/07/2017 10:52'</Date_time>
    <Default_economic_order_quantity />
    <Default_lead_time />
    <Default_suppliers_part_number />
    <Has_serial_number>False</Has_serial_number>
    <Use_manufacturers_serial_number>False</Use_manufacturers_serial_number>
    <Reorder_point>0</Reorder_point>
    <Shelf_life />
    <Default_number_of_items_per_container />
    <Default_number_of_items_per_outercase />
    <Buy_price>0.00</Buy_price>
    <Wholesale_price>0.00</Wholesale_price>
    <Retail_price>0.00</Retail_price>
    <Weight />
    <Height />
    <Width />
    <Depth />
    <Item_type_group>Item group</Item_type_group>
    <Tags />
    <Allocated>10</Allocated>
    <On_order>0</On_order>
    <Attribute1 />
    <Attribute2 />
    <Attribute3 />
    <Attribute4 />
    <Attribute5 />
    <Attribute6 />
    <Attribute7 />
    <Attribute8 />
    <Attribute9 />
    <Attribute10 />
    <Attribute11 />
    <Attribute12 />
    <Attribute13 />
    <Attribute14 />
    <Attribute15 />
  </Item>
</Items>
```
