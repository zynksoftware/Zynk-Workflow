---
slug: act-company-xml
title: ACT! Company XML
---
Import Companies allows you to create new and update existing Companies in ACT!. 

Any ACT! fields not documented below are not explicitly supported with our imports, however, due to ACT! records being highly customisable, we do allow for a custom field collection to be imported with each record, this technique can technically be used to import standard ACT! fields that are not supported by our standard import. (See the 'Custom Fields' section below)

Sample file for importing/updating a Company:

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>
      <Id>1</Id>
      <CompanyName>Zynk Software Limited</CompanyName>
      <CustomerInvoiceAddress>
        <Address1>Nelson House, Fleming Business Centre</Address1>
        <Address2>Jesmond</Address2>
        <Address3 />
        <Town>Newcastle upon Tyne</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne &amp; Wear</County>
        <Country>GB</Country>
        <Notes />
        <CustomFields />
        <Activities />
        <Groups />
      </CustomerInvoiceAddress>
      <Contacts />
      <CustomFields />
    </Customer>   
  </Customers>
</Company>
```

In each of the following sections, most of the XML has been omitted to make the samples easier to read. The whole structure of the Zynk XML Company schema is used below, as a reference of where fields should be in the object model.

## Identifying Fields
The Id field should be populated by the unique id of the company/customer from the external system (actual type depends on the system being integrated), Zynk uses this field to track Companies already imported into ACT!. The UniqueId (actual ACT! ID) of the record can be specified if this is known. We would typically advise to always populate the Id. If it is possible to customise the external system to support storing the ACT! ID, then the integration could be structured to always download the Id, the UniqueId (if populated on the website) and then to notify the external system of any successfully imported ACT! Companies so that their ID's can be stored.

| ACT! Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| N/A | Id | 1 | string | 100 | Optional | Required if UniqueId not specified. |
| ID | UniqueId | f1d5bf65-6af4-4152-ad28-10adacddaa84 | Guid | 36 | Optional | Required if Id not specified. Must be a valid GUID. Will fail if specified UniqueId cannot be found in ACT! ACT! field not visible from the ACT! UI by default. |

```xml
<?xml version="1.0"?>
<Company>
  <Customers>
    <Customer>
      <Id>1</Id>
      <UniqueId>f1d5bf65-6af4-4152-ad28-10adacddaa84</UniqueId>
    </Customer>
  </Customers>
</Company>
```

## Business Card

| ACT! Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Company | CompanyName | Zynk Software Limited | string | 128 | Required | Blank or white space only Company name is not allowed in ACT!. If the Company already exists in ACT! and a blank company name is provided then the Company name will not be updated, and an Error node (titled 'Import Warning') will be present against the XML record in the success file. We will attempt to import the rest of the fields as normal. If the Company does not already exist in ACT! then the Company will not be imported and an Error node will be present against the XML record in the fail file.    |

```xml
<?xml version="1.0"?>
<Company>
  <Customers>
    <Customer>
      <CompanyName>Zynk Software Limited</CompanyName>
    </Customer>
  </Customers>
</Company>
```

## Address

| ACT! Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Address 1 | Address1 | Nelson House, Fleming Business Centre | string | 256 | Optional |
| Address 2 | Address2 | Jesmond | string | 256 | Optional |
| City | Town | Newcastle upon Tyne | string | 256 | Optional |
| County | County | Tyne &amp; Wear | string | 256 | Optional |
| Post | Postcode | NE2 3AE | string | 256 | Optional |
| Country | Country | GB | string | 256 | Optional | The ISO2 Country code should be used as opposed to the Country name. |

```xml
<?xml version="1.0"?>
<Company>
  <Customers>
    <Customer>
      <CustomerInvoiceAddress>
        <Address1>Nelson House, Fleming Business Centre</Address1>
        <Address2>Jesmond</Address2>
        <Town>Newcastle upon Tyne</Town>
        <County>Tyne &amp; Wear</County>
        <Postcode>NE2 3AE</Postcode>
        <Country>GB</Country>
      </CustomerInvoiceAddress>
      <Contacts />
      <CustomFields />
    </Customer>   
  </Customers>
</Company>
```

## Custom Fields
_If there is any additional logic tied in with the setting of the ACT! field, we cannot guarantee that this will be fulfilled._  

If a custom field fails to import, an Error node (titled 'Import Warning') will be present against the XML record in either the success or the fail file (depending on the outcome of the record import). We will attempt to import the rest of the fields as normal.

| ACT! Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Field Name | Name | Web Site | string | 64 | Required | The field name to use within the XML can normally be identified by finding the field within the Tools -> Define Fields list in ACT! (ensuring you are looking at the correct record type i.e. Companies) |
| Field Value | Value | http://www.zynk.com | Depends on the field being set | Depends on the field being set | Depends on the field being set | The value that you would like to try and set the ACT! field to. If the field being imported to is of a specified type in ACT! _e.g. a Yes/No field in ACT! must be given a value of True, true, False or false._ |

```xml
<?xml version="1.0"?>
<Company>
  <Customers>
    <Customer>      
      <CustomFields>
        <CustomField>
    <Name>Web Site</Name>
          <Value>http://www.zynk.com</Value>
  </CustomField>
      </CustomFields>
    </Customer>   
  </Customers>
</Company>
```

## Contacts
By providing nested contacts in the XML on a Company import, the ACT! Company information will be created/updated and then each of the provided Contacts will be created/updated. Once imported, the ACT! Contacts will be linked to the parent Company that they were imported with and vice versa. This does mean that if you provide the Contact Id or UniqueId of an existing Contact record with a different parent Company, the ACT! Contact will be re-linked to the new Company.  

If a child Contact fails to import, an Error node (titled 'Import Warning') will be present against the Contact XML record in either the success or the fail file (depending on the outcome of the parent Company import).  

Sample file for importing/updating a Company with a nested Contact

```xml
<?xml version="1.0"?>
<Company 
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
    xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <Customers>
        <Customer>
            <Id>1</Id>
            <CompanyName>Zynk Software Limited</CompanyName>
            <CustomerInvoiceAddress>
                <Address1>Nelson House, Fleming Business Centre</Address1>
                <Address2>Jesmond</Address2>
                <Address3 />
                <Town>Newcastle upon Tyne</Town>
                <Postcode>NE2 3AE</Postcode>
                <County>Tyne and Wear</County>
                <Country>GB</Country>
                <Notes />
                <CustomFields />
                <Activities />
                <Groups />
            </CustomerInvoiceAddress>
            <Contacts>
                <Contact>
                    <Id>1</Id>
                    <Title>Mr</Title>
                    <Forename>Chris</Forename>
                    <Middlename>Michael</Middlename>
                    <Surname>Hotchkiss</Surname>
                    <Suffix>Jr.</Suffix>
                    <Address1>Nelson House, Fleming Business Centre</Address1>
                    <Address2>Jesmond</Address2>
                    <Town>Newcastle upon Tyne</Town>
                    <Postcode>NE2 3AE</Postcode>
                    <County>Tyne and Wear</County>
                    <Country>GB</Country>
                    <Notes />
                    <CustomFields />
                    <Activities />
                    <Groups />
                </Contact>
            </Contacts>
            <CustomFields />
        </Customer>
    </Customers>
</Company>
```

In each of the following sections, most of the XML has been omitted to make the samples easier to read. The whole structure of the Zynk XML Company schema is used below, as a reference of where fields should be in the object model.

### Identifying Fields
The Id field should be populated by the unique id of the customer/contact from the external system (actual type depends on the system being integrated), Zynk uses this field to track Contacts already imported into ACT!. The UniqueId (actual ACT! ID) of the record can be specified if this is known. We would typically advise to always populate the Id. If it is possible to customise the external system to support storing the ACT! ID, then the integration could be structured to always download the Id, the UniqueId (if populated on the website) and then to notify the external system of any successfully imported ACT! Contacts so that their ID's can be stored.

| ACT! Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| N/A | Id | 1 | string | 100 | Optional | Required if UniqueId not specified. |
| ID | UniqueId | 43a40019-ba07-427f-a7b0-13901c416f5e | Guid | 36 | Optional | Required if Id not specified. Must be a valid GUID. Will fail if specified UniqueId cannot be found in ACT! ACT! field not visible from the ACT! UI by default. |

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>
      <Contacts>
        <Contact>
          <Id>1</Id>
          <UniqueId>43a40019-ba07-427f-a7b0-13901c416f5e</UniqueId>
        </Contact>
      </Contacts>
    </Customer>   
  </Customers>
</Company>
```

### Business Card
| ACT! Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Contact | Title | Mr | string | 128 | Optional | Concatenated with the Forename, Middlename, Surname and Suffix fields if populated    |
| Contact | Forename | Chris | string | 128 | Optional | Concatenated with the Title, Middlename, Surname and Suffix fields if populated    |
| Contact | Middlename | Michael | string | 128 | Optional | Concatenated with the Title, Forename, Surname and Suffix fields if populated    |
| Contact | Surname | Hotchkiss | string | 128 | Optional | Concatenated with the Title, Forename, Middlename and Suffix fields if populated    |
| Contact | Suffix | Jnr. | string | 128 | Optional | Concatenated with the Title, Forename, Middlename and Surname fields if populated    |
| Phone | Telephone | 0845 123 2920 | string | 32 | Optional |
| Mobile | Mobile | 0778 479 2376 | string | 32 | Optional |
| Email | Email | support@zynk.com | string | 256 | Optional |
| Last Results | LastResults | Followed up | string | 128 | Optional | These are set up as list values in ACT!. Values are matched based on a case insensitive search. If a value is not present in the list, the value will be set on the record in ACT! but will not be added to the 'List Values'. |

```xml
<?xml version="1.0"?>
<Company>
    <Customers>
        <Customer>
            <Contacts>
                <Contact>
                    <Title>Mr</Title>
                    <Forename>Chris</Forename>
                    <Middlename>Michael</Middlename>
                    <Surname>Hotchkiss</Surname>
                    <Suffix>Jr.</Suffix>
                    <Telephone>0845 123 2920</Telephone>
                    <Mobile>0778 479 2376</Mobile>
                    <Email>support@zynk.com</Email>
                    <LastResults>Followed up</LastResults>
                </Contact>
            </Contacts>
        </Customer>
    </Customers>
</Company>
```

### Address

| ACT! Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Address 1 | Address1 | Nelson House, Fleming Business Centre | string | 256 | Optional |
| Address 2 | Address2 | Jesmond | string | 256 | Optional |
| City | Town | Newcastle upon Tyne | string | 256 | Optional |
| County | County | Tyne &amp; Wear | string | 256 | Optional |
| Post | Postcode | NE2 3AE | string | 256 | Optional |
| Country | Country | GB | string | 256 | Optional | The ISO2 Country code should be used as opposed to the Country name. |
| Fax | Fax | 0845 123 2921 | string | 32 | Optional |
| Web Site | Website | http://www.zynk.com | string | 128 | Optional |

```xml
<?xml version="1.0"?>
<Company>
    <Customers>
        <Customer>
            <Contacts>
                <Contact>
                    <Address1>Nelson House, Fleming Business Centre</Address1>
                    <Address2>Jesmond</Address2>
                    <Town>Newcastle upon Tyne</Town>
                    <County>Tyne and Wear</County>
                    <Postcode>NE2 3AE</Postcode>
                    <Country>GB</Country>
                    <Fax>0845 123 2921</Fax>
                    <Website>http://www.zynk.com</Website>
                </Contact>
            </Contacts>
        </Customer>
    </Customers>
</Company>
```

### Status
| ACT! Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| ID/Status | Status | Contractor;Customer | string | 256 | Optional | This field supports multiple values (represented as checkboxes via the ACT! interface), separate values in the XML should be separated by a semicolon (;). These are set up as list values in ACT!. Values are matched based on a case insensitive search. If a value is not present in the list, the value will be set on the record in ACT! but will not be added to the 'List Values'. |
| Referred By | ReferredBy | Word of Mouth | string | 64 | Optional | These are set up as list values in ACT!. Values are matched based on a case insensitive search. If a value is not present in the list, the value will be set on the record in ACT! but will not be added to the 'List Values'. |

```xml
<?xml version="1.0"?>
<Company>
    <Customers>
        <Customer>
            <Contacts>
                <Contact>
                    <Status>Contractor;Customer</Status>
                    <ReferredBy>Word of Mouth</ReferredBy>
                </Contact>
            </Contacts>
        </Customer>
    </Customers>
</Company>
```

