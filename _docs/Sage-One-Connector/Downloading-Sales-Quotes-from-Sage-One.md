---
slug: downloading-sales-quotes-from-sage-one
title: Downloading Sales Quotes from Sage One
---
This task will download sales quotes from your instance of Sage One.

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
A sample output file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <sales_quotes>
    <sales_quote>
      <legacy_id>73664942</legacy_id>
      <id>8dbbd424c0c911e8bad90617b3da4b8a</id>
      <displayed_as>SQ-2</displayed_as>
      <path>/sales_quotes/8dbbd424c0c911e8bad90617b3da4b8a</path>
      <created_at>2018-09-25T13:47:33Z</created_at>
      <updated_at>2018-09-25T13:47:33Z</updated_at>
      <quote_number>SQ-2</quote_number>
      <contact_name>Smoke on the Water</contact_name>
      <contact_reference>SMW</contact_reference>
      <contact>
        <legacy_id>33329885</legacy_id>
        <id>0dbf1a56c0c911e8bad90617b3da4b8a</id>
        <displayed_as>Smoke on the Water (SMW)</displayed_as>
        <path>/contacts/0dbf1a56c0c911e8bad90617b3da4b8a</path>
        <created_at xsi:nil="true" />
        <updated_at xsi:nil="true" />
        <credit_limit xsi:nil="true" />
        <credit_days xsi:nil="true" />
        <deletable xsi:nil="true" />
      </contact>
      <date>2018-09-25T00:00:00</date>
      <expiry_date>2018-10-25T00:00:00</expiry_date>
      <reference>QTE1/SMW</reference>
      <main_address_free_form>100 Main road
London
UK</main_address_free_form>
      <delivery_address_free_form>100 Main road
London
UK</delivery_address_free_form>
      <main_address>
        <legacy_id>47401271</legacy_id>
        <id>8dca5addc0c911e8bad90617b3da4b8a</id>
        <displayed_as>100 Main road
London
UK</displayed_as>
        <path>/contacts/8dca5addc0c911e8bad90617b3da4b8a</path>
        <created_at xsi:nil="true" />
        <updated_at xsi:nil="true" />
        <deleted_at xsi:nil="true" />
        <address_type>
          <legacy_id>3</legacy_id>
          <id>SALES</id>
          <displayed_as>Sales</displayed_as>
          <path>/address_types/SALES</path>
        </address_type>
        <address_line_1>100 Main road</address_line_1>
        <address_line_2 />
        <city>London</city>
        <region>UK</region>
        <postal_code />
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
      <delivery_address>
        <legacy_id>47401272</legacy_id>
        <id>8dcb76fdc0c911e8bad90617b3da4b8a</id>
        <displayed_as>100 Main road
London
UK</displayed_as>
        <path>/contacts/8dcb76fdc0c911e8bad90617b3da4b8a</path>
        <created_at xsi:nil="true" />
        <updated_at xsi:nil="true" />
        <deleted_at xsi:nil="true" />
        <address_type>
          <legacy_id>1</legacy_id>
          <id>DELIVERY</id>
          <displayed_as>Delivery</displayed_as>
          <path>/address_types/DELIVERY</path>
        </address_type>
        <address_line_1>100 Main road</address_line_1>
        <address_line_2 />
        <city>London</city>
        <region>UK</region>
        <postal_code />
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
      </delivery_address>
      <notes>Quote 1 notes</notes>
      <terms_and_conditions>T^C for SMW</terms_and_conditions>
      <shipping_net_amount>0</shipping_net_amount>
      <shipping_tax_rate>
        <legacy_id>1</legacy_id>
        <id>GB_STANDARD</id>
        <displayed_as>Standard 20.00%</displayed_as>
        <path>/tax_rates/GB_STANDARD</path>
        <created_at xsi:nil="true" />
        <updated_at xsi:nil="true" />
        <percentage xsi:nil="true" />
        <is_visible xsi:nil="true" />
        <is_combined_rate xsi:nil="true" />
        <editable xsi:nil="true" />
        <deletable xsi:nil="true" />
      </shipping_tax_rate>
      <shipping_tax_amount>0</shipping_tax_amount>
      <shipping_tax_breakdown />
      <shipping_total_amount>0</shipping_total_amount>
      <net_amount>50</net_amount>
      <tax_amount>10</tax_amount>
      <total_amount>60</total_amount>
      <currency>
        <legacy_id>10</legacy_id>
        <id>GBP</id>
        <displayed_as>Pound Sterling (GBP)</displayed_as>
        <path>/currencies/GBP</path>
      </currency>
      <exchange_rate>1</exchange_rate>
      <base_currency_shipping_net_amount>0</base_currency_shipping_net_amount>
      <base_currency_shipping_tax_amount>0</base_currency_shipping_tax_amount>
      <base_currency_shipping_tax_breakdown />
      <base_currency_shipping_total_amount>0</base_currency_shipping_total_amount>
      <base_currency_net_amount>50</base_currency_net_amount>
      <base_currency_tax_amount>10</base_currency_tax_amount>
      <base_currency_total_amount>60</base_currency_total_amount>
      <status>
        <id>EXPIRED</id>
        <displayed_as>Expired</displayed_as>
      </status>
      <quote_lines>
        <quote_line>
          <legacy_id>89026868</legacy_id>
          <id>8dc9c8adc0c911e8bad90617b3da4b8a</id>
          <displayed_as>Service 1</displayed_as>
          <description>Service 1</description>
          <service>
            <legacy_id>5985002</legacy_id>
            <id>3511cae9c0c911e8bad90617b3da4b8a</id>
            <displayed_as>Service 1</displayed_as>
            <path>/services/3511cae9c0c911e8bad90617b3da4b8a</path>
            <created_at xsi:nil="true" />
            <updated_at xsi:nil="true" />
            <deleted_at xsi:nil="true" />
            <active xsi:nil="true" />
          </service>
          <ledger_account>
            <legacy_id>2654285</legacy_id>
            <id>d959c74d180811e691e20a5d7cf84c3e</id>
            <displayed_as>Sales Type A (4000)</displayed_as>
            <path>/ledger_accounts/d959c74d180811e691e20a5d7cf84c3e</path>
            <created_at xsi:nil="true" />
            <updated_at xsi:nil="true" />
            <included_in_chart xsi:nil="true" />
            <nominal_code xsi:nil="true" />
            <fixed_tax_rate xsi:nil="true" />
            <visible_in_banking xsi:nil="true" />
            <visible_in_expenses xsi:nil="true" />
            <visible_in_journals xsi:nil="true" />
            <visible_in_other_payments xsi:nil="true" />
            <visible_in_other_receipts xsi:nil="true" />
            <visible_in_reporting xsi:nil="true" />
            <visible_in_sales xsi:nil="true" />
            <is_control_account xsi:nil="true" />
          </ledger_account>
          <quantity>1</quantity>
          <unit_price>50</unit_price>
          <net_amount>50</net_amount>
          <tax_rate>
            <legacy_id>1</legacy_id>
            <id>GB_STANDARD</id>
            <displayed_as>Standard 20.00%</displayed_as>
            <path>/tax_rates/GB_STANDARD</path>
            <created_at xsi:nil="true" />
            <updated_at xsi:nil="true" />
            <percentage xsi:nil="true" />
            <is_visible xsi:nil="true" />
            <is_combined_rate xsi:nil="true" />
            <editable xsi:nil="true" />
            <deletable xsi:nil="true" />
          </tax_rate>
          <tax_amount>10</tax_amount>
          <tax_breakdown>
            <tax>
              <tax_rate>
                <legacy_id>1</legacy_id>
                <id>GB_STANDARD</id>
                <displayed_as>Standard 20.00%</displayed_as>
                <path>/tax_rates/GB_STANDARD</path>
                <created_at xsi:nil="true" />
                <updated_at xsi:nil="true" />
                <percentage xsi:nil="true" />
                <is_visible xsi:nil="true" />
                <is_combined_rate xsi:nil="true" />
                <editable xsi:nil="true" />
                <deletable xsi:nil="true" />
              </tax_rate>
              <percentage>20</percentage>
              <amount>10</amount>
            </tax>
          </tax_breakdown>
          <discount_amount>0</discount_amount>
          <total_amount>60</total_amount>
          <base_currency_unit_price>50</base_currency_unit_price>
          <base_currency_net_amount>50</base_currency_net_amount>
          <base_currency_tax_amount>10</base_currency_tax_amount>
          <base_currency_tax_breakdown>
            <tax>
              <tax_rate>
                <legacy_id>1</legacy_id>
                <id>GB_STANDARD</id>
                <displayed_as>Standard 20.00%</displayed_as>
                <path>/tax_rates/GB_STANDARD</path>
                <created_at xsi:nil="true" />
                <updated_at xsi:nil="true" />
                <percentage xsi:nil="true" />
                <is_visible xsi:nil="true" />
                <is_combined_rate xsi:nil="true" />
                <editable xsi:nil="true" />
                <deletable xsi:nil="true" />
              </tax_rate>
              <percentage>20</percentage>
              <amount>10</amount>
            </tax>
          </base_currency_tax_breakdown>
          <base_currency_total_amount>60</base_currency_total_amount>
          <base_currency_discount_amount>0</base_currency_discount_amount>
        </quote_line>
      </quote_lines>
      <tax_analysis>
        <ArtefactTaxAnalysis>
          <tax_rate>
            <legacy_id>1</legacy_id>
            <id>GB_STANDARD</id>
            <displayed_as>Standard 20.00%</displayed_as>
            <path>/tax_rates/GB_STANDARD</path>
            <created_at xsi:nil="true" />
            <updated_at xsi:nil="true" />
            <percentage xsi:nil="true" />
            <is_visible xsi:nil="true" />
            <is_combined_rate xsi:nil="true" />
            <editable xsi:nil="true" />
            <deletable xsi:nil="true" />
          </tax_rate>
          <net_amount>50</net_amount>
          <tax_amount>10</tax_amount>
          <total_amount>60</total_amount>
          <goods_amount>0</goods_amount>
          <service_amount>0</service_amount>
        </ArtefactTaxAnalysis>
      </tax_analysis>
      <withholding_tax_rate xsi:nil="true" />
      <withholding_tax_amount xsi:nil="true" />
      <base_currency_withholding_tax_amount xsi:nil="true" />
    </sales_quote>
  </sales_quotes>
</sage_one_company>
```