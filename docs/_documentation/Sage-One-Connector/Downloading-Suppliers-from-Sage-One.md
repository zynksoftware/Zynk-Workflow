---
slug: downloading-suppliers-from-sage-one
redirect_from: "/article/858-download-suppliers"
title: Downloading Suppliers from Sage One
---
This task will download Suppliers from your instance of Sage One.

## Settings
### Sage One Connection
_Required_  
The connection to Sage One to use. See [Connecting to Sage One](connecting-to-sage-one) if you require more information on how to create/manage connections.

### Export Addresses
_Required_  
Set to true to export all addresses for the suppliers. When set to false, only the main address and delivery will be exported. 

### Export Contacts
_Required_  
Set to true to export all contacts for the suppliers. When set to false, only the main contact will be exported. 

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
A sample output file is shown below. See [Sage One Supplier XML](sage-one-supplier-xml) for full documentation of the XML format.
```xml
<?xml version="1.0"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <suppliers>
    <supplier>
      <legacy_id>9148392</legacy_id>
      <id>d87f394c321311e691e20a5d7cf84c3e</id>
      <external_id>479108</external_id>
      <displayed_as>The Smiths (SMIT0001)</displayed_as>
      <path>/contacts/d87f394c321311e691e20a5d7cf84c3e</path>
      <created_at>2016-06-14T09:39:09Z</created_at>
      <updated_at>2016-06-17T13:38:16Z</updated_at>
      <contact_types>
        <contact_type>
          <legacy_id>2</legacy_id>
          <id>VENDOR</id>
          <displayed_as>Supplier</displayed_as>
          <path>/contact_types/VENDOR</path>
        </contact_type>
      </contact_types>
      <name>The Smiths</name>
      <reference>SMIT0001</reference>
      <default_purchase_ledger_account>
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
      </default_purchase_ledger_account>
      <notes>Testing, testing, 1, 2, 3...</notes>
      <main_address>
        <legacy_id>5073257</legacy_id>
        <id>d880452e321311e691e20a5d7cf84c3e</id>
        <displayed_as>Charming Man House
123 Ask Road
Morrissey
Marrshire
NE29 2PQ</displayed_as>
        <path>/addresses/d880452e321311e691e20a5d7cf84c3e</path>
        <created_at>2016-06-14T09:39:09Z</created_at>
        <updated_at>2016-06-14T09:39:09Z</updated_at>
        <deleted_at xsi:nil="true" />
        <contact>
          <legacy_id>9148392</legacy_id>
          <id>d87f394c321311e691e20a5d7cf84c3e</id>
          <displayed_as>The Smiths (SMIT0001)</displayed_as>
          <path>/contacts/d87f394c321311e691e20a5d7cf84c3e</path>
        </contact>
        <address_type>
          <legacy_id>1</legacy_id>
          <id>DELIVERY</id>
          <displayed_as>Delivery</displayed_as>
          <path>/address_types/DELIVERY</path>
        </address_type>
        <name>Main Address</name>
        <address_line_1>Charming Man House</address_line_1>
        <address_line_2>123 Ask Road</address_line_2>
        <city>Morrissey</city>
        <region>Marrshire</region>
        <postal_code>NE29 2PQ</postal_code>
        <country_group>
          <legacy_id>1</legacy_id>
          <id>ALL</id>
          <displayed_as>Other</displayed_as>
          <path>/country_groups/ALL</path>
        </country_group>
        <is_main_address>true</is_main_address>
      </main_address>
      <main_contact_person>
        <legacy_id>9148393</legacy_id>
        <id>d881ad0c321311e691e20a5d7cf84c3e</id>
        <displayed_as>Johnny Marr</displayed_as>
        <path>/contact_persons/d881ad0c321311e691e20a5d7cf84c3e</path>
        <created_at>2016-06-14T09:39:09Z</created_at>
        <updated_at>2016-06-14T09:39:09Z</updated_at>
        <deleted_at xsi:nil="true" />
        <contact_person_types>
          <contact_person_type>
            <legacy_id>4</legacy_id>
            <id>ACCOUNTS</id>
            <displayed_as>Accounts</displayed_as>
            <path>/contact_person_types/ACCOUNTS</path>
          </contact_person_type>
        </contact_person_types>
        <name>Johnny Marr</name>
        <telephone>0191 290 0618</telephone>
        <email>johnny@thesmiths.co.uk</email>
        <is_main_contact>true</is_main_contact>
        <contactable xsi:nil="true" />
        <address>
          <legacy_id>5073257</legacy_id>
          <id>d880452e321311e691e20a5d7cf84c3e</id>
          <displayed_as>Charming Man House
123 Ask Road
Morrissey
Marrshire
NE29 2PQ</displayed_as>
          <path>/addresses/d880452e321311e691e20a5d7cf84c3e</path>
        </address>
      </main_contact_person>
      <bank_account_details />
      <credit_limit xsi:nil="true" />
      <credit_days xsi:nil="true" />
      <currency>
        <legacy_id>10</legacy_id>
        <id>GBP</id>
        <displayed_as>Pound Sterling (GBP)</displayed_as>
        <path>/currencies/GBP</path>
      </currency>
      <aux_reference />
      <deletable>true</deletable>
    </supplier>
  </suppliers>
</sage_one_company>
```