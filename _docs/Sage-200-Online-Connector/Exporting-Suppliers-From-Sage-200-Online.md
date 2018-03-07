---
slug: exporting-suppliers-from-sage-200-online
redirect_from: "/article/exporting-suppliers-from-sage-200-online"
title: Exporting Suppliers From Sage 200 Online
---
This task will download suppliers from Sage 200 Online to an XML file.

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
Allows a filter to be set to limit the data that is returned. For example, you can return the suppliers with a balance greater than 0 using: `balance gt 0`

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
<Suppliers xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Supplier>
    <external_id>321</external_id>
    <id>18076</id>
    <date_time_updated>2016-05-20T15:43:55.353</date_time_updated>
    <reference>ZYNK0001</reference>
    <name>Zynk Software</name>
    <short_name>Zynk Sof</short_name>
    <balance>0.00</balance>
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
    <credit_limit>1000.00</credit_limit>
    <country_code_id>13</country_code_id>
    <default_tax_code_id>2</default_tax_code_id>
    <vat_number />
    <analysis_code_1 />
    <analysis_code_2 />
    <analysis_code_3 />
    <analysis_code_4 />
    <analysis_code_5 />
    <country_code>
      <id>13</id>
      <date_time_updated>2015-10-30T22:33:16.67</date_time_updated>
      <name>Great Britain</name>
      <code>GB</code>
      <eu_member>true</eu_member>
    </country_code>
    <currency>
      <id>1</id>
      <date_time_updated>2015-10-30T22:33:17.53</date_time_updated>
      <symbol>£</symbol>
      <name>Pound Sterling</name>
      <core_currency_rate>1.000000</core_currency_rate>
      <euro_currency_rate>1.000000</euro_currency_rate>
      <currency_iso_code_id>49</currency_iso_code_id>
      <is_base_currency>true</is_base_currency>
      <is_euro_currency>false</is_euro_currency>
    </currency>
    <default_tax_code>
      <id>2</id>
      <date_time_updated>2015-10-30T22:33:16.473</date_time_updated>
      <code>1</code>
      <name>Standard Rate</name>
      <tax_rate>20.00</tax_rate>
    </default_tax_code>
    <main_address>
      <id>18077</id>
      <date_time_updated>2016-05-20T15:43:55.413</date_time_updated>
      <address_1>Nelson House</address_1>
      <address_2>Jesmond</address_2>
      <address_3 />
      <address_4 />
      <city>Newcastle</city>
      <county>Tyne & Wear</county>
      <postcode>NE2 3AE</postcode>
      <address_country_code_id>13</address_country_code_id>
      <supplier_id>18076</supplier_id>
    </main_address>
    <bank>
      <id>18166</id>
      <date_time_updated>2016-05-20T15:43:58.43</date_time_updated>
      <supplier_id>18076</supplier_id>
      <sort_code>123456</sort_code>
      <account_number>123456789</account_number>
      <account_name>Current Account</account_name>
      <bank_payment_reference />
      <iban_number />
      <bic_number />
      <roll_number />
      <bacs_reference />
      <additional_reference />
      <non_uk_sort_code />
    </bank>
  </Supplier>
</Suppliers>
```
