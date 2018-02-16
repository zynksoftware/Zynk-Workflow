---
slug: downloading-stock-items-from-sage-one
title: Downloading Stock Items from Sage One
---
This task will download stock items from your instance of Sage One.

## Settings
### Sage One Connection
_Required_  
The connection to Sage One to use. See [Connecting to Sage One](connecting-to-sage-one) if you require more information on how to create/manage connections.

### Export All
_Required_  
Set to true to export all records from Sage One, or false to only export those updated since the date specified in the 'Export From' setting.

### Export From
_Required_  
The date to export new/modified records from. This setting only takes effect when 'Export All' is set to false. The date will update automatically each time the task runs.

### Output File
_Required_  
The file to save the downloaded records to.

### Items Per Page
_Required_  
The number records to fetch per request to Sage One. Increasing this value will reduce the number of requests needed to export the records, which may reduce the time taken.

### Search
_Optional_  
Enter a search to filter the records returned.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample output file is shown below. See [Sage One Stock Item XML](sage-one-stock-item-xml) for full documentation of the XML format.
```xml
<?xml version="1.0"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <stock_items>
    <stock_item>
      <legacy_id>4597716</legacy_id>
      <id>e9460b98e40311e7aa730a57719b2edb</id>
      <external_id>97575</external_id>
      <displayed_as>50 Colouring Pencils</displayed_as>
      <path>/stock_items/e9460b98e40311e7aa730a57719b2edb</path>
      <created_at>2017-12-18T14:58:30Z</created_at>
      <updated_at>2017-12-18T15:01:05Z</updated_at>
      <deleted_at xsi:nil="true" />
      <item_code>PENCILS2</item_code>
      <description>50 Colouring Pencils</description>
      <notes />
      <sales_ledger_account>
        <legacy_id>2654285</legacy_id>
        <id>d959c74d180811e691e20a5d7cf84c3e</id>
        <displayed_as>Sales Type A (4000)</displayed_as>
        <path>/ledger_accounts/d959c74d180811e691e20a5d7cf84c3e</path>
      </sales_ledger_account>
      <sales_tax_rate>
        <legacy_id>1</legacy_id>
        <id>GB_STANDARD</id>
        <displayed_as>Standard 20.00%</displayed_as>
        <path>/tax_rates/GB_STANDARD</path>
      </sales_tax_rate>
      <purchase_ledger_account>
        <legacy_id>2654291</legacy_id>
        <id>d959cd0e180811e691e20a5d7cf84c3e</id>
        <displayed_as>Cost of sales - goods (5000)</displayed_as>
        <path>/ledger_accounts/d959cd0e180811e691e20a5d7cf84c3e</path>
      </purchase_ledger_account>
      <purchase_tax_rate>
        <legacy_id>1</legacy_id>
        <id>GB_STANDARD</id>
        <displayed_as>Standard 20.00%</displayed_as>
        <path>/tax_rates/GB_STANDARD</path>
      </purchase_tax_rate>
      <cost_price>2</cost_price>
      <sales_prices>
        <sales_price>
          <legacy_id>12822312</legacy_id>
          <id>e948036ee40311e7aa730a57719b2edb</id>
          <displayed_as>Sales Price</displayed_as>
          <price>5</price>
          <price_includes_tax>false</price_includes_tax>
          <price_name>Sales Price</price_name>
          <product_sales_price_type>
            <legacy_id>1052117</legacy_id>
            <id>7a34ae55175011e691e20a5d7cf84c3e</id>
            <displayed_as>Sales Price</displayed_as>
            <path>/product_sales_price_types/7a34ae55175011e691e20a5d7cf84c3e</path>
          </product_sales_price_type>
        </sales_price>
        <sales_price>
          <legacy_id>12822313</legacy_id>
          <id>e94c3dfae40311e7aa730a57719b2edb</id>
          <displayed_as>Trade</displayed_as>
          <price>4</price>
          <price_includes_tax>false</price_includes_tax>
          <price_name>Trade</price_name>
          <product_sales_price_type>
            <legacy_id>1052118</legacy_id>
            <id>7a34b512175011e691e20a5d7cf84c3e</id>
            <displayed_as>Trade</displayed_as>
            <path>/product_sales_price_types/7a34b512175011e691e20a5d7cf84c3e</path>
          </product_sales_price_type>
        </sales_price>
        <sales_price>
          <legacy_id>12822314</legacy_id>
          <id>e94ce37ee40311e7aa730a57719b2edb</id>
          <displayed_as>Wholesale</displayed_as>
          <price>3</price>
          <price_includes_tax>false</price_includes_tax>
          <price_name>Wholesale</price_name>
          <product_sales_price_type>
            <legacy_id>1052119</legacy_id>
            <id>7a34bf52175011e691e20a5d7cf84c3e</id>
            <displayed_as>Wholesale</displayed_as>
            <path>/product_sales_price_types/7a34bf52175011e691e20a5d7cf84c3e</path>
          </product_sales_price_type>
        </sales_price>
      </sales_prices>
      <reorder_level>10</reorder_level>
      <reorder_quantity>20</reorder_quantity>
      <location>Home</location>
      <barcode>402184102948314</barcode>
      <supplier_part_number>PENCIL-50</supplier_part_number>
      <weight>1</weight>
      <measurement_unit>kg</measurement_unit>
      <weight_converted>1000</weight_converted>
      <quantity_in_stock>0</quantity_in_stock>
      <last_cost_price>0</last_cost_price>
      <last_cost_price_stock_value>0</last_cost_price_stock_value>
      <average_cost_price>0</average_cost_price>
      <average_cost_price_stock_value>0</average_cost_price_stock_value>
      <cost_price_last_updated xsi:nil="true" />
    </stock_item>
  </stock_items>
</sage_one_company>
```