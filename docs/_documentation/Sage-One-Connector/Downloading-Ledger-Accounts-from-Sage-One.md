---
slug: downloading-ledger-accounts-from-sage-one
redirect_from: "/article/852-download-ledger-accounts"
title: Downloading Ledger Accounts from Sage One
---
This task will download Ledger Accounts from your instance of Sage One.

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

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Example
A sample output file is shown below.
```xml
<?xml version="1.0"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <ledger_accounts>
    <ledger_account>
      <legacy_id>2654285</legacy_id>
      <id>d959c74d180811e691e20a5d7cf84c3e</id>
      <displayed_as>Sales Type A (4000)</displayed_as>
      <path>/ledger_accounts/d959c74d180811e691e20a5d7cf84c3e</path>
      <created_at>2015-06-22T08:33:54Z</created_at>
      <updated_at>2015-06-22T08:33:54Z</updated_at>
      <name>Sales Type A</name>
      <display_name>Sales Type A</display_name>
      <included_in_chart>true</included_in_chart>
      <nominal_code>4000</nominal_code>
      <ledger_account_type>
        <legacy_id>1</legacy_id>
        <id>SALES</id>
        <displayed_as>Sales</displayed_as>
        <path>/ledger_account_types/SALES</path>
      </ledger_account_type>
      <tax_rate>
        <legacy_id>1</legacy_id>
        <id>GB_STANDARD</id>
        <displayed_as>Standard 20.00%</displayed_as>
        <path>/tax_rates/GB_STANDARD</path>
      </tax_rate>
      <fixed_tax_rate>true</fixed_tax_rate>
      <visible_in_banking>false</visible_in_banking>
      <visible_in_expenses>false</visible_in_expenses>
      <visible_in_journals>true</visible_in_journals>
      <visible_in_other_payments>false</visible_in_other_payments>
      <visible_in_other_receipts>true</visible_in_other_receipts>
      <visible_in_reporting>true</visible_in_reporting>
      <visible_in_sales>true</visible_in_sales>
      <is_control_account>false</is_control_account>
    </ledger_account>
  </ledger_accounts>
</sage_one_company>
```