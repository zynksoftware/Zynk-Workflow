---
slug: downloading-bank-accounts-from-sage-one
redirect_from: "/article/849-download-bank-accounts"
title: Downloading Bank Accounts from Sage One
---
This task will download Bank Accounts from your instance of Sage One.

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
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <bank_accounts>
    <bank_account>
      <legacy_id>124211</legacy_id>
      <id>864bd308174511e691e20a5d7cf84c3e</id>
      <displayed_as>Current (1200)</displayed_as>
      <path>/bank_accounts/864bd308174511e691e20a5d7cf84c3e</path>
      <created_at>2015-06-22T08:33:53Z</created_at>
      <updated_at>2017-08-04T15:42:44Z</updated_at>
      <bank_account_details>
        <account_name>Current</account_name>
        <account_number>TEST01</account_number>
        <sort_code>404040</sort_code>
        <bic />
        <iban />
      </bank_account_details>
      <ledger_account>
        <legacy_id>2654253</legacy_id>
        <id>d959966a180811e691e20a5d7cf84c3e</id>
        <displayed_as>Current (1200)</displayed_as>
        <path>/ledger_accounts/d959966a180811e691e20a5d7cf84c3e</path>
      </ledger_account>
      <bank_account_type>
        <legacy_id>1</legacy_id>
        <id>CHECKING</id>
        <displayed_as>Current</displayed_as>
        <path>/bank_account_types/CHECKING</path>
      </bank_account_type>
      <balance>-179.54</balance>
      <main_address>
        <legacy_id>1559148</legacy_id>
        <id>992a3f64174411e691e20a5d7cf84c3e</id>
        <displayed_as>Test House
123 Test Road
Test
Testishire
NE30 2DR
United Kingdom</displayed_as>
        <path>/addresses/992a3f64174411e691e20a5d7cf84c3e</path>
        <created_at>2015-06-22T08:33:53Z</created_at>
        <updated_at>2016-05-24T13:55:44Z</updated_at>
        <deleted_at xsi:nil="true" />
        <bank_account>
          <legacy_id>124211</legacy_id>
          <id>864bd308174511e691e20a5d7cf84c3e</id>
          <displayed_as>Current (1200)</displayed_as>
          <path>/bank_accounts/864bd308174511e691e20a5d7cf84c3e</path>
        </bank_account>
        <address_type>
          <legacy_id>1</legacy_id>
          <id>DELIVERY</id>
          <displayed_as>Delivery</displayed_as>
          <path>/address_types/DELIVERY</path>
        </address_type>
        <name>Main Address</name>
        <address_line_1>Test House</address_line_1>
        <address_line_2>123 Test Road</address_line_2>
        <city>Test</city>
        <region>Testishire</region>
        <postal_code>NE30 2DR</postal_code>
        <country>
          <legacy_id>218</legacy_id>
          <id>GB</id>
          <displayed_as>United Kingdom (GB)</displayed_as>
          <path>/countries/GB</path>
        </country>
        <country_group>
          <legacy_id>1</legacy_id>
          <id>ALL</id>
          <displayed_as>Other</displayed_as>
          <path>/country_groups/ALL</path>
        </country_group>
        <is_main_address>true</is_main_address>
      </main_address>
      <main_contact_person>
        <name>Main Contact</name>
        <job_title />
        <telephone />
        <mobile />
        <email />
        <fax />
      </main_contact_person>
      <nominal_code xsi:nil="true" />
      <editable>true</editable>
      <deletable>false</deletable>
    </bank_account>
  </bank_accounts>
</sage_one_company>
```