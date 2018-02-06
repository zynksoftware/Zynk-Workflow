---
slug: downloading-purchase-invoices-from-sage-one
redirect_from: "/article/855-download-purchase-invoices"
title: Downloading Purchase Invoices from Sage One
---
This task will download Purchase Invoices from your instance of Sage One.

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
A sample output file is shown below. See [Sage One Purchase Invoice XML](sage-one-purchase-invoice-xml) for full documentation of the XML format.
```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <purchase_invoices>
    <purchase_invoice>
      <legacy_id>14277167</legacy_id>
      <id>2ba0c0c7228f11e691e20a5d7cf84c3e</id>
      <displayed_as>54321</displayed_as>
      <path>/purchase_invoices/2ba0c0c7228f11e691e20a5d7cf84c3e</path>
      <transaction>
        <legacy_id>33412588</legacy_id>
        <id>2ba45cfe228f11e691e20a5d7cf84c3e</id>
        <displayed_as>54321</displayed_as>
        <path>/transactions/2ba45cfe228f11e691e20a5d7cf84c3e</path>
      </transaction>
      <created_at>2016-05-25T15:41:38Z</created_at>
      <updated_at>2016-06-08T09:29:38Z</updated_at>
      <contact_name>The Jimi Hendrix Experience</contact_name>
      <contact_reference>HENDRI01</contact_reference>
      <contact>
        <legacy_id>8762276</legacy_id>
        <id>1531595a228f11e691e20a5d7cf84c3e</id>
        <displayed_as>The Jimi Hendrix Experience (HENDRI01)</displayed_as>
        <path>/contacts/1531595a228f11e691e20a5d7cf84c3e</path>
      </contact>
      <date>2016-05-25T00:00:00</date>
      <due_date>2016-06-24T00:00:00</due_date>
      <reference>54321</reference>
      <notes>Testing, testing, 1, 2, 3...</notes>
      <net_amount>400</net_amount>
      <tax_amount>80</tax_amount>
      <total_amount>480</total_amount>
      <total_paid>480</total_paid>
      <outstanding_amount>0</outstanding_amount>
      <total_quantity>20</total_quantity>
      <currency>
        <legacy_id>10</legacy_id>
        <id>GBP</id>
        <displayed_as>Pound Sterling (GBP)</displayed_as>
        <path>/currencies/GBP</path>
      </currency>
      <exchange_rate>1</exchange_rate>
      <inverse_exchange_rate>1</inverse_exchange_rate>
      <base_currency_net_amount>400</base_currency_net_amount>
      <base_currency_tax_amount>80</base_currency_tax_amount>
      <base_currency_total_amount>480</base_currency_total_amount>
      <base_currency_outstanding_amount>0</base_currency_outstanding_amount>
      <status>
        <legacy_id>3</legacy_id>
        <id>PAID</id>
        <displayed_as>Paid</displayed_as>
        <path>/artefact_statuses/PAID</path>
      </status>
      <invoice_lines>
        <invoice_line>
          <legacy_id>16484491</legacy_id>
          <id>2ba9d35f228f11e691e20a5d7cf84c3e</id>
          <displayed_as>Book of Spells.</displayed_as>
          <description>Book of Spells.</description>
          <product>
            <legacy_id>676809</legacy_id>
            <id>0dfbbb5d174611e691e20a5d7cf84c3e</id>
            <displayed_as>Book of Spells.</displayed_as>
            <path>/products/0dfbbb5d174611e691e20a5d7cf84c3e</path>
          </product>
          <ledger_account>
            <legacy_id>2654291</legacy_id>
            <id>d959cd0e180811e691e20a5d7cf84c3e</id>
            <displayed_as>Cost of sales - goods (5000)</displayed_as>
            <path>/ledger_accounts/d959cd0e180811e691e20a5d7cf84c3e</path>
          </ledger_account>
          <quantity>20</quantity>
          <unit_price>20</unit_price>
          <net_amount>400</net_amount>
          <tax_rate>
            <legacy_id>1</legacy_id>
            <id>GB_STANDARD</id>
            <displayed_as>Standard 20.00%</displayed_as>
            <path>/tax_rates/GB_STANDARD</path>
          </tax_rate>
          <tax_amount>80</tax_amount>
          <tax_breakdown>
            <tax>
              <tax_rate>
                <legacy_id>1</legacy_id>
                <id>GB_STANDARD</id>
                <displayed_as>Standard 20.00%</displayed_as>
                <path>/tax_rates/GB_STANDARD</path>
              </tax_rate>
              <percentage>20</percentage>
              <amount>80</amount>
            </tax>
          </tax_breakdown>
          <discount_amount xsi:nil="true" />
          <total_amount>480</total_amount>
          <base_currency_unit_price>20</base_currency_unit_price>
          <base_currency_net_amount>400</base_currency_net_amount>
          <base_currency_tax_amount>80</base_currency_tax_amount>
          <base_currency_tax_breakdown>
            <tax>
              <tax_rate>
                <legacy_id>1</legacy_id>
                <id>GB_STANDARD</id>
                <displayed_as>Standard 20.00%</displayed_as>
                <path>/tax_rates/GB_STANDARD</path>
              </tax_rate>
              <percentage>20</percentage>
              <amount>80</amount>
            </tax>
          </base_currency_tax_breakdown>
          <base_currency_total_amount>480</base_currency_total_amount>
          <base_currency_discount_amount xsi:nil="true" />
        </invoice_line>
      </invoice_lines>
      <tax_analysis />
      <withholding_tax_rate xsi:nil="true" />
      <withholding_tax_amount xsi:nil="true" />
      <base_currency_withholding_tax_amount xsi:nil="true" />
      <vendor_reference>12345</vendor_reference>
    </purchase_invoice>
  </purchase_invoices>
</sage_one_company>
```