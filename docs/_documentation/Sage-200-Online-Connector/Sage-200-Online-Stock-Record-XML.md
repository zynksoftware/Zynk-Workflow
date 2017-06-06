---
slug: sage-200-online-stock-record-xml
title: Sage 200 Online Stock Record XML
---
Products are used to track stock within Sage 200. This is not just for physical items, but also for items that are ordered direct from suppliers, services, and time or labour that can be included on customer invoices. Each stock item has default settings that are used each time the item is bought or sold. Some of these are inherited from the product group and some are set on each item.  Further information can be found on the [Sage 200 Online Products API Documentation](https://developer.columbus.sage.com/docs#/uk/sage200extra/accounts/v1/products).

Note, it is not currently possible to update products via the API, you can only create and download.

## Tasks
 * [Exporting Stock Records from Sage 200 Online](exporting-stock-records-from-sage-200-online)
 * [Importing Stock Records to Sage 200 Online](importing-stock-records-to-sage-200-online)

## Identifiers
### id
_Dependant_  
The `<id>` field is the unique internal database id of the stock record.  This can be obtained from running a download of stock records, or from the response of an upload.

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 27256 | `<id>27256</id>` |

### code
_Dependant_  
The `<code>` field is the stock record code as shown with the Sage 200 Online interface.

| Type | Example | XML |
| --- | --- | --- |
| string(30) | BOARD001 | `<code>BOARD001</code>` |

## Fields for Download and Upload
### name
_Required_  
Product name.

| Type | Example | XML |
| --- | --- | --- |
| string(60) | Whiteboard - Drywipe (900 x 1200) | `<name>Whiteboard - Drywipe (900 x 1200)</name>` |

### product_group_id
_Dependant (see [product_group](#product_group))_  
Product group record Id, can also be set using product group code, see [product_group](#product_group).

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 14910 | `<product_group_id>14910</product_group_id>` |

### description
_Optional_  
Product description.

| Type | Example | XML |
| --- | --- | --- |
| string(1000) | Magnetic steel drywipe whiteboard. | `<description>Magnetic steel drywipe whiteboard.</description>` |

### barcode
_Optional_  
Product barcode.

| Type | Example | XML |
| --- | --- | --- |
| string(60) |  | `<barcode />` |

### allow_sales_order
_Optional_  
Allowed on a sales order.

| Type | Example | XML |
| --- | --- | --- |
| boolean | true | `<allow_sales_order>true</allow_sales_order>` |

#### Available Values
 * true
 * false

### tax_code_id
_Dependant (see [tax_code](#tax_code))_  
Tax code record Id, can also be set using tax code, see [tax_code](#tax_code).

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 2 | `<tax_code_id>2</tax_code_id>` |

### warehouse_holdings
_Required_  
Warehouse holding(s) for the product.  Note Sage 200 Standard Online uses multiple locations so at least one must be provided when creating a new product.  See [Sage 200 Online Stock Level XML](sage-200-online-stock-level-xml) for full details.

## Fields for Download Only
### date_time_updated
_Read Only_  
The date and time this entity was last updated (UTC).

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2017-06-05T10:00:53.483 | `<date_time_updated>2017-06-05T10:00:53.483</date_time_updated>` |

## Expandable Fields
Related information linked to stock records are also included in the downloaded XML, these can also be used to set certain fields on stock level uploads using lookups rather than needing to know the internal id of the related record.

### tax_code
_Dependant (see [tax_code_id](#tax_code_id))_  
The stock records tax code. On a download all the related information of the tax code will be included in the XML, see [Sage 200 Online Tax Code XML](sage-200-online-tax-code-xml). On an upload you can set the code of the tax code to use for the stock record and Zynk will lookup the correct internal id from Sage.

#### Download example showing related information

```xml
<tax_code>
    <id>2</id>
    <date_time_updated>2015-10-30T22:33:16.473</date_time_updated>
    <code>1</code>
    <name>Standard Rate</name>
    <tax_rate>20.00</tax_rate>
</tax_code>
```

#### Upload example only setting the code

```xml
<tax_code>
    <code>1</code>>
</tax_code>
```

### product_group
_Dependant (see [product_group_id](#product_group_id))_  
The stock records product group. On a download all the related information of the product group will be included in the XML, see [Sage 200 Online Product Group XML](sage-200-online-product-group-xml). On an upload you can set the code of the product group to use for the stock record and Zynk will lookup the correct internal id from Sage.

#### Download example showing related information

```xml
<product_group>
    <id>14910</id>
    <date_time_updated>2015-10-30T22:33:22.773</date_time_updated>
    <code>GROUP01</code>
    <description>Default Product Group</description>
    <product_type>EnumStockItemTypeStock</product_type>
    <can_levels_go_negative>true</can_levels_go_negative>
</product_group>
```

#### Upload example only setting the code

```xml
<product_group>
    <code>GROUP01</code>
</product_group>
```