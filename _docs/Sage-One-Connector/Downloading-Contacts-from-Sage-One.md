---
slug: downloading-contacts-from-sage-one
title: Downloading Contacts from Sage One
---
This task will download customer and vendor information from your instance of Sage One based on your settings. 

## Settings
### Sage One Connection
_Required_  
The connection to Sage One to use. See [Connecting to Sage One](connecting-to-sage-one) if you require more information on how to create/manage connections.

### Export Addresses
_Required_  
Set to true to export all addresses for the customers. When set to false, only the main address and delivery will be exported. 

### Export Contacts
_Required_  
Set to true to export all contacts associated with each address. When set to false, only the main contact will be exported. 

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
  <contacts>
    <contact>
      <legacy_id>2806942</legacy_id>
      <id>8841227f174c11e691e20a5d7cf84c3e</id>
      <displayed_as>HMRC Reclaimed (HMRC Rec)</displayed_as>
      <path>/contacts/8841227f174c11e691e20a5d7cf84c3e</path>
      <created_at>2015-06-22T08:36:23Z</created_at>
      <updated_at>2018-02-22T12:42:30Z</updated_at>
      <contact_types>
        <contact_type>
          <legacy_id>1</legacy_id>
          <id>CUSTOMER</id>
          <displayed_as>Customer</displayed_as>
          <path>/contact_types/CUSTOMER</path>
        </contact_type>
      </contact_types>
      <name>HMRC Reclaimed</name>
      <reference>HMRC Rec</reference>
      <default_sales_ledger_account>
        <legacy_id>2654289</legacy_id>
        <id>d959cb23180811e691e20a5d7cf84c3e</id>
        <displayed_as>Other income (4900)</displayed_as>
        <path>/ledger_accounts/d959cb23180811e691e20a5d7cf84c3e</path>
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
      </default_sales_ledger_account>
      <tax_number>GB123456789</tax_number>
      <main_address>
        <legacy_id>1559159</legacy_id>
        <id>992a7ffa174411e691e20a5d7cf84c3e</id>
        <displayed_as>test
test</displayed_as>
        <path>/addresses/992a7ffa174411e691e20a5d7cf84c3e</path>
        <created_at>2015-06-22T08:36:23Z</created_at>
        <updated_at>2017-10-12T16:20:47Z</updated_at>
        <deleted_at xsi:nil="true" />
        <contact>
          <legacy_id>2806942</legacy_id>
          <id>8841227f174c11e691e20a5d7cf84c3e</id>
          <displayed_as>HMRC Reclaimed (HMRC Rec)</displayed_as>
          <path>/contacts/8841227f174c11e691e20a5d7cf84c3e</path>
          <created_at xsi:nil="true" />
          <updated_at xsi:nil="true" />
          <credit_limit xsi:nil="true" />
          <credit_days xsi:nil="true" />
          <deletable xsi:nil="true" />
        </contact>
        <address_type>
          <legacy_id>1</legacy_id>
          <id>DELIVERY</id>
          <displayed_as>Delivery</displayed_as>
          <path>/address_types/DELIVERY</path>
        </address_type>
        <name>Main Address</name>
        <address_line_1>test</address_line_1>
        <address_line_2>test</address_line_2>
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
        <is_main_address>true</is_main_address>
      </main_address>
      <main_contact_person>
        <legacy_id>2806943</legacy_id>
        <id>884126aa174c11e691e20a5d7cf84c3e</id>
        <displayed_as>Main Contact</displayed_as>
        <path>/contact_persons/884126aa174c11e691e20a5d7cf84c3e</path>
        <created_at>2015-06-22T08:36:23Z</created_at>
        <updated_at>2015-06-22T08:36:23Z</updated_at>
        <deleted_at xsi:nil="true" />
        <contact_person_types>
          <contact_person_type>
            <legacy_id>4</legacy_id>
            <id>ACCOUNTS</id>
            <displayed_as>Accounts</displayed_as>
            <path>/contact_person_types/ACCOUNTS</path>
          </contact_person_type>
        </contact_person_types>
        <name>Main Contact</name>
        <is_main_contact>true</is_main_contact>
        <contactable xsi:nil="true" />
        <address>
          <legacy_id>1559159</legacy_id>
          <id>992a7ffa174411e691e20a5d7cf84c3e</id>
          <displayed_as>test
test</displayed_as>
          <path>/addresses/992a7ffa174411e691e20a5d7cf84c3e</path>
          <created_at xsi:nil="true" />
          <updated_at xsi:nil="true" />
          <deleted_at xsi:nil="true" />
          <is_main_address xsi:nil="true" />
        </address>
      </main_contact_person>
      <bank_account_details />
      <credit_limit xsi:nil="true" />
      <credit_days>30</credit_days>
      <product_sales_price_type>
        <legacy_id>1052119</legacy_id>
        <id>7a34bf52175011e691e20a5d7cf84c3e</id>
        <displayed_as>Wholesale</displayed_as>
        <path>/product_sales_price_types/7a34bf52175011e691e20a5d7cf84c3e</path>
        <created_at xsi:nil="true" />
        <updated_at xsi:nil="true" />
        <active xsi:nil="true" />
      </product_sales_price_type>
      <currency>
        <legacy_id>10</legacy_id>
        <id>GBP</id>
        <displayed_as>Pound Sterling (GBP)</displayed_as>
        <path>/currencies/GBP</path>
      </currency>
      <aux_reference />
      <deletable>false</deletable>
    </contact>
  </contacts>
</sage_one_company>
```