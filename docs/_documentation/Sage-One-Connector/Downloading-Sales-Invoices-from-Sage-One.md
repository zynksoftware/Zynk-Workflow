---
slug: downloading-sales-invoices-from-sage-one
redirect_from: "/article/856-download-sales-invoices"
title: Downloading Sales Invoices from Sage One
---
This task will download Sales Invoices from your instance of Sage One.

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
A sample output file is shown below. See [Sage One Sales Invoice XML](sage-one-sales-invoice-xml) for full documentation of the XML format.
```xml
<?xml version="1.0"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <sales_invoices>
    <sales_invoice>
      <legacy_id>48200089</legacy_id>
      <id>ea84cdf6e4ad11e7aa730a57719b2edb</id>
      <displayed_as>SI-48</displayed_as>
      <path>/sales_invoices/ea84cdf6e4ad11e7aa730a57719b2edb</path>
      <transaction>
        <legacy_id>110238255</legacy_id>
        <id>ea914809e4ad11e7aa730a57719b2edb</id>
        <path>/transactions/ea914809e4ad11e7aa730a57719b2edb</path>
        <created_at xsi:nil="true" />
        <updated_at xsi:nil="true" />
        <deleted xsi:nil="true" />
        <total xsi:nil="true" />
      </transaction>
      <created_at>2017-12-19T11:15:27Z</created_at>
      <updated_at>2017-12-19T11:15:27Z</updated_at>
      <contact_name>Zynk Software</contact_name>
      <contact_reference>ZYNK0001</contact_reference>
      <contact>
        <legacy_id>2840943</legacy_id>
        <id>8a9b4b1f174c11e691e20a5d7cf84c3e</id>
        <displayed_as>Zynk Software (ZYNK0001)</displayed_as>
        <path>/contacts/8a9b4b1f174c11e691e20a5d7cf84c3e</path>
      </contact>
      <invoice_number>SI-48</invoice_number>
      <date>2017-12-19T00:00:00</date>
      <due_date>2018-01-18T00:00:00</due_date>
      <net_amount>10</net_amount>
      <tax_amount>0</tax_amount>
      <total_amount>10</total_amount>
      <total_paid>0</total_paid>
      <outstanding_amount>10</outstanding_amount>
      <total_quantity>1</total_quantity>
      <currency>
        <legacy_id>10</legacy_id>
        <id>GBP</id>
        <displayed_as>Pound Sterling (GBP)</displayed_as>
        <path>/currencies/GBP</path>
      </currency>
      <exchange_rate>1</exchange_rate>
      <inverse_exchange_rate>1</inverse_exchange_rate>
      <base_currency_net_amount>10</base_currency_net_amount>
      <base_currency_tax_amount>0</base_currency_tax_amount>
      <base_currency_total_amount>10</base_currency_total_amount>
      <base_currency_outstanding_amount>10</base_currency_outstanding_amount>
      <status>
        <legacy_id>1</legacy_id>
        <id>UNPAID</id>
        <displayed_as>Unpaid</displayed_as>
        <path>/artefact_statuses/UNPAID</path>
      </status>
      <invoice_lines>
        <invoice_line>
          <legacy_id>57311833</legacy_id>
          <id>ea8cf301e4ad11e7aa730a57719b2edb</id>
          <displayed_as>Free text item</displayed_as>
          <description>Free text item</description>
          <ledger_account>
            <legacy_id>2654285</legacy_id>
            <id>d959c74d180811e691e20a5d7cf84c3e</id>
            <displayed_as>Sales Type A (4000)</displayed_as>
            <path>/ledger_accounts/d959c74d180811e691e20a5d7cf84c3e</path>
          </ledger_account>
          <quantity>1</quantity>
          <unit_price>10</unit_price>
          <net_amount>10</net_amount>
          <tax_rate>
            <legacy_id>1</legacy_id>
            <id>GB_STANDARD</id>
            <displayed_as>Standard 20.00%</displayed_as>
            <path>/tax_rates/GB_STANDARD</path>
          </tax_rate>
          <tax_amount>0</tax_amount>
          <tax_breakdown />
          <total_amount>10</total_amount>
          <base_currency_unit_price>10</base_currency_unit_price>
          <base_currency_net_amount>10</base_currency_net_amount>
          <base_currency_tax_amount>0</base_currency_tax_amount>
          <base_currency_tax_breakdown />
          <base_currency_total_amount>10</base_currency_total_amount>
        </invoice_line>
      </invoice_lines>
      <tax_analysis>
        <tax>
          <tax_rate>
            <legacy_id>1</legacy_id>
            <id>GB_STANDARD</id>
            <displayed_as>Standard 20.00%</displayed_as>
            <path>/tax_rates/GB_STANDARD</path>
          </tax_rate>
          <net_amount>10</net_amount>
          <tax_amount>0</tax_amount>
          <total_amount>10</total_amount>
          <goods_amount>0</goods_amount>
          <service_amount>0</service_amount>
        </tax>
      </tax_analysis>
      <withholding_tax_rate xsi:nil="true" />
      <withholding_tax_amount xsi:nil="true" />
      <base_currency_withholding_tax_amount xsi:nil="true" />
      <main_address_free_form>Zynk Software
6-8 Charlotte Square
Newcastle upon Tyne
Tyne &amp; Wear
NE1 4XF</main_address_free_form>
      <main_address>
        <legacy_id>28243375</legacy_id>
        <id>ea8a1782e4ad11e7aa730a57719b2edb</id>
        <displayed_as>Zynk Software
6-8 Charlotte Square
Newcastle upon Tyne
Tyne &amp; Wear
NE1 4XF</displayed_as>
        <path>/contacts/ea8a1782e4ad11e7aa730a57719b2edb</path>
        <created_at xsi:nil="true" />
        <updated_at xsi:nil="true" />
        <deleted_at xsi:nil="true" />
        <address_type>
          <legacy_id>3</legacy_id>
          <id>SALES</id>
          <displayed_as>Sales</displayed_as>
          <path>/address_types/SALES</path>
        </address_type>
        <address_line_1>Zynk Software</address_line_1>
        <address_line_2>6-8 Charlotte Square</address_line_2>
        <city>Newcastle upon Tyne</city>
        <region>Tyne &amp; Wear</region>
        <postal_code>NE1 4XF</postal_code>
        <country>
          <legacy_id>218</legacy_id>
          <id>GB</id>
          <displayed_as>United Kingdom (GB)</displayed_as>
          <path>/countries/GB</path>
        </country>
        <country_group>
          <legacy_id>4</legacy_id>
          <id>GBIE</id>
          <displayed_as>UK &amp; Ireland</displayed_as>
          <path>/country_groups/GBIE</path>
        </country_group>
        <is_main_address xsi:nil="true" />
      </main_address>
      <shipping_net_amount>0</shipping_net_amount>
      <shipping_tax_amount>0</shipping_tax_amount>
      <shipping_total_amount>0</shipping_total_amount>
      <base_currency_shipping_net_amount>0</base_currency_shipping_net_amount>
      <base_currency_shipping_tax_amount>0</base_currency_shipping_tax_amount>
      <base_currency_shipping_total_amount>0</base_currency_shipping_total_amount>
      <total_discount_amount>0</total_discount_amount>
      <sent>false</sent>
    </sales_invoice>
  </sales_invoices>
</sage_one_company>
```