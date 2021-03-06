---
slug: exporting-sales-transactions-from-sage-200-online
redirect_from: "/article/exporting-sales-transactions-from-sage-200-online"
title: Exporting Sales Transactions From Sage 200 Online
---
This task will download sales transactions from Sage 200 Online in [Sage 200 Online Sales Transaction XML](sage-200-online-sales-transaction-xml) format.

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
Allows a filter to be set to limit the data that is returned. For example, you can return sales transactions for the customer with ID 1 using: `customer_id eq 1`

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
<SalesTransactions xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <SalesTransaction>
    <id>16428</id>
    <date_time_updated>2016-05-09T11:24:40.013</date_time_updated>
    <trader_transaction_type>TradingAccountEntryTypeInvoice</trader_transaction_type>
    <reference>0000000001</reference>
    <second_reference>0000000001</second_reference>
    <queried />
    <transaction_date>2016-05-09T00:00:00</transaction_date>
    <posted_date>2016-05-09T00:00:00</posted_date>
    <due_date>2016-06-08T00:00:00</due_date>
    <document_goods_value>20.00</document_goods_value>
    <document_gross_value>24.00</document_gross_value>
    <document_tax_value>4.00</document_tax_value>
    <document_discount_value>0.00</document_discount_value>
    <discount_percent>0.00</discount_percent>
    <document_tax_discount_value>0.00</document_tax_discount_value>
    <document_allocated_value>0.00</document_allocated_value>
    <document_outstanding_value>24.00</document_outstanding_value>
    <base_goods_value>20.0</base_goods_value>
    <base_gross_value>24.0</base_gross_value>
    <base_tax_value>4.0</base_tax_value>
    <base_discount_value>0.0</base_discount_value>
    <base_tax_discount_value>0.0</base_tax_discount_value>
    <base_allocated_value>0.0</base_allocated_value>
    <control_value_in_base_currency>24.00</control_value_in_base_currency>
    <exchange_rate>1.000000</exchange_rate>
    <settled_immediately>false</settled_immediately>
    <discount_days>0</discount_days>
    <urn>1</urn>
    <user_name>Demo Site</user_name>
    <customer_id>14950</customer_id>
    <customer>
      <id>14950</id>
      <date_time_updated>2016-05-23T15:42:57.307</date_time_updated>
      <reference>ZYNK0001</reference>
      <name>Zynk Software</name>
      <short_name>Zynk Sof</short_name>
      <balance>48.00</balance>
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
  </SalesTransaction>
</SalesTransactions>
```
