---
slug: sage-200-online-customer-xml
title: Sage 200 Online Customer XML
---
Customers are one of the most important entities within Sage 200 as they are associated with many important resources within the application and underpin most of the main features (e.g. sales orders, payment receipts, etc).  Further information can be found on the [Sage 200 Online Customers API Documentation](https://developer.columbus.sage.com/docs#/uk/sage200/accounts/v1/customers).

## Tasks
 * [Exporting Customers From Sage 200 Online](exporting-customers-from-sage-200-online)
 * [Importing Customers To Sage 200 Online](importing-customers-to-sage-200-online)

## Identifiers
The logic surrounding inserting/updating customers works as follows:
1. If an `<id>` is provided for the customer, the existing customer with this id will be updated.
2. If an `<external_id>` is provided for the customer, and a match is found in Zynk's truth table, the existing customer will be updated.
3. If a `<reference>` is provided for the customer, the task will check if a customer already exists with this reference. If a match is found, the existing customer will be updated, otherwise a new customer will be created and given the reference specified.
4. If none of the above conditions are fulfilled, and the 'Auto Generate References' setting is enabled on the task, a new customer will be created and given an automatically generated reference. 

### id
_Dependant_  
The `<id>` field is the unique internal database id of the customer.  This can be obtained from running a download of customers, or from the response of an upload.

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 27006 | `<id>27006</id>` |

### external_id
_Optional (recommended)_  
The `<external_id>` field is used within Zynk to match records already processed.  If it is provided Zynk will store the external_id along with the reference in its internal database.  

| Type | Example | XML |
| --- | --- | --- |
| string(255) | 12345 | `<external_id>12345</external_id>` |

### reference
_Dependant_  
The `<reference>` field is the customer account reference as shown with the Sage 200 Online interface.  This can either be generated automatically if the setting is enabled within Sage, or Zynk can generate one based on the settings setup on the task.

| Type | Example | XML |
| --- | --- | --- |
| string(8) | ZYNK001 | `<reference>ZYNK001</reference>` |

## Fields for Download and Upload
### name
_Required_  
Customer name.

| Type | Example | XML |
| --- | --- | --- |
| string(60) | Zynk Software Ltd. | `<name>Zynk Software Ltd.</name>` |

### short_name
_Optional_  
Customer short name.

| Type | Example | XML
| --- | --- | --- |
| string(8) | Zynk | `<short_name>Zynk</short_name>` |

### on_hold
_Optional_  
True if customer account is on hold, else False.

| Type | Example | XML
| --- | --- | --- |
| boolean | false | `<on_hold>false</on_hold>` |

#### Available Values
 * true
 * false

### account_status_type
_Optional_  
The status of the customer account.

| Type | Example | XML |
| --- | --- | --- |
| string(20) | AccountStatusActive | `<account_status_type>AccountStatusActive</account_status_type>` |

#### Available Values
 * AccountStatusActive
 * AccountStatusHidden

### currency_id
_Dependant (see [currency](#currency))_  
Currency record Id, can also be set using currency ISO code, see [currency](#currency).

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 3 | `<currency_id>3</currency_id>` |

### exchange_rate_type
_Optional_  
The type of exchange rate used on the customer account.

| Type | Example | XML |
| --- | --- | --- |
| string(20) | ExchangeRateSingle | `<exchange_rate_type>ExchangeRateSingle</exchange_rate_type>` |

#### Available Values
 * ExchangeRateSingle
 * ExchangeRatePeriod
 * ExchangeRateBoth

### telephone_country_code †
_Optional_  
Telephone country code.

| Type | Example | XML |
| --- | --- | --- |
| string(5) | +44 | `<telephone_country_code>+44</telephone_country_code>` |

### telephone_area_code †
_Optional_  
Telephone area code.

| Type | Example | XML |
| --- | --- | --- |
| string(20) | 191 | `<telephone_area_code>191</telephone_area_code>` |

### telephone_subscriber_number †
_Optional_  
Telephone subscriber number.

| Type | Example | XML |
| --- | --- | --- |
| string(200) | 303 7279 | `<telephone_subscriber_number>303 7279</telephone_subscriber_number>` |

### fax_country_code
_Optional_  
Fax country code.

| Type | Example | XML |
| --- | --- | --- |
| string(5) | +44 | `<fax_country_code>+44</fax_country_code>` |

### fax_area_code
_Optional_  
Fax area code.

| Type | Example | XML |
| --- | --- | --- |
| string(20) | 845| `<fax_area_code>845</fax_area_code>` |

### fax_subscriber_number
_Optional_  
Fax subscriber number.

| Type | Example | XML |
| --- | --- | --- |
| string(200) | 123 2920 | `<fax_subscriber_number>123 2920</fax_subscriber_number>` |

### website
_Optional_  
Website address.

| Type | Example | XML |
| --- | --- | --- |
| string(200) | http://zynk.com | `<website>http://zynk.com</website>` |

### credit_limit
_Optional_  
Credit limit for the customer.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 10000 | `<credit_limit>10000</credit_limit>` |

### country_code_id
_Dependant (see [country_code](#country_code))_  
Country code record Id, can also be set using country code, see [country_code](#country_code).

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 13 | `<country_code_id>13</country_code_id>` |

### default_tax_code_id
_Dependant (see [default_tax_code](#default_tax_code))_  
Default tax code record Id, can also be set using tax code, see [default_tax_code](#default_tax_code).

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 2 | `<default_tax_code_id>2</default_tax_code_id>` |

### vat_number
_Optional_  
VAT registration number.

| Type | Example | XML |
| --- | --- | --- |
| string(30) | 796 5763 59 | `<vat_number>796 5763 59</vat_number>` |

### duns_code
DUNS number.

| Type | Example | XML |
| --- | --- | --- |
| string(9) | 424458615 | `<duns_code>424458615</duns_code>` |

### analysis_code_1
_Optional_  
Analysis code 1.

| Type | Example | XML |
| --- | --- | --- |
| string(60) | North | `<analysis_code_1>North</analysis_code_1>` |

### analysis_code_2
_Optional_  
Analysis code 2.

| Type | Example | XML |
| --- | --- | --- |
| string(60) | Software | `<analysis_code_2>Software</analysis_code_2>` |

### analysis_code_3
_Optional_  
Analysis code 3.

| Type | Example | XML |
| --- | --- | --- |
| string(60) | 01/01/2005 | `<analysis_code_3>01/01/2005</analysis_code_3>` |

### analysis_code_4
_Optional_  
Analysis code 4.

| Type | Example | XML |
| --- | --- | --- |
| string(60) | 10 | `<analysis_code_4>10</analysis_code_4>` |

### analysis_code_5
_Optional_  
Analysis code 5.

| Type | Example | XML |
| --- | --- | --- |
| string(60) | true | `<analysis_code_5>true</analysis_code_5>` |

### main_address
_Optional_  
The customers main address.  The `<main_address>` node is an object which contains the address fields, all of following fields must be inside the node, see full example XML below.

#### address_1
_Optional_  
Address line 1.

| Type | Example | XML |
| --- | --- | --- |
| string(60) | i6 | `<address_1>i6</address_1>` |

#### address_2
_Optional_  
Address line 2.

| Type | Example | XML |
| --- | --- | --- |
| string(60) | 6 - 8 Charlotte Square | `<address_2>6 - 8 Charlotte Square</address_2>` |

#### address_3
_Optional_  
Address line 3.

| Type | Example | XML |
| --- | --- | --- |
| string(60) |  | `<address_3></address_3>` |

#### address_4
_Optional_  
Address line 4.

| Type | Example | XML |
| --- | --- | --- |
| string(60) |  | `<address_4></address_4>` |

#### city
_Optional_  
City.

| Type | Example | XML |
| --- | --- | --- |
| string(60) |  | `<city>Newcastle</city>` |

#### county
_Optional_  
County.

| Type | Example | XML |
| --- | --- | --- |
| string(60) | Tyne and Wear | `<county>Tyne and Wear</county>` |

#### postcode
_Optional_  
Postcode.

| Type | Example | XML |
| --- | --- | --- |
| string(10) | NE1 4XF | `<postcode>NE1 4XF</postcode>` |

#### address_country_code_id
_Dependant (see [address_country_code](#address_country_code))_  
Country code Id, can also be set using country code, see [address_country_code](#address_country_code).

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 13 | `<address_country_code_id>13</address_country_code_id>` |

#### address_country_code
_Dependant (see [address_country_code_id](#address_country_code_id))_  
The address country code. On a download all the related information of the address country code will be included in the XML, see [Sage 200 Online Country Code XML](sage-200-online-country-code-xml). On an upload you can set the code of the country to use for the address and Zynk will lookup the correct internal id from Sage.

##### Export example showing related information

```xml
<address_country_code>
    <id>13</id>
    <date_time_updated>2015-10-30T22:33:16.67</date_time_updated>
    <name>Great Britain</name>
    <code>GB</code>
    <eu_member>true</eu_member>
</address_country_code>
```

#### Import example only setting the code

```xml
<address_country_code>
    <code>GB</code>
</address_country_code>
```

### contacts
_Optional_  
Customer contacts.  Note Sage 200 Standard Online only supports a single collection, so whilst the contact is in a collection in the XML it is invalid for more than one to be provided.  Only the default contact will be updated using this task.  See [Sage 200 Online Contact XML](sage-200-online-contact-xml) for full details.

## Fields for Download Only
### balance
_Read Only_  
Customer account balance.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 1000 | `<balance>1000<balance/>` |

### date_time_updated
_Read Only_  
The date and time this entity was last updated (UTC).  This field is updated when a customer is uploaded using Zynk as well as when using the Sage 200 Online interface.

| Type | Example | XML
| --- | --- | --- |
| string(date-time) | 2017-06-02T08:19:00.147 | `<date_time_updated>2017-06-02T08:19:00.147</date_time_updated>` |

## Expandable Fields
Related information linked to customers are also included in the downloaded XML, these can also be used to set certain fields on customer uploads using lookups rather than needing to know the internal id of the related record.

### currency
_Dependant (see [currency_id](#currency_id))_  
The customers currency.  On a download all the related information of the currency will be included in the XML, see [Sage 200 Online Currency XML](sage-200-online-currency-xml).  On an upload you can set the code of the currency to use for the customer and Zynk will lookup the correct internal id from Sage.

#### Export example showing related information

```xml
<currency>
    <id>1</id>
    <date_time_updated>2016-07-08T09:28:40.9</date_time_updated>
    <symbol>£</symbol>
    <name>Pound Sterling</name>
    <core_currency_rate>1.000000</core_currency_rate>
    <euro_currency_rate>0.860000</euro_currency_rate>
    <currency_iso_code_id>49</currency_iso_code_id>
    <is_base_currency>true</is_base_currency>
    <is_euro_currency>false</is_euro_currency>
    <currency_iso_code>
        <id>49</id>
        <date_time_updated>2015-10-30T22:33:17.707</date_time_updated>
        <code>GBP</code>
        <name>UNITED KINGDOM, Pound Sterling</name>
    </currency_iso_code>
</currency>
```

#### Import example only setting the code
```xml
<currency>
    <currency_iso_code>
        <code>GBP</code>
    </currency_iso_code>
</currency>
```

### country_code
_Dependant (see [country_code_id](#country_code_id))_  
The customers country code.  On a download all the related information of the country code will be included in the XML, see [Sage 200 Online Country Code XML](sage-200-online-country-code-xml).  On an upload you can set the code of the country to use for the customer and Zynk will lookup the correct internal id from Sage.

#### Export example showing related information

```xml
<country_code>
    <id>13</id>
    <date_time_updated>2015-10-30T22:33:16.67</date_time_updated>
    <name>Great Britain</name>
    <code>GB</code>
    <eu_member>true</eu_member>
</country_code>
```

#### Import example only setting the code

```xml
<country_code>
    <code>GB</code>
</country_code>
```

### default_tax_code
_Dependant (see [default_tax_code_id](#default_tax_code_id))_  
The default tax code to be used in transactions for the customer.  On a download all the related information of the tax code will be included in the XML.  On an upload you can set the code of the tax rate to use for the customer and Zynk will lookup the correct internal id from Sage.

#### Export example showing related information

```xml
<default_tax_code>
    <id>2</id>
    <date_time_updated>2015-10-30T22:33:16.473</date_time_updated>
    <code>1</code>
    <name>Standard Rate</name>
    <tax_rate>20.00</tax_rate>
</default_tax_code>
```

#### Import example only setting the code

```xml
<default_tax_code>
    <code>1</code>
</default_tax_code>
```

## Example XML
### Minimal Example

```xml
<?xml version="1.0" encoding="utf-8"?>
<Customers 
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
    xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <Customer>
        <name>Zynk Software Ltd.</name>
    </Customer>
</Customers>
```

### Full Example
```xml
<?xml version="1.0" encoding="utf-8"?>
<Customers xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customer>
    <external_id>12345</external_id>
    <id>27006</id>
    <date_time_updated>2017-06-02T14:59:04.877</date_time_updated>
    <reference>ZYNK001</reference>
    <name>Zynk Software Ltd.</name>
    <short_name>Zynk</short_name>
    <balance>0.00</balance>
    <on_hold>false</on_hold>
    <account_status_type>AccountStatusActive</account_status_type>
    <currency_id>1</currency_id>
    <exchange_rate_type>ExchangeRateSingle</exchange_rate_type>
    <telephone_country_code>+44</telephone_country_code>
    <telephone_area_code>191</telephone_area_code>
    <telephone_subscriber_number>303 7279</telephone_subscriber_number>
    <fax_country_code>+44</fax_country_code>
    <fax_area_code>845</fax_area_code>
    <fax_subscriber_number>123 2920</fax_subscriber_number>
    <website>http://zynk.com</website>
    <credit_limit>10000.00</credit_limit>
    <country_code_id>13</country_code_id>
    <default_tax_code_id>2</default_tax_code_id>
    <vat_number>796 5763 59</vat_number>
    <analysis_code_1>North</analysis_code_1>
    <analysis_code_2>Software</analysis_code_2>
    <analysis_code_3>01/01/2005</analysis_code_3>
    <analysis_code_4>10</analysis_code_4>
    <analysis_code_5>true</analysis_code_5>
    <country_code>
      <id>13</id>
      <date_time_updated>2015-10-30T22:33:16.67</date_time_updated>
      <name>Great Britain</name>
      <code>GB</code>
      <eu_member>true</eu_member>
    </country_code>
    <currency>
      <id>1</id>
      <date_time_updated>2016-07-08T09:28:40.9</date_time_updated>
      <symbol>£</symbol>
      <name>Pound Sterling</name>
      <core_currency_rate>1.000000</core_currency_rate>
      <euro_currency_rate>0.860000</euro_currency_rate>
      <currency_iso_code_id>49</currency_iso_code_id>
      <is_base_currency>true</is_base_currency>
      <is_euro_currency>false</is_euro_currency>
      <currency_iso_code>
        <id>49</id>
        <date_time_updated>2015-10-30T22:33:17.707</date_time_updated>
        <code>GBP</code>
        <name>UNITED KINGDOM, Pound Sterling</name>
      </currency_iso_code>
    </currency>
    <default_tax_code>
      <id>2</id>
      <date_time_updated>2015-10-30T22:33:16.473</date_time_updated>
      <code>1</code>
      <name>Standard Rate</name>
      <tax_rate>20.00</tax_rate>
    </default_tax_code>
    <main_address>
      <id>27007</id>
      <date_time_updated>2017-06-02T11:36:13.097</date_time_updated>
      <address_1>i6</address_1>
      <address_2>6 - 8 Charlotte Square</address_2>
      <address_3 />
      <address_4 />
      <city>Newcastle</city>
      <county>Tyne and Wear</county>
      <postcode>NE1 4XF</postcode>
      <address_country_code_id>13</address_country_code_id>
      <address_country_code>
        <id>13</id>
        <date_time_updated>2015-10-30T22:33:16.67</date_time_updated>
        <name>Great Britain</name>
        <code>GB</code>
        <eu_member>true</eu_member>
      </address_country_code>
      <customer_id>27006</customer_id>
    </main_address>
    <contacts>
      <contact>
        <id>27008</id>
        <salutation_id>1</salutation_id>
        <name>Mr. Andrew Bryan Snape</name>
        <first_name>Andrew</first_name>
        <middle_name>Bryan</middle_name>
        <last_name>Snape</last_name>
        <is_default>true</is_default>
        <default_telephone>+44 191 303 7279</default_telephone>
        <default_email>support@zynk.com</default_email>
        <salutation>
          <id>1</id>
          <date_time_updated>2015-10-30T22:33:25.81</date_time_updated>
          <code>Mr.</code>
          <description>Mr.</description>
          <is_default>false</is_default>
        </salutation>
        <date_time_updated>2017-06-02T14:59:04.893</date_time_updated>
        <customer_id>27006</customer_id>
      </contact>
    </contacts>
    <duns_code>424458615</duns_code>
  </Customer>
</Customers>
```

***
† Available with Sage 200 Extra Online only.