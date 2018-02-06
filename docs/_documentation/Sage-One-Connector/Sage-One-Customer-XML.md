---
slug: sage-one-customer-xml
title: Sage One Customer XML
---
The [Import Customers](uploading-customers-to-sage-one) task allows you to create new and update existing customer records in Sage One, using the XML format described below. Any Sage One fields not documented below are not supported with our import.   

A complete example of the XML is shown below. This represents the minimum information required to create a customer record in Sage One:

```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <customers>
    <customer>
      <name>Zynk Software</name>
    </customer>
  </customers>
</sage_one_company>
```

## Customer Identification
The following fields are use to identify the customer to create/update. At least one of these fields should be provided. If more than one is provided, Zynk will look for a match based on each field in turn, in the order they are listed below.

| Sage Field | XML Field | Example | Field Type | Input | Notes |
| --- | --- | --- | --- | --- | --- |
| Reference | reference | ZYNK0001 | string | Optional |  |
| - | id | 8a9b4b1f174c11e691e20a5d7cf84c3e | GUID | Optional | Sage's unique customer ID. |
| - | external_id | 1234567 | string  | Optional | The ID of the customer from the source data. |
| Company / Name | name | Zynk Software | string | Required |  |
| Main Contact > Email | main_contact_person/email | john.smith@example.com | string | Optional | Will only match against the main contact's email address |

```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <customers>
    <customer>
      <reference>ZYNK0001</reference>
      <id>8a9b4b1f174c11e691e20a5d7cf84c3e</id>
      <external_id>1234567</external_id>
      <name>Zynk Software</name>
      <main_contact_person>
        <email>john.smith@example.com</email>
      </main_contact_person>
    </customer>
  </customers>
</sage_one_company>
```

## Addresses
The address information below can be specified on the Contacts and Addresses tab in Sage. The main address has it's own specific element in the XML; `main_address`. All other addresses should go in the `addresses` collection.

| Sage Field | XML Field | Example | Field Type | Input | Notes |
| --- | --- | --- | --- | --- | --- |
| Main Address > Address Type | main_address/address_type_id | DELIVERY | string | Optional | Available values: DELIVERY, ACCOUNTS, SALES, PURCHASING |
| Main Address > Address Name | main_address/name | Main Address | string | Required |  |
| Main Address > Country Group | main_address/country_group/id | GBIE | string | Optional | Available values: ALL, CA, EU, GBIE, US. Will default to 'ALL' if not specified |
| Main Address > Address 1 | main_address/address_line_1 | Zynk Software | string | Optional |  |
| Main Address > Address 2 | main_address/address_line_2 | 6-8 Charlotte Square | string | Optional |  |
| Main Address > Town / City | main_address/city | Newcastle upon Type | string | Optional |  |
| Main Address > Province / State / County | main_address/region | Tyne &amp; Wear | string | Optional |  |
| Main Address > Postcode | main_address/postal_code | NE1 4XF | string | Optional |  |
| Main Address > Country | main_address/country/id | GB | string | Optional | Use the two letter ISO country code |
| - | main_address/is_main_address | true | boolean | Optional | Should be set to true |
| Address > Address Type | addresses/address/address_type_id | DELIVERY | string | Optional | Available values: DELIVERY, ACCOUNTS, SALES, PURCHASING |
| Address > Address Name | addresses/address/name | Alternative Address | string | Required | Used for matching existing addresses |
| Address > Country Group | addresses/address/country_group/id | GBIE | string | Optional | Available values: ALL, CA, EU, GBIE, US. Will default to 'ALL' if not specified |
| Address > Address 1 | addresses/address/address_line_1 | Nelson House | string | Optional |  |
| Address > Address 2 | addresses/address/address_line_2 | Fleming Business Centre | string | Optional |  |
| Address > Town / City | addresses/address/city | Jesmond | string | Optional |  |
| Address > Province / State / County | addresses/address/region | Tyne &amp; Wear | string | Optional |  |
| Address > Postcode | addresses/address/postal_code | NE2 3AE | string | Optional |  |
| Address > Country | addresses/address/country/id | GB | string | Optional | Use the two letter ISO country code |
| - | addresses/address/is_main_address | false | boolean | Optional | Should be set to false |

```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <customers>
    <customer>
      <main_address>
        <address_type_id>DELIVERY</address_type_id>
        <name>Main Address</name>
        <country_group>
          <id>GBIE</id>
        </country_group>
        <address_line_1>Zynk Software</address_line_1>
        <address_line_2>6-8 Charlotte Square</address_line_2>
        <city>Newcastle upon Type</city>
        <region>Tyne &amp; Wear</region>
        <postal_code>NE1 4XF</postal_code>
        <country>
          <id>GB</id>
        </country>
        <is_main_address>true</is_main_address>
      </main_address>
      <addresses>
        <address>
          <address_type>
            <id>DELIVERY</id>
          </address_type>
          <name>Alternative Address</name>
          <country_group>
            <id>GBIE</id>
          </country_group>
          <address_line_1>Nelson House</address_line_1>
          <address_line_2>Fleming Business Centre</address_line_2>
          <city>Jesmond</city>
          <region>Tyne &amp; Wear</region>
          <postal_code>NE2 3AE</postal_code>
          <country>
            <id>GB</id>
          </country>
          <is_main_address>false</is_main_address>
        </address>
      </addresses>
    </customer>
  </customers>
</sage_one_company>
```

## Contacts
The contact information below can be specified on the Contacts and Addresses tab in Sage. The main contact has it's own specific element in the XML; `main_contact_person`. All other contacts should go in the `contact_persons` collection.

| Sage Field | XML Field | Example | Field Type | Input | Notes |
| --- | --- | --- | --- | --- | --- |
| Main Contact > Name | main_contact_person/name | John Smith | string | Required |  |
| Main Contact > Role | main_contact_person/job_title | Accountant | string | Optional |  |
| Main Contact > Email | main_contact_person/email | john.smith@example.com | string | Optional |  |
| Main Contact > Telephone | main_contact_person/telephone | 0191 123 7279 | string | Optional |  |
| Main Contact > Mobile | main_contact_person/mobile | 07123456789 | string | Optional |  |
| Main Contact > Fax | main_contact_person/fax | 0123 456 7890 | string | Optional |  |
| - | main_contact_person/contact_person_types/contact_person_type/id | ACCOUNTS | string | Optional | Available values: ACCOUNTS, SALES, PURCHASING |
| Contact > Name | contact_persons/contact_person/name | Bill | string | Required |  |
| Contact > Role | contact_persons/contact_person/job_title | Account Manager | string | Optional |  |
| Contact > Email | contact_persons/contact_person/email | bill@example.com | string | Optional | Used for matching existing contacts |
| Contact > Telephone | contact_persons/contact_person/telephone | 0191 123 7279 | string | Optional |  |
| Contact > Mobile | contact_persons/contact_person/mobile | 07123456789 | string | Optional |  |
| Contact > Fax | contact_persons/contact_person/fax | 0123 456 7890 | string | Optional |  |
| Contact > Copy emails to this person | contact_persons/contact/contactable | true | boolean |  |  |
| - | contact_persons/contact/address/name | Main Address | string | Optional | Controls which address the contact is related to. Defaults to the main address if not specified |
| - | contact_persons/contact_person/contact_person_types/contact_person_type/id | ACCOUNTS | string | Optional | Available values: ACCOUNTS, SALES, PURCHASING |

```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <customers>
    <customer>
      <main_contact_person>
        <name>John Smith</name>
        <job_title>Accountant</job_title>
        <email>john.smith@example.com</email>
        <telephone>0191 123 7279</telephone>
        <mobile>07123456789</mobile>
        <fax>0123 456 7890</fax>
        <contact_person_types>
          <contact_person_type>
            <id>ACCOUNTS</id>
          </contact_person_type>
        </contact_person_types>
      </main_contact_person>
      <contact_persons>
        <contact_person>
          <name>Bill</name>
          <job_title>Account Manager</job_title>
          <email>bill@example.com</email>
          <telephone>0191 290 0614</telephone>
          <mobile>07123456789</mobile>
          <fax>0123 456 7890</fax>
          <contactable>true</contactable>
          <address>
            <name>Main Address</name>
          </address>
          <contact_person_types>
            <contact_person_type>
              <id>ACCOUNTS</id>
            </contact_person_type>
          </contact_person_types>
        </contact_person>
      </contact_persons>
    </customer>
  </customers>
</sage_one_company>
```

## Payment Details
The information below can be specified on the Payment Details tab in Sage.

| Sage Field | XML Field | Example | Field Type | Input | Notes |
| --- | --- | --- | --- | --- | --- |
| Currency | currency/id | GBP | string |  | Use the ISO currency code |
| Credit Limit | credit_limit | 1000 | double |  |  |
| Credit Terms | credit_days | 30 | int |  |  |
| Terms and Conditions | credit_terms_and_conditions | Payment due within 30 days | string |  |  |
| Account Name | bank_account_details/account_name | Barclays Connect | string |  |  |
| Sort Code | bank_account_details/sort_code | 112233 | string |  |  |
| Account Number | bank_account_details/account_number | 12345678 | string |  |  |
| BIC/Swift | bank_account_details/bic | MIDLGB22123 | string |  |  |
| IBAN | bank_account_details/iban | GB15 MIDL 4005 1512 3456 78 | string |  |  |

```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <customers>
    <customer>
      <currency>
        <id>GBP</id>
      </currency>
      <credit_limit>1000</credit_limit>
      <credit_days>30</credit_days>
      <credit_terms_and_conditions>Payment due within 30 days</credit_terms_and_conditions>
      <bank_account_details>
        <account_name>Barclays Connect</account_name>
        <sort_code>112233</sort_code>
        <account_number>12345678</account_number>
        <bic>MIDLGB22123</bic>
        <iban>GB15 MIDL 4005 1512 3456 78</iban>
      </bank_account_details>
    </customer>
  </customers>
</sage_one_company>
```

## Options
The information below can be specified on the options tab in Sage.

| Sage Field | XML Field | Example | Field Type | Input | Notes |
| --- | --- | --- | --- | --- | --- |
| Company / Name | name | Zynk Software | string | Required |  |
| Reference | reference | ZYNK0001 | string | Optional | Can be auto-generated, if enabled in the task settings |
| Price Default | product_sales_price_type/name | Optional |  |  |  |
| Account Default | default_sales_ledger_account/nominal_code | Optional |  |  |  |
| Account Default | default_sales_ledger_account/name | Optional |  |  | Only used if `nominal_code` is not specified |
| Account Default | default_sales_ledger_account/display_name | Optional |  |  | Only used if `nominal_code` and `name` are not specified |
| - | default_sales_tax_rate/id | GB_STANDARD | string | Optional |  |
| - | default_sales_tax_rate/name | Standard 20.00% | string | Optional | Only used if `id` is not specified |
| VAT Number | tax_number | GB12345678 | string | Optional |  |
| - | locale | en | string | Optional |  |

```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <customers>
    <customer>
      <name>Zynk Software</name>
      <reference>ZYNK0001</reference>
      <product_sales_price_type>
        <name>Sales Price</name>
      </product_sales_price_type>
      <default_sales_ledger_account>
        <nominal_code>4000</nominal_code>
        <name>Sales Type A</name>
        <display_name>Sales Type A (4000)</display_name>
      </default_sales_ledger_account>
      <default_sales_tax_rate>
        <id>GB_STANDARD</id>
        <name>Standard 20.00%</name>
      </default_sales_tax_rate>
      <tax_number>GB12345678</tax_number>
      <locale>en</locale>
    </customer>
  </customers>
</sage_one_company>
```

## Notes
The information below can be specified on the Notes tab in Sage.

| Sage Field | XML Field | Example | Field Type | Input | Notes |
| --- | --- | --- | --- | --- | --- |
| Notes | notes | This is a customer record. | string | Optional |  |

```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <customers>
    <customer>
      <notes>This is a customer record.</notes>
    </customer>
  </customers>
</sage_one_company>
```