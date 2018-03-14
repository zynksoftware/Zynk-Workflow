---
slug: importing-customers-to-sage-200-online
redirect_from: "/article/importing-customers-to-sage-200-online"
title: Importing Customers To Sage 200 Online
---
This task will insert new and update existing customers in Sage 200 Online, using [Sage 200 Online Customer XML](sage-200-online-customer-xml) format.  Please note that it is only possible to create/update the default contact using this task.

## Settings
### Sage 200 Online Connection
_Required_  
The connection to Sage 200 Online to use. See the [Connecting to Sage 200 Online](connecting-to-sage-200-online) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
 The XML file to output any records to which fail to upload to Sage.

### Input File
_Required_  
The XML file containing the records to upload to Sage. See below for a sample input file.

### Success File
_Required_  
The XML file to output any records to which are successfully uploaded to Sage.

### Auto Generate References > Auto Generate Convention
_Required_  
Select a method for generating the alphabetic part of the account reference. The following options are available:

* __CompanyOtherwiseFullName__ - The company name will be used if provided, otherwise the customers full name.
* __CompanyOtherwiseForenameSurname__ - The company name will be used if provided, otherwise the customers forename followed by surname.
* __CompanyOtherwiseSurnameForename__ - The company name will be used if provided, otherwise the customers surname followed by forename.
* __ForenameSurname__ - The customers forename followed by surname.
* __SurnameForename__ - The customers surname followed by forename. 

### Auto Generate References - Alphabetic Length
_Required_  
Specify the number of alphabetic characters to use in the auto generated reference. E.g. 3 = ABC 

### Auto Generate References - Auto Generate Account References 
_Required_  
Set to True to have the task auto generate references where a reference is not provided in the input file. Set to False if automatic reference generation is not required. 

### Auto Generate References - Mask 
_Optional_  
A mask to apply to the auto generated references. This can be used to add prefixes or suffixes to the account references. Question marks are replaced by auto generated characters, as determined by the Alphabetic Length and Numeric Length settings, any other characters will be included in the generated account reference. For example, the mask `A??????` would ensure that the account references always start with the letter A.

### Auto Generate References - Numeric Length 
_Required_  
Specify the number of numeric characters to use in the auto generated reference. E.g. 3 = 001 

### Auto Generate References - Regular Expression 
_Optional_  
The regular expression to use for stripping out undesired characters from the generated reference. Any character which matches the regular expression will be removed. For example, `\s*` would be used to strip out all spaces. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
Sample input file:
```xml
<?xml version="1.0" encoding="utf-8"?>
<Customers xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customer>
    <id>14950</id>
    <external_id>1234</external_id>
    <reference>ZYNK0001</reference>
    <name>Zynk Software</name>
    <short_name>Zynk Sof</short_name>
    <on_hold>false</on_hold>
    <exchange_rate_type>ExchangeRateSingle</exchange_rate_type>
    <telephone_country_code />
    <telephone_area_code />
    <telephone_subscriber_number />
    <fax_country_code />
    <fax_area_code />
    <fax_subscriber_number />
    <website />
    <credit_limit>0.00</credit_limit>
    <vat_number />
    <duns_code />
    <analysis_code_1 />
    <analysis_code_2 />
    <analysis_code_3 />
    <analysis_code_4 />
    <analysis_code_5 />
    <currency>
      <currency_iso_code>
        <code>GBP</code>
      </currency_iso_code>
    </currency>
    <country_code>
      <code>GB</code>
    </country_code>
    <default_tax_code>
      <code>1</code>
    </default_tax_code>
    <main_address>
      <address_1>Nelson House</address_1>
      <address_2>Jesmond</address_2>
      <address_3 />
      <address_4 />
      <city>Newcastle</city>
      <county>Tyne & Wear</county>
      <postcode>NE2 3AE</postcode>
      <address_country_code_id>13</address_country_code_id>
    </main_address>
  </Customer>
</Customers>
```
