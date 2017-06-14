---
slug: sage-200-online-sales-order-line-xml
title: Sage 200 Online Sales Order Line XML
---
All sales orders contain 'line items' that define what an order consists of (e.g. items on an order). If the contents of an order are modified by adding/updating/deleting order lines, this will affect the overall value of the order.  Further information can be found on the [Sage 200 Online Sales Order Line API Documentation](https://developer.columbus.sage.com/docs#/uk/sage200extra/accounts/v1/sop_order_lines). 

## Tasks
Zynk does not currently support downloading or uploading sales order lines directly, but can be used within [Sage 200 Online Sales Order XML](sage-200-online-sales-order-xml) as part of the export and import of sales order records.

 * [Exporting Sales Orders From Sage 200 Online](exporting-sales-orders-from-sage-200-online)
 * [Importing Sales Orders To Sage 200 Online](importing-sales-orders-to-sage-200-online)

## Fields for Download and Upload
### product_id
_Dependant (see [product](#product))_  
Product record Id, can also be set using product code, see [product](#product).

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 27256 | `<product_id>27256</product_id>` |

### line_type
_Required_  
The sales order line type.

| Type | Example | XML |
| --- | --- | --- |
| string(20) | EnumLineTypeStandard | `<line_type>EnumLineTypeStandard</line_type>` |

#### Available Values
 * EnumLineTypeStandard
 * EnumLineTypeFreeText
 * EnumLineTypeCharge
 * EnumLineTypeComment

### code
_Dependant_  
The stock item code. In case of an additional charge, this can only be set for lines of type EnumLineTypeCharge and is required if description is not specified.

| Type | Example | XML |
| --- | --- | --- |
| string(30) | CAR001 | `<code>CAR001</code>` |

### description
_Dependant_  
The item description. This could be stock item description, free text, additional charge or comment. Required for lines of type EnumLineTypeFreeText and is required for lines of type EnumLineTypeCharge if code is not specified.

| Type | Example | XML |
| --- | --- | --- |
| string(6000) | Shipping Charges | `<description>Shipping Charges</description>` |

### tax_code_id
_Dependant (see [tax_code](#tax-code))_  
Tax code Id, can also be set using tax code, see [tax_code](#tax-code).

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 2 | `<tax_code_id>2</tax_code_id>` |

### line_quantity
_Optional_  
Item quantity.Note: Decimals cannot be used as quantity values for traceable items that use serial numbers. These will be rounded up/down at the time of posting via the API.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 5dp) | 1 | `<line_quantity>1</line_quantity>` |

### selling_unit_price
_Optional_  
Selling unit price.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 5dp) | 10.0 | `<selling_unit_price>10.0</selling_unit_price>` |

### unit_discount_percent
_Optional_  
Unit discount percent.  Note if [unit_discount_value](#unit_discount_value) is provided as well, this value will be adjusted accordingly.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 10.0 | `<unit_discount_percent>10.0</unit_discount_percent>` |

### unit_discount_value
_Optional_  
Unit discount value.  Note if [unit_discount_percent](#unit_discount_percent) is provided as well, this value will be used and the percentage will be adjusted accordingly.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 5dp | 5.0 | `<unit_discount_value>5.0</unit_discount_value>` |

### cost_price
_Optional_  
Cost price.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 5dp) | 5.0 | `<cost_price>5.0</cost_price>` |

### show_on_customer_docs
_Optional_  
Can only be set for lines of type EnumLineTypeComment.

| Type | Example | XML |
| --- | --- | --- |
| boolean | true | `<show_on_customer_docs>true</show_on_customer_docs>` |

#### Available Values
 * true
 * false

### show_on_picking_list_type
_Optional_  
Whether the line should appear on the picking list.

| Type | Example | XML |
| --- | --- | --- |
| string(20) | ShowButExclude | `<show_on_picking_list_type>ShowButExclude</show_on_picking_list_type>` |

#### Available Values
 * DoNotShow
 * Show
 * ShowButExclude

## Fields for Download Only
### id
_Read Only_  
Sales order line record Id.

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 27767 | `<id>27767</id>` |

### line_number
_Read Only_  
The line number.

| Type | Example | XML |
| --- | --- | --- |
| integer(int16) | 1 | `<line_number>1</line_number>` |

### sop_order_id
_Read Only_  
Sales order record Id.

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 28006 | `<sop_order_id>28006</sop_order_id>` |

### allocated_quantity
_Read Only_  
Allocated quantity.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 5dp) | 0.0 | `<allocated_quantity>0.0</allocated_quantity>` |

### despatch_receipt_quantity
_Read Only_  
Despatch quantity.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 5dp) | 0.0 | `<despatch_receipt_quantity>0.0</despatch_receipt_quantity>` |

### invoice_credit_quantity
_Read Only_  
Invoiced quantity.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 5dp) | 0.0 | `<invoice_credit_quantity>0.0</invoice_credit_quantity>` |

### line_total_value
_Read Only_  
The total value of the line.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 5.0 | `<line_total_value>5.0</line_total_value>` |

### line_tax_value
_Read Only_  
The tax value of the line.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 1.0 | `<line_tax_value>1.0</line_tax_value>` |

### date_time_updated
_Read Only_  
The date and time this entity was last updated (UTC).

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2017-06-05T16:27:25.623 | `<date_time_updated>2017-06-05T16:27:25.623</date_time_updated>` |

## Expandable Fields
Related information linked to sales order lines are also included in the exported XML, these can also be used to set certain fields on sales order imports using lookups rather than needing to know the internal id of the related record.

### Product
_Dependant (see [product_id](#product_id))_  
The sales order lines product code.  On an import you can set the code of the product to use for the sales order line and Zynk will lookup the correct internal id from Sage.

#### Import example only setting the code

```xml
<product>
    <code>BOARD001</code>
</product>
```

### Tax Code
_Dependant (see [tax_code_id](#tax_code_id))_  
The sales order lines tax code.  On an import you can set the code of the tax code to use for the sales order line and Zynk will lookup the correct internal id from Sage.

#### Import example only setting the code

```xml
<tax_code>
    <code>1</code>
</tax_code>
```
