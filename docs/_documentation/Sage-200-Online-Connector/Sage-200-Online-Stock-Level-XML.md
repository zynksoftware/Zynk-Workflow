---
slug: sage-200-online-stock-level-xml
title: Sage 200 Online Stock Level XML
---
All stock within Sage 200 regardless of type (Stock, Service/labour, or Miscellaneous), require a holding location. The location indicates where an item is stored and the stock level settings for each product in the warehouse i.e. the re-order level, the minimum and maximum stock levels. Items with a type of 'Stock' have levels recorded for each warehouse location and the levels are used when allocating, issuing and receiving stock.  Further information can be found on the [Sage 200 Online Warehouse Holdings API Documentation](https://developer.columbus.sage.com/docs#/uk/sage200extra/accounts/v1/warehouse_holdings).

## Tasks
Zynk does not currently support uploading stock levels directly, but can be used within [Sage 200 Online Stock Record XML](sage-200-online-stock-record-xml) as part of the download or upload of stock records.

 * [Exporting Stock Levels From Sage 200 Online](exporting-stock-levels-from-sage-200-online) 
 * [Exporting Stock Records From Sage 200 Online](exporting-stock-records-from-sage-200-online)
 * [Importing Stock Records To Sage 200 Online](importing-stock-records-to-sage-200-online)

## Fields for Download and Upload
### warehouse_id
_Read Only_  
Warehouse record Id, will also return [warehouse](#warehouse) data.

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 1 | `<warehouse_id>1</warehouse_id>` |

### product_id
_Read Only_  
Product record Id, will also return [product](#product) data.

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 27256 | `<product_id>27256</product_id>` |

### reorder_level
_Optional_  
Reorder stock level.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 5dp) | 2.00000 | `<reorder_level>2.00000</reorder_level>` |

### minimum_level
_Optional_  
Minimum stock quantity level.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 5dp) | 1.00000 | `<minimum_level>1.00000</minimum_level>` |

### maximum_level
_Optional_  
Maximum stock quantity level.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 5dp) | 0.00000 | `<maximum_level>0.00000</maximum_level>` |

## Fields for Download Only
### id
_Read Only_  
Warehouse holding record Id.

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 27336 | `<id>27336</id>` |

### confirmed_qty_in_stock
_Read Only_  
Confirmed stock quantity.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 5dp) | 0.00000 | `<confirmed_qty_in_stock>0.00000</confirmed_qty_in_stock>` |

### unconfirmed_qty_in_stock
_Read Only_  
Unconfirmed stock quantity.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 5dp) | 0.00000 | `<unconfirmed_qty_in_stock>0.00000</unconfirmed_qty_in_stock>` |

### quantity_in_stock
_Read Only_  
Total confirmed and unconfirmed stock quantity.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 5dp) | 0.00000 | `<quantity_in_stock>0.00000</quantity_in_stock>` |

### quantity_allocated_stock
_Read Only_  
Allocated stock quantity.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 5dp) | 0.00000 | `<quantity_allocated_stock>0.00000</quantity_allocated_stock>` |

### quantity_allocated_sop
_Read Only_  
Allocated sales order quantity.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 5dp) | 0.00000 | `<quantity_allocated_sop>0.00000</quantity_allocated_sop>` |

### quantity_allocated_bom
_Read Only_  
Allocated bill of materials quantity.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 5dp) | 0.00000 | `<quantity_allocated_bom>0.00000</quantity_allocated_bom>` |

### quantity_allocated
_Read Only_  
Total Allocated stock, sop and bom quantity.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 5dp) | 0.00000 | `<quantity_allocated>0.00000</quantity_allocated>` |

### date_time_updated
_Read Only_  
The date and time this entity was last updated (UTC).

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2017-06-05T09:56:51.967 | `<date_time_updated>2017-06-05T09:56:51.967</date_time_updated>` |

## Expandable Fields
Related information linked to stock levels are also included in the downloaded XML.

### warehouse
_Read Only_  
The warehouse related to the stock level, see [Sage 200 Online Warehouse XML](sage-200-online-warehouse-xml). 

#### Download example showing related information

```xml
<warehouse>
    <id>1</id>
    <name>HOME</name>
    <date_time_updated>2017-05-15T16:04:40.42</date_time_updated>
</warehouse>
```

### product
_Read Only_  
The product related to the stock level, see [Sage 200 Online Stock Record XML](sage-200-online-stock-record-xml). 

#### Download example showing related information

```xml
<product>
    <id>27256</id>
    <date_time_updated>2017-06-05T10:00:53.483</date_time_updated>
    <code>BOARD001</code>
    <name>Whiteboard - Drywipe (900 x 1200)</name>
    <description>Magnetic steel drywipe whiteboard.Complete with marker tray.Compatible with most rail systemsDimensions: 900 x 1200</description>
    <barcode />
    <allow_sales_order>true</allow_sales_order>
    <product_group_id>14910</product_group_id>
    <tax_code_id>2</tax_code_id>
</product>
```

## Example XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<WarehouseHoldings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <WarehouseHolding>
    <id>27336</id>
    <warehouse_id>1</warehouse_id>
    <product_id>27256</product_id>
    <reorder_level>2.00000</reorder_level>
    <minimum_level>1.00000</minimum_level>
    <maximum_level>0.00000</maximum_level>
    <confirmed_qty_in_stock>0.00000</confirmed_qty_in_stock>
    <unconfirmed_qty_in_stock>0.00000</unconfirmed_qty_in_stock>
    <quantity_in_stock>0.00000</quantity_in_stock>
    <quantity_allocated_stock>0.00000</quantity_allocated_stock>
    <quantity_allocated_sop>0.00000</quantity_allocated_sop>
    <quantity_allocated_bom>0.00000</quantity_allocated_bom>
    <quantity_allocated>0.00000</quantity_allocated>
    <warehouse>
      <id>1</id>
      <name>HOME</name>
      <date_time_updated>2017-05-15T16:04:40.42</date_time_updated>
    </warehouse>
    <product>
      <id>27256</id>
      <date_time_updated>2017-06-05T10:00:53.483</date_time_updated>
      <code>BOARD001</code>
      <name>Whiteboard - Drywipe (900 x 1200)</name>
      <description>Magnetic steel drywipe whiteboard.

Complete with marker tray.

Compatible with most rail systems

Dimensions: 900 x 1200</description>
      <barcode />
      <allow_sales_order>true</allow_sales_order>
      <product_group_id>14910</product_group_id>
      <tax_code_id>2</tax_code_id>
    </product>
    <date_time_updated>2017-06-05T09:56:51.967</date_time_updated>
  </WarehouseHolding>
</WarehouseHoldings>
```
