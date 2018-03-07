---
slug: exporting-sales-orders-from-sage-200-online
redirect_from: "/article/exporting-sales-orders-from-sage-200-online"
title: Exporting Sales Orders From Sage 200 Online
---
This task will download sales orders from Sage 200 Online to an XML file.

## Settings
### Sage 200 Online Connection
_Required_  
The connection to Sage 200 Online to use. See the [Connecting to Sage 200 Online](connecting-to-sage-200-online) article if you require more information on how to create/manage connections.

### Export Settings > Date Modified
_Required_  
When the 'Export Modified or All Records' setting is set to 'Modified', only records modified after this date will be downloaded. The date will update automatically each time the task runs, to ensure that only records modified since the task last ran will be downloaded.

### Export Settings > Export Modified or All Records
_Required_  
Used to choose which records should be included in the download. The available options are:

* __All__ - All records will be downloaded, regardless of whether or not they have been updated since the task last ran.
* __Modified__ - Only records created or updated since the task last ran will be downloaded.

### Filter
_Optional_  
Allows a filter to be set to limit the data that is returned. For example, you can return sales orders where the net value is greater than 100 using: `total_net_value gt 100`

Sage 200 Online uses the OData protocol, and expects the filter to be specified in this format. You can find more information on OData filters [here](http://www.odata.org/getting-started/basic-tutorial/#queryData).

### Output File
_Required_  
The name of the file to save the downloaded records to.

### Page Size
_Required_  
The number of records to include in each page of results downloaded from Sage. Increasing this value will speed up the download, but will use more memory. Defaults to 50.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample output file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<SalesOrders xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesOrder>
    <id>16976</id>
    <date_time_updated>2016-05-17T08:57:38.003</date_time_updated>
    <document_no>0000000002</document_no>
    <document_date>2016-05-17T00:00:00</document_date>
    <document_status>EnumDocumentStatusLive</document_status>
    <customer_id>14950</customer_id>
    <exchange_rate>1.000000</exchange_rate>
    <subtotal_goods_value>45.00</subtotal_goods_value>
    <total_net_value>45.00</total_net_value>
    <total_tax_value>9.00</total_tax_value>
    <total_gross_value>54.00</total_gross_value>
    <customer_document_no>abc123</customer_document_no>
    <use_invoice_address>false</use_invoice_address>
    <settlement_discount_days>0</settlement_discount_days>
    <settlement_discount_percent>0.00</settlement_discount_percent>
    <customer>
      <id>14950</id>
      <date_time_updated>2016-05-23T09:34:10.79</date_time_updated>
      <reference>ZYNK0001</reference>
      <name>Zynk Software</name>
      <short_name>Zynk Sof</short_name>
      <balance>24.00</balance>
      <on_hold>false</on_hold>
      <currency_id>1</currency_id>
      <exchange_rate_type>ExchangeRateSingle</exchange_rate_type>
      <telephone_country_code />
      <telephone_area_code />
      <telephone_subscriber_number />
      <fax_country_code />
      <fax_area_code />
      <fax_subscriber_number />
      <website />
      <credit_limit>0.00</credit_limit>
      <country_code_id>13</country_code_id>
      <default_tax_code_id>2</default_tax_code_id>
      <vat_number />
      <analysis_code_1 />
      <analysis_code_2 />
      <analysis_code_3 />
      <analysis_code_4 />
      <analysis_code_5 />
      <duns_code />
    </customer>
    <delivery_address>
      <id>17066</id>
      <date_time_updated>2016-05-17T08:57:38.033</date_time_updated>
      <address_1>Nelson House</address_1>
      <address_2>Jesmond</address_2>
      <address_3 />
      <address_4 />
      <city>Newcaslte</city>
      <county>Tyne & Wear</county>
      <postcode>NE2 3AE</postcode>
      <address_country_code_id>13</address_country_code_id>
      <customer_id xsi:nil="true" />
    </delivery_address>
    <lines>
      <line>
        <id>16977</id>
        <date_time_updated>2016-05-17T08:55:10.363</date_time_updated>
        <line_number>1</line_number>
        <line_type>EnumLineTypeStandard</line_type>
        <sop_order_id>16976</sop_order_id>
        <code>TEST001</code>
        <description>Test Product</description>
        <tax_code_id>2</tax_code_id>
        <line_quantity>4.0</line_quantity>
        <allocated_quantity>4.0</allocated_quantity>
        <despatch_receipt_quantity>0.0</despatch_receipt_quantity>
        <invoice_credit_quantity>0.0</invoice_credit_quantity>
        <selling_unit_price>10.0</selling_unit_price>
        <unit_discount_percent>0.0</unit_discount_percent>
        <unit_discount_value>0.0</unit_discount_value>
        <cost_price>4.0</cost_price>
        <show_on_customer_docs>true</show_on_customer_docs>
        <show_on_picking_list_type>Show</show_on_picking_list_type>
        <line_total_value>40.0</line_total_value>
        <line_tax_value>8.0</line_tax_value>
        <product_id>15536</product_id>
        <warehouse_id>1</warehouse_id>
      </line>
      <line>
        <id>17006</id>
        <date_time_updated>2016-05-17T08:57:37.893</date_time_updated>
        <line_number>2</line_number>
        <line_type>EnumLineTypeFreeText</line_type>
        <sop_order_id>16976</sop_order_id>
        <code />
        <description>Blah blah</description>
        <tax_code_id>2</tax_code_id>
        <line_quantity>1.0</line_quantity>
        <allocated_quantity>0.0</allocated_quantity>
        <despatch_receipt_quantity>0.0</despatch_receipt_quantity>
        <invoice_credit_quantity>0.0</invoice_credit_quantity>
        <selling_unit_price>5.0</selling_unit_price>
        <unit_discount_percent>0.0</unit_discount_percent>
        <unit_discount_value>0.0</unit_discount_value>
        <cost_price>0.0</cost_price>
        <show_on_customer_docs>true</show_on_customer_docs>
        <show_on_picking_list_type>Show</show_on_picking_list_type>
        <line_total_value>5.0</line_total_value>
        <line_tax_value>1.0</line_tax_value>
        <product_id xsi:nil="true" />
        <warehouse_id xsi:nil="true" />
      </line>
    </lines>
  </SalesOrder>
</SalesOrders>
```
