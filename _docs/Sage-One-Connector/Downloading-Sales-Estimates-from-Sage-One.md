---
slug: downloading-sales-estimates-from-sage-one
title: Downloading Sales Estimates from Sage One
---
This task will download sales estimates from your instance of Sage One.

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
  <sales_estimates>
    <sales_estimate>
      <legacy_id>84498297</legacy_id>
      <id>a2761c43d99a411f982584f810fa1466</id>
      <displayed_as>SE-3</displayed_as>
      <path>/sales_estimates/a2761c43d99a411f982584f810fa1466</path>
      <created_at>2018-11-23T14:54:00Z</created_at>
      <updated_at>2018-11-23T14:54:01Z</updated_at>
      <estimate_number>SE-3</estimate_number>
      <contact_name>Zynk Software</contact_name>
      <contact_reference>ZYNK0001</contact_reference>
      <contact>
        <legacy_id>31966735</legacy_id>
        <id>7e6a7104ad2611e8bad90617b3da4b8a</id>
        <displayed_as>Zynk Software (ZYNK0001)</displayed_as>
        <path>/contacts/7e6a7104ad2611e8bad90617b3da4b8a</path>
        <created_at xsi:nil="true" />
        <updated_at xsi:nil="true" />
        <credit_limit xsi:nil="true" />
        <credit_days xsi:nil="true" />
        <deletable xsi:nil="true" />
      </contact>
      <date>2018-11-23T00:00:00</date>
      <expiry_date>2018-12-23T00:00:00</expiry_date>
      <reference>5230</reference>
      <main_address_free_form>Zynk Software
6-8 Charlotte Square
Newcastle upon Type
Tyne &amp; Wear
NE1 4XF</main_address_free_form>
      <delivery_address_free_form>Zynk Software
6-8 Charlotte Square
Newcastle upon Type
Tyne &amp; Wear
NE1 4XF</delivery_address_free_form>
      <main_address>
        <legacy_id>55903055</legacy_id>
        <id>fe6d2824dea44d1494cfdd0fb5d5c737</id>
        <displayed_as>Zynk Software
6-8 Charlotte Square
Newcastle upon Type
Tyne &amp; Wear
NE1 4XF</displayed_as>
        <path>/contacts/fe6d2824dea44d1494cfdd0fb5d5c737</path>
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
        <city>Newcastle upon Type</city>
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
      <delivery_address>
        <legacy_id>55903056</legacy_id>
        <id>80938f175eae44dea13e5d3dddad1442</id>
        <displayed_as>Zynk Software
6-8 Charlotte Square
Newcastle upon Type
Tyne &amp; Wear
NE1 4XF</displayed_as>
        <path>/contacts/80938f175eae44dea13e5d3dddad1442</path>
        <created_at xsi:nil="true" />
        <updated_at xsi:nil="true" />
        <deleted_at xsi:nil="true" />
        <address_type>
          <legacy_id>1</legacy_id>
          <id>DELIVERY</id>
          <displayed_as>Delivery</displayed_as>
          <path>/address_types/DELIVERY</path>
        </address_type>
        <address_line_1>Zynk Software</address_line_1>
        <address_line_2>6-8 Charlotte Square</address_line_2>
        <city>Newcastle upon Type</city>
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
      </delivery_address>
      <notes />
      <terms_and_conditions />
      <shipping_net_amount>0</shipping_net_amount>
      <shipping_tax_rate>
        <percentage xsi:nil="true" />
        <amount xsi:nil="true" />
      </shipping_tax_rate>
      <shipping_tax_amount>0</shipping_tax_amount>
      <shipping_tax_breakdown />
      <shipping_total_amount>0</shipping_total_amount>
      <net_amount>5</net_amount>
      <tax_amount>1</tax_amount>
      <total_amount>6</total_amount>
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
      <base_currency_net_amount>5</base_currency_net_amount>
      <base_currency_tax_amount>1</base_currency_tax_amount>
      <base_currency_total_amount>6</base_currency_total_amount>
      <status>
        <id>PENDING</id>
        <displayed_as>Pending</displayed_as>
      </status>
      <estimate_lines>
        <estimate_line>
          <legacy_id>106023557</legacy_id>
          <id>30c713bed02247198aca4ec246a90164</id>
          <displayed_as>50 Colouring Pencils- Set</displayed_as>
          <description>50 Colouring Pencils- Set</description>
          <product>
            <legacy_id>4597716</legacy_id>
            <id>e9460b98e40311e7aa730a57719b2edb</id>
            <displayed_as>50 Colouring Pencils- Set</displayed_as>
            <path>/products/e9460b98e40311e7aa730a57719b2edb</path>
            <created_at xsi:nil="true" />
            <updated_at xsi:nil="true" />
            <deleted_at xsi:nil="true" />
            <active xsi:nil="true" />
            <cost_price xsi:nil="true" />
          </product>
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
          <unit_price>5</unit_price>
          <net_amount>5</net_amount>
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
          <tax_amount>1</tax_amount>
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
              <amount>1</amount>
            </tax>
          </tax_breakdown>
          <discount_amount>0</discount_amount>
          <total_amount>6</total_amount>
          <base_currency_unit_price>5</base_currency_unit_price>
          <base_currency_net_amount>5</base_currency_net_amount>
          <base_currency_tax_amount>1</base_currency_tax_amount>
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
              <amount>1</amount>
            </tax>
          </base_currency_tax_breakdown>
          <base_currency_total_amount>6</base_currency_total_amount>
          <base_currency_discount_amount>0</base_currency_discount_amount>
        </estimate_line>
      </estimate_lines>
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
          <net_amount>5</net_amount>
          <tax_amount>1</tax_amount>
          <total_amount>6</total_amount>
          <goods_amount>0</goods_amount>
          <service_amount>0</service_amount>
        </ArtefactTaxAnalysis>
      </tax_analysis>
      <withholding_tax_rate xsi:nil="true" />
      <withholding_tax_amount xsi:nil="true" />
      <base_currency_withholding_tax_amount xsi:nil="true" />
    </sales_estimate>
  </sales_estimates>
</sage_one_company>
```