---
slug: sage-one-product-xml
title: Sage One Product XML
---
The [Import Products](uploading-products-to-sage-one) task allows you to create new and update existing non-stock product records in Sage One, using the XML format described below. Any Sage One fields not documented below are not supported with our import.   

A complete example of the XML is shown below. This represents the minimum information required to create a non-stock product record in Sage One:

```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <products>
    <product>
      <description>50 Coloured Pencils</description>
      <sales_ledger_account>
        <nominal_code>4000</nominal_code>
      </sales_ledger_account>
      <purchase_ledger_account>
        <nominal_code>5000</nominal_code>
      </purchase_ledger_account>
    </product>
  </products>
</sage_one_company>
```

## Product Identification
The following fields are use to identify the product to create/update. At least one of these fields should be provided. If more than one is provided, Zynk will look for a match based on each field in turn, in the order they are listed below.

| Sage Field | XML Field | Example | Field Type | Input | Notes |
| --- | --- | --- | --- | --- | --- |
| Item Information > Item Code | item_code | PENCILS | string | Optional |  |
| - | id | 0dfbbb5d174611e691e20a5d7cf84c3e | GUID | Optional | Sage's unique product ID. |
| - | external_id | PENCILS | string  | Optional | The ID of the product from the source data. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <products>
    <product>
      <item_code>PENCILS</item_code>
      <id>0dfbbb5d174611e691e20a5d7cf84c3e</id>
      <external_id>PENCILS</external_id>
    </product>
  </products>
</sage_one_company>
```

## Product Details
The following product fields can be set using Zynk.

| Sage Field | XML Field | Example | Field Type | Input | Notes |
| --- | --- | --- | --- | --- | --- |
| Item Information > Item Code | item_code | PENCILS | string | Optional |  |
| Item Information > Description | description | 50 Coloured Pencils | string | Required |  |
| Item Information > Inactive | active | true | string | Optional | Set to true to make the product active, or false to make it inactive |
| Sales > Sales Account | sales_ledger_account/nominal_code | 4000 | string | Dependant | At least one of the `sales_ledger_account` elements must be provided |
| Sales > Sales Account | sales_ledger_account/name | Sales Type A | string | Dependant | At least one of the `sales_ledger_account` elements must be provided |
| Sales > Sales Account | sales_ledger_account/display_name | Sales Type A (4000) | string | Dependant | At least one of the `sales_ledger_account` elements must be provided |
| Sales > VAT Rate | sales_tax_rate/id | GB_STANDARD | string | Optional |  |
| Sales > VAT Rate | sales_tax_rate/name | Standard 20.00% | string | Optional |  |
| Purchases > Purchase Description | purchase_description | 50 Coloured Pencils | string | Optional |  |
| Purchases > Cost Price | cost_price | 2.50 | double | Optional |  |
| Purchases > Purchase Account | purchase_ledger_account/nominal_code | 5000 | string | Optional |  |
| Purchases > Purchase Account | purchase_ledger_account/name | Cost of sales - goods | string | Optional |  |
| Purchases > Purchase Account | purchase_ledger_account/display_name | Cost of sales - goods (5000) | string | Optional |  |
| Purchases > VAT Rate | purchase_tax_rate/id | GB_STANDARD | string | Optional |  |
| Purchases > VAT Rate | purchase_tax_rate/name | Standard 20.00% | string | Optional |  |
| Additional Information > Notes | Notes | A pack of 50 coloured pencils | string | Optional |  |

```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <products>
    <product>
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
      <notes>A pack of 50 coloured pencils</notes>
    </product>
  </products>
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
  <products>
    <product>
      <sales_prices>
        <sales_price>
          <product_sales_price_type>
            <name>Sales Price</name>
          </product_sales_price_type>
          <price>5.99</price>
          <price_includes_tax>false</price_includes_tax>
        </sales_price>
      </sales_prices>
    </product>
  </products>
</sage_one_company>
```
