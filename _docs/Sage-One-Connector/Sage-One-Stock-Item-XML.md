---
slug: sage-one-stock-item-xml
title: Sage One Stock Item XML
---
The [Import Stock Items](uploading-stock-items-to-sage-one) task allows you to create new and update existing stock product records in Sage One, using the XML format described below. Any Sage One fields not documented below are not supported with our import.   

A complete example of the XML is shown below. This represents the minimum information required to create a stock product record in Sage One:

```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <stock_items>
    <stock_item>
      <item_code>PENCILS</item_code>
      <description>50 Coloured Pencils</description>
      <sales_ledger_account>
        <nominal_code>4000</nominal_code>
      </sales_ledger_account>
      <purchase_ledger_account>
        <nominal_code>5000</nominal_code>
      </purchase_ledger_account>
    </stock_item>
  </stock_items>
</sage_one_company>
```

## Product Identification
The following fields are use to identify the product to create/update. At least one of these fields should be provided. If more than one is provided, Zynk will look for a match based on each field in turn, in the order they are listed below.

| Sage Field | XML Field | Example | Field Type | Input | Notes |
| --- | --- | --- | --- | --- | --- |
| Item Information > Item Code | item_code | PENCILS | string | Required |  |
| - | id | 0dfbbb5d174611e691e20a5d7cf84c3e | GUID | Optional | Sage's unique product ID. |
| - | external_id | PENCILS | string  | Optional | The ID of the product from the source data. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <stock_items>
    <stock_item>
      <item_code>PENCILS</item_code>
      <id>0dfbbb5d174611e691e20a5d7cf84c3e</id>
      <external_id>PENCILS</external_id>
    </stock_item>
  </stock_items>
</sage_one_company>
```

## Product Details
The following product fields can be set using Zynk.

| Sage Field | XML Field | Example | Field Type | Input | Notes |
| --- | --- | --- | --- | --- | --- |
| Item Information > Item Code | item_code | PENCILS | string | Required |  |
| Item Information > Description | description | 50 Coloured Pencils | string | Required |  |
| Item Information > Inactive | active | true | string | Optional | Set to true to make the product active, or false to make it inactive |
| Sales > Sales Account | sales_ledger_account/nominal_code | 4000 | string | Dependant | At least one of the `sales_ledger_account` elements must be provided |
| Sales > Sales Account | sales_ledger_account/name | Sales Type A | string | Dependant | At least one of the `sales_ledger_account` elements must be provided |
| Sales > Sales Account | sales_ledger_account/display_name | Sales Type A (4000) | string | Dependant | At least one of the `sales_ledger_account` elements must be provided |
| Sales > VAT Rate | sales_tax_rate/id | GB_STANDARD | string | Optional |  |
| Sales > VAT Rate | sales_tax_rate/name | Standard 20.00% | string | Optional |  |
| Purchases > Supplier Item Code | supplier_part_number | PENCIL-50 | string | Optional |  |
| Purchases > Purchase Description | purchase_description | 50 Coloured Pencils | string | Optional |  |
| Purchases > Cost Price | cost_price | 2.50 | double | Optional |  |
| Purchases > Purchase Account | purchase_ledger_account/nominal_code | 5000 | string | Optional |  |
| Purchases > Purchase Account | purchase_ledger_account/name | Cost of sales - goods | string | Optional |  |
| Purchases > Purchase Account | purchase_ledger_account/display_name | Cost of sales - goods (5000) | string | Optional |  |
| Purchases > VAT Rate | purchase_tax_rate/id | GB_STANDARD | string | Optional |  |
| Purchases > VAT Rate | purchase_tax_rate/name | Standard 20.00% | string | Optional |  |
| Purchases > Reorder Level | reorder_level | 10 | double | Optional |  |
| Purchases > Reorder Quantity | reorder_quantity | 20 | double | Optional |  |
| Additional Information > Location | location | Home | string | Optional |  |
| Additional Information > Barcode | barcode | 402184102948314 | string | Optional |  |
| Additional Information > Weight | wieght | 1 | double | Optional |  |
| Additional Information > Weight (Units) | measurement_unit | kg | string | Optional |  |
| Additional Information > Notes | Notes | A pack of 50 coloured pencils | string | Optional |  |

```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <stock_items>
    <stock_item>
      <item_code>PENCILS</item_code>
      <description>50 Coloured Pencils</description>
      <active>true</active>
      <sales_ledger_account>
        <nominal_code>4000</nominal_code>
        <name>Sales Type A</name>
        <display_name>Sales Type A (4000)</display_name>
      </sales_ledger_account>
      <sales_tax_rate>
        <id>GB_STANDARD</id>
        <name>Standard 20.00%</name>
      </sales_tax_rate>
      <supplier_part_number>PENCIL-50</supplier_part_number>
      <purchase_description>50 Coloured Pencils</purchase_description>
      <cost_price>2.50</cost_price>
      <purchase_ledger_account>
        <nominal_code>5000</nominal_code>
        <name>Cost of sales - goods</name>
        <display_name>Cost of sales - goods (5000)</display_name>
      </purchase_ledger_account>
      <purchase_tax_rate>
        <id>GB_STANDARD</id>
        <name>Standard 20.00%</name>
      </purchase_tax_rate>
      <reorder_level>10</reorder_level>
      <reorder_quantity>20</reorder_quantity>
      <location>Home</location>
      <barcode>402184102948314</barcode>
      <weight>1</weight>
      <measurement_unit>kg</measurement_unit>
      <notes>A pack of 50 coloured pencils</notes>
    </stock_item>
  </stock_items>
</sage_one_company>
```

## Sales Prices
The following sales price fields can be set using Zynk. The price names must already exist in Sage, this task will not create any that do not already exist.

| Sage Field | XML Field | Example | Field Type | Input | Notes |
| --- | --- | --- | --- | --- | --- |
| Price Name | product_sales_price_type/name | Sales Price | string | Required |  |
| Price | price | 5.99 | double | Required |  |
| Includes VAT | price_includes_tax | true | boolean | Optional |  |

```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <stock_items>
    <stock_item>
      <sales_prices>
        <sales_price>
          <product_sales_price_type>
            <name>Sales Price</name>
          </product_sales_price_type>
          <price>5.99</price>
          <price_includes_tax>false</price_includes_tax>
        </sales_price>
      </sales_prices>
    </stock_item>
  </stock_items>
</sage_one_company>
```
