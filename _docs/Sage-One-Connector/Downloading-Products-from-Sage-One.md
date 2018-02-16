---
slug: downloading-products-from-sage-one
redirect_from: "/article/854-download-products"
title: Downloading Products from Sage One
---
This task will download Products from your instance of Sage One.

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
A sample output file is shown below. See [Sage One Product XML](sage-one-product-xml) for full documentation of the XML format.
```xml
<?xml version="1.0"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <products>
    <product>
      <legacy_id>1757214</legacy_id>
      <id>2205825f270e11e691e20a5d7cf84c3e</id>
      <displayed_as>Another Side Of Bob Dylan</displayed_as>
      <path>/products/2205825f270e11e691e20a5d7cf84c3e</path>
      <created_at>2016-05-31T09:00:33Z</created_at>
      <updated_at>2016-05-31T09:00:33Z</updated_at>
      <deleted_at xsi:nil="true" />
      <item_code>ASOBD</item_code>
      <description>Another Side Of Bob Dylan</description>
      <notes>1964 classic from Bob Dylan, including Chimes Of Freedom.</notes>
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
      <cost_price>0</cost_price>
      <sales_prices>
        <sales_price>
          <legacy_id>4405060</legacy_id>
          <id>2206173c270e11e691e20a5d7cf84c3e</id>
          <displayed_as>Sales Price</displayed_as>
          <price>7.99</price>
          <price_includes_tax>true</price_includes_tax>
          <price_name>Sales Price</price_name>
          <product_sales_price_type>
            <legacy_id>1052117</legacy_id>
            <id>7a34ae55175011e691e20a5d7cf84c3e</id>
            <displayed_as>Sales Price</displayed_as>
            <path>/product_sales_price_types/7a34ae55175011e691e20a5d7cf84c3e</path>
          </product_sales_price_type>
        </sales_price>
        <sales_price>
          <legacy_id>4405061</legacy_id>
          <id>22074de9270e11e691e20a5d7cf84c3e</id>
          <displayed_as>Trade</displayed_as>
          <price>0</price>
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
          <legacy_id>4405062</legacy_id>
          <id>220838ac270e11e691e20a5d7cf84c3e</id>
          <displayed_as>Wholesale</displayed_as>
          <price>0</price>
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
    </product>
  </products>
</sage_one_company>
```