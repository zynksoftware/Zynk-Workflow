---
slug: downloading-customers-from-sage-one
redirect_from: "/article/851-download-customers"
title: Downloading Customers from Sage One
---
This task will download customer information from your instance of Sage One based on your settings. 

## Settings
### Sage One Connection
_Required_  
The connection to Sage One to use. See [Connecting to Sage One](connecting-to-sage-one) if you require more information on how to create/manage connections.

### Export Addresses
_Required_  
Set to true to export all addresses for the customers. When set to false, only the main address and delivery will be exported. 

### Export Contacts
_Required_  
Set to true to export all contacts for the customers. When set to false, only the main contact will be exported. 

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
A sample output file is shown below. See [Sage One Customer XML](sage-one-customer-xml) for full documentation of the XML format.
```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <customers>
    <customer>
      <legacy_id>22221513</legacy_id>
      <id>d7d2f5bbcad911e797950a57719b2edb</id>
      <external_id>12345</external_id>
      <displayed_as>Zynk Software (ZYNK0001)</displayed_as>
      <path>/contacts/d7d2f5bbcad911e797950a57719b2edb</path>
      <created_at>2017-11-16T14:24:23Z</created_at>
      <updated_at>2017-11-16T16:41:48Z</updated_at>
      <contact_types>
        <contact_type>
          <legacy_id>1</legacy_id>
          <id>CUSTOMER</id>
          <displayed_as>Customer</displayed_as>
          <path>/contact_types/CUSTOMER</path>
        </contact_type>
      </contact_types>
      <name>Zynk Software</name>
      <reference>ZYNK0001</reference>
      <default_sales_ledger_account>
        <legacy_id>2654289</legacy_id>
        <id>d959cb23180811e691e20a5d7cf84c3e</id>
        <displayed_as>Other income (4900)</displayed_as>
        <path>/ledger_accounts/d959cb23180811e691e20a5d7cf84c3e</path>
      </default_sales_ledger_account>
      <notes>Testing, testing, 1, 2, 3...</notes>
      <locale>en</locale>
      <main_address>
        <legacy_id>26321253</legacy_id>
        <id>d7d6cf2ccad911e797950a57719b2edb</id>
        <displayed_as>i6 Charlotte Square
Newcastle
Tyne &amp; Wear
NE1 4XF</displayed_as>
        <path>/addresses/d7d6cf2ccad911e797950a57719b2edb</path>
        <created_at>2017-11-16T14:24:23Z</created_at>
        <updated_at>2017-11-16T14:24:23Z</updated_at>
        <deleted_at xsi:nil="true" />
        <contact>
          <legacy_id>22221513</legacy_id>
          <id>d7d2f5bbcad911e797950a57719b2edb</id>
          <displayed_as>Zynk Software (ZYNK0001)</displayed_as>
          <path>/contacts/d7d2f5bbcad911e797950a57719b2edb</path>
        </contact>
        <address_type>
          <legacy_id>1</legacy_id>
          <id>DELIVERY</id>
          <displayed_as>Delivery</displayed_as>
          <path>/address_types/DELIVERY</path>
        </address_type>
        <name>Main Address</name>
        <address_line_1>i6 Charlotte Square</address_line_1>
        <city>Newcastle</city>
        <region>Tyne &amp; Wear</region>
        <postal_code>NE1 4XF</postal_code>
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
      <delivery_address>
        <legacy_id>26321254</legacy_id>
        <id>d7da95f3cad911e797950a57719b2edb</id>
        <displayed_as>i6
Charlotte Square
Newcastle
Tyne &amp; Wear
NE1 4XF</displayed_as>
        <path>/addresses/d7da95f3cad911e797950a57719b2edb</path>
        <created_at>2017-11-16T14:24:23Z</created_at>
        <updated_at>2017-11-16T14:47:28Z</updated_at>
        <deleted_at xsi:nil="true" />
        <contact>
          <legacy_id>22221513</legacy_id>
          <id>d7d2f5bbcad911e797950a57719b2edb</id>
          <displayed_as>Zynk Software (ZYNK0001)</displayed_as>
          <path>/contacts/d7d2f5bbcad911e797950a57719b2edb</path>
        </contact>
        <address_type>
          <legacy_id>1</legacy_id>
          <id>DELIVERY</id>
          <displayed_as>Delivery</displayed_as>
          <path>/address_types/DELIVERY</path>
        </address_type>
        <name>Delivery Address</name>
        <address_line_1>i6</address_line_1>
        <address_line_2>Charlotte Square</address_line_2>
        <city>Newcastle</city>
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
        <is_main_address>false</is_main_address>
      </delivery_address>
      <main_contact_person>
        <legacy_id>22221514</legacy_id>
        <id>d7d92feacad911e797950a57719b2edb</id>
        <displayed_as>John Smith</displayed_as>
        <path>/contact_persons/d7d92feacad911e797950a57719b2edb</path>
        <created_at>2017-11-16T14:24:23Z</created_at>
        <updated_at>2017-11-16T14:24:23Z</updated_at>
        <deleted_at xsi:nil="true" />
        <contact_person_types>
          <contact_person_type>
            <legacy_id>4</legacy_id>
            <id>ACCOUNTS</id>
            <displayed_as>Accounts</displayed_as>
            <path>/contact_person_types/ACCOUNTS</path>
          </contact_person_type>
        </contact_person_types>
        <name>John Smith</name>
        <telephone>0191 290 0614</telephone>
        <email>support@zynk.com</email>
        <is_main_contact>true</is_main_contact>
        <contactable xsi:nil="true" />
        <address>
          <legacy_id>26321253</legacy_id>
          <id>d7d6cf2ccad911e797950a57719b2edb</id>
          <displayed_as>i6 Charlotte Square
Newcastle
Tyne &amp; Wear
NE1 4XF</displayed_as>
          <path>/addresses/d7d6cf2ccad911e797950a57719b2edb</path>
        </address>
      </main_contact_person>
      <bank_account_details />
      <credit_limit xsi:nil="true" />
      <credit_days xsi:nil="true" />
      <product_sales_price_type>
        <legacy_id>1052117</legacy_id>
        <id>7a34ae55175011e691e20a5d7cf84c3e</id>
        <displayed_as>Sales Price</displayed_as>
        <path>/product_sales_price_types/7a34ae55175011e691e20a5d7cf84c3e</path>
      </product_sales_price_type>
      <currency>
        <legacy_id>10</legacy_id>
        <id>GBP</id>
        <displayed_as>Pound Sterling (GBP)</displayed_as>
        <path>/currencies/GBP</path>
      </currency>
      <aux_reference />
      <deletable>true</deletable>
      <addresses>
        <address>
          <legacy_id xsi:nil="true" />
          <id>d7d6cf2ccad911e797950a57719b2edb</id>
          <displayed_as>i6 Charlotte Square
Newcastle
Tyne &amp; Wear
NE1 4XF</displayed_as>
          <path>/addresses/d7d6cf2ccad911e797950a57719b2edb</path>
          <created_at>2017-11-16T14:24:23Z</created_at>
          <updated_at>2017-11-16T14:24:23Z</updated_at>
          <deleted_at xsi:nil="true" />
          <contact>
            <legacy_id xsi:nil="true" />
            <id>d7d2f5bbcad911e797950a57719b2edb</id>
            <displayed_as>Zynk Software (ZYNK0001)</displayed_as>
            <path>/contacts/d7d2f5bbcad911e797950a57719b2edb</path>
          </contact>
          <address_type>
            <legacy_id xsi:nil="true" />
            <id>DELIVERY</id>
            <displayed_as>Delivery</displayed_as>
            <path>/address_types/DELIVERY</path>
          </address_type>
          <name>Main Address</name>
          <address_line_1>i6 Charlotte Square</address_line_1>
          <city>Newcastle</city>
          <region>Tyne &amp; Wear</region>
          <postal_code>NE1 4XF</postal_code>
          <country>
            <legacy_id xsi:nil="true" />
            <id>GB</id>
            <displayed_as>United Kingdom (GB)</displayed_as>
            <path>/countries/GB</path>
          </country>
          <country_group>
            <legacy_id xsi:nil="true" />
            <id>ALL</id>
            <displayed_as>Other</displayed_as>
            <path>/country_groups/ALL</path>
          </country_group>
          <is_main_address>true</is_main_address>
        </address>
        <address>
          <legacy_id xsi:nil="true" />
          <id>d7da95f3cad911e797950a57719b2edb</id>
          <displayed_as>i6
Charlotte Square
Newcastle
Tyne &amp; Wear
NE1 4XF</displayed_as>
          <path>/addresses/d7da95f3cad911e797950a57719b2edb</path>
          <created_at>2017-11-16T14:24:23Z</created_at>
          <updated_at>2017-11-16T14:47:28Z</updated_at>
          <deleted_at xsi:nil="true" />
          <contact>
            <legacy_id xsi:nil="true" />
            <id>d7d2f5bbcad911e797950a57719b2edb</id>
            <displayed_as>Zynk Software (ZYNK0001)</displayed_as>
            <path>/contacts/d7d2f5bbcad911e797950a57719b2edb</path>
          </contact>
          <address_type>
            <legacy_id xsi:nil="true" />
            <id>DELIVERY</id>
            <displayed_as>Delivery</displayed_as>
            <path>/address_types/DELIVERY</path>
          </address_type>
          <name>Delivery Address</name>
          <address_line_1>i6</address_line_1>
          <address_line_2>Charlotte Square</address_line_2>
          <city>Newcastle</city>
          <region>Tyne &amp; Wear</region>
          <postal_code>NE1 4XF</postal_code>
          <country>
            <legacy_id xsi:nil="true" />
            <id>GB</id>
            <displayed_as>United Kingdom (GB)</displayed_as>
            <path>/countries/GB</path>
          </country>
          <country_group>
            <legacy_id xsi:nil="true" />
            <id>GBIE</id>
            <displayed_as>UK &amp; Ireland</displayed_as>
            <path>/country_groups/GBIE</path>
          </country_group>
          <is_main_address>false</is_main_address>
        </address>
        <address>
          <legacy_id xsi:nil="true" />
          <id>11da2f81cadd11e797950a57719b2edb</id>
          <displayed_as>Starman House
123 Ziggy Street
Bowietown
Bowieshire
NE1 2DE</displayed_as>
          <path>/addresses/11da2f81cadd11e797950a57719b2edb</path>
          <created_at>2017-11-16T14:47:29Z</created_at>
          <updated_at>2017-11-16T16:41:48Z</updated_at>
          <deleted_at xsi:nil="true" />
          <contact>
            <legacy_id xsi:nil="true" />
            <id>d7d2f5bbcad911e797950a57719b2edb</id>
            <displayed_as>Zynk Software (ZYNK0001)</displayed_as>
            <path>/contacts/d7d2f5bbcad911e797950a57719b2edb</path>
          </contact>
          <address_type>
            <legacy_id xsi:nil="true" />
            <id>DELIVERY</id>
            <displayed_as>Delivery</displayed_as>
            <path>/address_types/DELIVERY</path>
          </address_type>
          <name>Another Address</name>
          <address_line_1>Starman House</address_line_1>
          <address_line_2>123 Ziggy Street</address_line_2>
          <city>Bowietown</city>
          <region>Bowieshire</region>
          <postal_code>NE1 2DE</postal_code>
          <country>
            <legacy_id xsi:nil="true" />
            <id>GB</id>
            <displayed_as>United Kingdom (GB)</displayed_as>
            <path>/countries/GB</path>
          </country>
          <country_group>
            <legacy_id xsi:nil="true" />
            <id>GBIE</id>
            <displayed_as>UK &amp; Ireland</displayed_as>
            <path>/country_groups/GBIE</path>
          </country_group>
          <is_main_address>false</is_main_address>
        </address>
      </addresses>
      <contact_persons>
        <contact_person>
          <legacy_id xsi:nil="true" />
          <id>d7d92feacad911e797950a57719b2edb</id>
          <displayed_as>John Smith</displayed_as>
          <path>/contact_persons/d7d92feacad911e797950a57719b2edb</path>
          <created_at>2017-11-16T14:24:23Z</created_at>
          <updated_at>2017-11-16T14:24:23Z</updated_at>
          <deleted_at xsi:nil="true" />
          <contact_person_types>
            <contact_person_type>
              <legacy_id xsi:nil="true" />
              <id>ACCOUNTS</id>
              <displayed_as>Accounts</displayed_as>
              <path>/contact_person_types/ACCOUNTS</path>
            </contact_person_type>
          </contact_person_types>
          <name>John Smith</name>
          <telephone>0191 290 0614</telephone>
          <email>support@zynk.com</email>
          <is_main_contact>true</is_main_contact>
          <contactable xsi:nil="true" />
          <address>
            <legacy_id xsi:nil="true" />
            <id>d7d6cf2ccad911e797950a57719b2edb</id>
            <displayed_as>i6 Charlotte Square
Newcastle
Tyne &amp; Wear
NE1 4XF</displayed_as>
            <path>/addresses/d7d6cf2ccad911e797950a57719b2edb</path>
          </address>
        </contact_person>
        <contact_person>
          <legacy_id xsi:nil="true" />
          <id>3062ebb4caea11e797950a57719b2edb</id>
          <displayed_as>Bill</displayed_as>
          <path>/contact_persons/3062ebb4caea11e797950a57719b2edb</path>
          <created_at>2017-11-16T16:21:24Z</created_at>
          <updated_at>2017-11-16T16:41:48Z</updated_at>
          <deleted_at xsi:nil="true" />
          <contact_person_types>
            <contact_person_type>
              <legacy_id xsi:nil="true" />
              <id>ACCOUNTS</id>
              <displayed_as>Accounts</displayed_as>
              <path>/contact_person_types/ACCOUNTS</path>
            </contact_person_type>
          </contact_person_types>
          <name>Bill</name>
          <telephone>0191 290 0614</telephone>
          <email>bill@example.com</email>
          <is_main_contact>false</is_main_contact>
          <contactable xsi:nil="true" />
          <address>
            <legacy_id xsi:nil="true" />
            <id>d7d6cf2ccad911e797950a57719b2edb</id>
            <displayed_as>i6 Charlotte Square
Newcastle
Tyne &amp; Wear
NE1 4XF</displayed_as>
            <path>/addresses/d7d6cf2ccad911e797950a57719b2edb</path>
          </address>
        </contact_person>
      </contact_persons>
    </customer>
  </customers>
</sage_one_company>
```