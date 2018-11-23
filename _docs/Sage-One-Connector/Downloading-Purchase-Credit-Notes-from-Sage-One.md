---
slug: downloading-purchase-credit-notes-from-sage-one
title: Downloading Purchase Credit Notes from Sage One
---
This task will download purchase credit notes from your instance of Sage One.

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
  <purchase_credit_notes>
    <purchase_credit_note>
      <legacy_id>14301462</legacy_id>
      <id>66e0b50a231a11e691e20a5d7cf84c3e</id>
      <displayed_as>54321</displayed_as>
      <path>/purchase_credit_notes/66e0b50a231a11e691e20a5d7cf84c3e</path>
      <transaction>
        <legacy_id>33474003</legacy_id>
        <id>66e4ced3231a11e691e20a5d7cf84c3e</id>
        <displayed_as>54321</displayed_as>
        <path>/transactions/66e4ced3231a11e691e20a5d7cf84c3e</path>
        <created_at xsi:nil="true" />
        <updated_at xsi:nil="true" />
        <deleted xsi:nil="true" />
        <total xsi:nil="true" />
      </transaction>
      <created_at>2016-05-26T08:18:18Z</created_at>
      <updated_at>2016-05-26T08:18:18Z</updated_at>
      <contact_name>The Jimi Hendrix Experience</contact_name>
      <contact_reference>HENDRI01</contact_reference>
      <contact>
        <legacy_id>8762276</legacy_id>
        <id>1531595a228f11e691e20a5d7cf84c3e</id>
        <displayed_as>The Jimi Hendrix Experience (HENDRI01)</displayed_as>
        <path>/contacts/1531595a228f11e691e20a5d7cf84c3e</path>
        <created_at xsi:nil="true" />
        <updated_at xsi:nil="true" />
        <credit_limit xsi:nil="true" />
        <credit_days xsi:nil="true" />
        <deletable xsi:nil="true" />
      </contact>
      <date>2016-05-26T00:00:00</date>
      <reference>54321</reference>
      <notes>Testing, testing, 1, 2, 3...</notes>
      <net_amount>20</net_amount>
      <tax_amount>4</tax_amount>
      <total_amount>24</total_amount>
      <outstanding_amount>0</outstanding_amount>
      <currency>
        <legacy_id>10</legacy_id>
        <id>GBP</id>
        <displayed_as>Pound Sterling (GBP)</displayed_as>
        <path>/currencies/GBP</path>
      </currency>
      <exchange_rate>1</exchange_rate>
      <base_currency_net_amount>20</base_currency_net_amount>
      <base_currency_tax_amount>4</base_currency_tax_amount>
      <base_currency_total_amount>24</base_currency_total_amount>
      <base_currency_outstanding_amount>0</base_currency_outstanding_amount>
      <status>
        <legacy_id>3</legacy_id>
        <id>PAID</id>
        <displayed_as>Paid</displayed_as>
        <path>/artefact_statuses/PAID</path>
      </status>
      <credit_note_lines>
        <credit_note_line>
          <legacy_id>16521511</legacy_id>
          <id>66eb10c9231a11e691e20a5d7cf84c3e</id>
          <displayed_as>Book of Spells.</displayed_as>
          <description>Book of Spells.</description>
          <product>
            <legacy_id>676809</legacy_id>
            <id>0dfbbb5d174611e691e20a5d7cf84c3e</id>
            <displayed_as>Book of Spells.</displayed_as>
            <path>/products/0dfbbb5d174611e691e20a5d7cf84c3e</path>
            <created_at xsi:nil="true" />
            <updated_at xsi:nil="true" />
            <deleted_at xsi:nil="true" />
            <active xsi:nil="true" />
            <cost_price xsi:nil="true" />
          </product>
          <ledger_account>
            <legacy_id>2654291</legacy_id>
            <id>d959cd0e180811e691e20a5d7cf84c3e</id>
            <displayed_as>Cost of sales - goods (5000)</displayed_as>
            <path>/ledger_accounts/d959cd0e180811e691e20a5d7cf84c3e</path>
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
          <unit_price>20</unit_price>
          <net_amount>20</net_amount>
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
          <tax_amount>4</tax_amount>
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
              <amount>4</amount>
            </tax>
          </tax_breakdown>
          <discount_amount xsi:nil="true" />
          <total_amount>24</total_amount>
          <base_currency_unit_price>20</base_currency_unit_price>
          <base_currency_net_amount>20</base_currency_net_amount>
          <base_currency_tax_amount>4</base_currency_tax_amount>
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
              <amount>4</amount>
            </tax>
          </base_currency_tax_breakdown>
          <base_currency_total_amount>24</base_currency_total_amount>
          <base_currency_discount_amount xsi:nil="true" />
        </credit_note_line>
      </credit_note_lines>
      <tax_analysis />
      <vendor_reference>12345</vendor_reference>
    </purchase_credit_note>
  </purchase_credit_notes>
</sage_one_company>
```