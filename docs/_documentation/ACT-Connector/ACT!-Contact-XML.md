---
slug: act-contact-xml
title: ACT! Contact XML
---
Import Contacts allows you to create new and update existing Contacts in ACT!. 

Any ACT! fields not documented below are not explicitly supported with our imports, however, due to ACT! records being highly customisable, we do allow for a custom field collection to be imported with each record, this technique can technically be used to import standard ACT! fields that are not supported by our standard import. (See the 'Custom Fields' section below)

Sample file for importing/updating a Contact:

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>
      <Id>1</Id>
      <CompanyName>Zynk Software Limited</CompanyName>
      <CustomerInvoiceAddress>
        <Title>Mr</Title>
        <Forename>Chris</Forename>
        <Middlename>Michael</Middlename>
        <Surname>Hotchkiss</Surname>
        <Suffix>Jr.</Suffix>
        <Address1>Nelson House, Fleming Business Centre</Address1>
        <Address2>Jesmond</Address2>
        <Address3 />
        <Town>Newcastle upon Tyne</Town>
        <Postcode>NE2 3AE</Postcode>
        <County>Tyne and Wear</County>
        <Country>GB</Country>
        <Telephone>0845 123 2920</Telephone>
        <Mobile>0778 479 2376</Mobile>
        <Email>support@zynk.com</Email>
        <LastResults>Followed up</LastResults>
      </CustomerInvoiceAddress>
      <CustomerDeliveryAddress>
        <Address1>Newcastle Enterprise Centres</Address1>
        <Address2>6 Charlotte Square</Address2>
        <Town>Newcastle upon Tyne</Town>
        <Postcode>NE1 4XF</Postcode>
        <County>Tyne and Wear</County>
        <Country>GB</Country>
        <Notes />
        <CustomFields />
        <Activities />
        <Groups />
      </CustomerDeliveryAddress>
      <CustomFields />
    </Customer>   
  </Customers>
</Company>
```

In each of the following sections, most of the XML has been omitted to make the samples easier to read. The whole structure of the Zynk XML Company schema is used below, as a reference of where fields should be in the object model.

## Identifying Fields
The Id field should be populated by the unique id of the customer/contact from the external system (actual type depends on the system being integrated), Zynk uses this field to track Contacts already imported into ACT!. The UniqueId (actual ACT! ID) of the record can be specified if this is known. We would typically advise to always populate the Id. If it is possible to customise the external system to support storing the ACT! ID, then the integration could be structured to always download the Id, the UniqueId (if populated on the website) and then to notify the external system of any successfully imported ACT! Contacts so that their ID's can be stored.

| ACT! Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| N/A | Id | 1 | string | 100 | Optional | Required if UniqueId not specified. |
| ID | UniqueId | 43a40019-ba07-427f-a7b0-13901c416f5e | Guid | 36 | Optional | Required if Id not specified.  Must be a valid GUID.  Will fail if specified UniqueId cannot be found in ACT! ACT! field not visible from the ACT! UI by default. |

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>
      <Id>1</Id>
      <UniqueId>43a40019-ba07-427f-a7b0-13901c416f5e</UniqueId>
    </Customer>   
  </Customers>
</Company>
```

## Business Card
| ACT! Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Contact | Title | Mr | string | 128 | Optional | Concatenated with the Forename, Middlename, Surname and Suffix fields if populated   |
| Contact | Forename | Chris | string | 128 | Optional | Concatenated with the Title, Middlename, Surname and Suffix fields if populated   |
| Contact | Middlename | Michael | string | 128 | Optional | Concatenated with the Title, Forename, Surname and Suffix fields if populated   |
| Contact | Surname | Hotchkiss | string | 128 | Optional | Concatenated with the Title, Forename, Middlename and Suffix fields if populated   |
| Contact | Suffix | Jnr. | string | 128 | Optional | Concatenated with the Title, Forename, Middlename and Surname fields if populated   |
| Phone | Telephone | 0845 123 2920 | string | 32 | Optional |
| Mobile | Mobile | 0778 479 2376 | string | 32 | Optional |
| Email | Email | support@zynk.com | string | 256 | Optional |
| Last Results | LastResults | Followed up | string | 128 | Optional | These are set up as list values in ACT!. Values are matched based on a case insensitive search. If a value is not present in the list, the value will be set on the record in ACT! but will not be added to the 'List Values'. |

```xml
<?xml version="1.0"?>
<Company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
    <Customer>
      <CustomerInvoiceAddress>
        <Title>Mr</Title>
        <Forename>Chris</Forename>
        <Middlename>Michael</Middlename>
        <Surname>Hotchkiss</Surname>
        <Suffix>Jr.</Suffix>
        <Telephone>0845 123 2920</Telephone>
        <Mobile>0778 479 2376</Mobile>
        <Email>support@zynk.com</Email>
        <LastResults>Followed up</LastResults>
      </CustomerInvoiceAddress>
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
| County | County | Tyne and Wear | string | 256 | Optional | These are set up as list values in ACT!. Values are matched based on a case insensitive search. If a value is not present in the list, the value will be set on the record in ACT! but will not be added to the 'List Values'. |
| Post | Postcode | NE2 3AE | string | 256 | Optional |
| Country | Country | GB | string | 256 | Optional | The ISO2 Country code should be used as opposed to the Country name. |
| Fax | Fax | 0845 123 2921 | string | 32 | Optional |
| Personal E-mail | Email | support@zynk.com | string | 256 | Optional |
| Web Site | Website | http://www.zynk.com | string | 128 | Optional |

```xml
<?xml version="1.0"?>
<Company>
  <Customers>
    <Customer>
      <CustomerInvoiceAddress>
        <Address1>Nelson House, Fleming Business Centre</Address1>
        <Address2>Jesmond</Address2>
        <Town>Newcastle upon Tyne</Town>          
        <County>Tyne and Wear</County>
        <Postcode>NE2 3AE</Postcode>
        <Country>GB</Country>          
        <Fax>0845 123 2921</Fax>
        <Website>http://www.zynk.com</Website>
      </CustomerInvoiceAddress>
      <CustomerDeliveryAddress>
        <Email>support@zynk.com</Email>
      </CustomerDeliveryAddress>
    </Customer>   
  </Customers>
</Company>
```

## Status
| ACT! Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| ID/Status | Status | Contractor;Customer | string | 256 | Optional | This field supports multiple values (represented as checkboxes via the ACT! interface), separate values in the XML should be separated by a semicolon (;). These are set up as list values in ACT!. Values are matched based on a case insensitive search. If a value is not present in the list, the value will be set on the record in ACT! but will not be added to the 'List Values'. |
| Referred By | ReferredBy | Word of Mouth | string | 64 | Optional | These are set up as list values in ACT!. Values are matched based on a case insensitive search. If a value is not present in the list, the value will be set on the record in ACT! but will not be added to the 'List Values'. |

```xml
<?xml version="1.0"?>
<Company>
  <Customers>
    <Customer>
      <CustomerInvoiceAddress>
        <Status>Contractor;Customer</Status>
        <ReferredBy>Word of Mouth</ReferredBy>
      </CustomerInvoiceAddress>
    </Customer>   
  </Customers>
</Company>
```

## Home Address 
| ACT! Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Address 1 | Address1 | Newcastle Enterprise Centres | string | 256 | Optional |
| Address 2 | Address2 | 6 Charlotte Square | string | 256 | Optional |
| Address 3 | Address3 | string | 256 | Optional | Not visible in the default contact layout. |
| City | Town | Newcastle upon Tyne | string | 256 | Optional |
| County | County | Tyne and Wear | string | 256 | Optional | These are set up as list values in ACT!. Values are matched based on a case insensitive search. If a value is not present in the list, the value will be set on the record in ACT! but will not be added to the 'List Values'. |
| Post | Postcode | NE1 4XF | string | 256 | Optional |
| Country | Country | GB | string | 256 | Optional | The ISO2 Country code should be used as opposed to the Country name. |
| Home Phone | Telephone | 0845 123 2920 | string | 32 | Optional |

```xml
<?xml version="1.0"?>
<Company>
    <Customers>
        <Customer>
            <CustomerDeliveryAddress>
                <Address1>Newcastle Enterprise Centres</Address1>
                <Address2>6 Charlotte Square</Address2>
                <Address3></Address3>
                <Town>Newcastle upon Tyne</Town>
                <County>Tyne and Wear</County>
                <Postcode>NE1 4XF</Postcode>
                <Country>GB</Country>
                <Telephone>0845 123 2920</Telephone>
            </CustomerDeliveryAddress>
        </Customer>
    </Customers>
</Company>
```

## Activities
Will import Activities against the Contact. If an Activity cannot be imported, a warning will be logged in Zynk and against the Activity within the Success file of the import.   

| ACT! Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Regarding | Name | Activity Name | string | 256 | Optional | These are set up as list values in ACT!. Values are matched based on a case insensitive search. If a value is not present in the list, the value will be set on the record in ACT! but will not be added to the 'List Values'. |
| Details | Details | Activity Details | string | N/A | Optional |
| Start Date | DueDate | 2014-08-26T00:00:00 | date | - | Required | Must fall on or after 01/01/1900. Will be set to the same date as End Date. |
| End Date | DueDate | 2014-08-26T00:00:00 | date | - | Required | Must fall on or after 01/01/1900. Will be set to the same date as Start Date. |
| Activity Type | Type | ToDo | enum | - | Optional | The Activity Type will default to Call if not provided. Valid values are: **Call**, **Meeting** and **ToDo** |

```xml
<?xml version="1.0"?>
<Company>
  <Customers>
    <Customer>
      <Activities>
        <Activity>
          <Name>Activity Name</Name>
          <Details>Activity Details</Details>
          <DueDate>2014-08-26T00:00:00</DueDate>
          <Type>ToDo</Type>
        </Activity>
      </Activities>
    </Customer>   
  </Customers>
</Company>
```

## Groups
Will assign the Contact to the specified Groups. If the Contact cannot be assigned to a Group, a warning will be logged in Zynk and against the Contact within the Success file of the import.    

| ACT! Field | XML Field | Example | Field Type | Field Length | Input | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Group Name | Name | Prospects | string | 256 | Required | Group names are matched based on a case insensitive search. Groups must already be set up in ACT!. |

```xml
<?xml version="1.0"?>
<Company>
  <Customers>
    <Customer>
      <Groups>
        <Group>
          <Name>Prospects</Name>
        </Group>
      </Groups>
    </Customer>   
  </Customers>
</Company>
```