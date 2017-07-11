---
slug: sage-200-online-contact-xml
title: Sage 200 Online Contact XML
---

Information can be stored for multiple contacts against each customer account. Each contact can have its own details such as telephone numbers, fax numbers, email address and website. **Note: In Sage 200 Standard, only one contact is supported.**  Further information can be found on the [Sage 200 Online Contact API Documentation](https://developer.columbus.sage.com/docs#/uk/sage200/accounts/v1/customer_contacts). 

## Tasks
Zynk does not currently support downloading or uploading contacts directly, but can be used within [Sage 200 Online Customer XML](sage-200-online-customer-xml) as part of the export and import of customer records.

 * [Exporting Customers From Sage 200 Online](exporting-customers-from-sage-200-online)
 * [Importing Customers To Sage 200 Online](importing-customers-to-sage-200-online)

## Fields for Download and Upload
### salutation_id
_Optional_  
Salutation record Id, can also be set using code, see [salutation](#salutation).

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 1 | `<salutation_id>1</salutation_id>` |

### first_name
_Optional_  
Contact first name.

| Type | Example | XML |
| --- | --- | --- |
| string(60) | Andrew | `<first_name>Andrew</first_name>` |

### middle_name
_Optional_  
Contact middle name.

| Type | Example | XML |
| --- | --- | --- |
| string(60) | Bryan | `<middle_name>Bryan</middle_name>` |

### last_name
_Optional_  
Contact surname.

| Type | Example | XML |
| --- | --- | --- |
| string(60) | Snape | `<last_name>Snape</last_name>` |

### is_default
_Optional_  
Is this the default contact for the parent customer.

| Type | Example | XML |
| --- | --- | --- |
| boolean | true | `<is_default>true</is_default>` |

#### Available Values
 * true
 * false

## Fields for Download Only
### id
_Read Only_  
Customer contact record Id.

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 27008 | `<id>27008</id>` |

### customer_id
_Read Only_  
Customer record Id.

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 27006 | `<customer_id>27006</customer_id>` |

### name
_Read Only_
Contact Name - Concatenated `first_name`, `middle_name` and `last_name`.

| Type | Example | XML |
| --- | --- | --- |
| string(180) | Mr. Andrew Bryan Snape | `<name>Mr. Andrew Bryan Snape</name>` |

### default_telephone
_Read Only_
Default telephone number.

| Type | Example | XML |
| --- | --- | --- |
| string(227) |  | `` |

### default_email
_Read Only_
Default email address.

| Type | Example | XML |
| --- | --- | --- |
| string(227) |  | `` |

### date_time_updated
_Read Only_  
The date and time this entity was last updated (UTC).  This field is updated when a contact is uploaded using Zynk as well as when using the Sage 200 Online interface.

## Expandable Fields
Related information linked to contacts are also included in the downloaded XML, and these can be used to set certain fields on contact uploads using lookups rather than needing to know the internal id of the related record.

### salutation
_Optional_  
The salutation to be used for the contact.  On a download all the related information of the salutation will be included in the XML.  On an upload you can set the code of the salutation to use for the contact and Zynk will lookup the correct internal id from Sage.

#### Download example showing all related information

```xml
<salutation>
    <id>1</id>
    <date_time_updated>2015-10-30T22:33:25.81</date_time_updated>
    <code>Mr.</code>
    <description>Mr.</description>
    <is_default>false</is_default>
</salutation>
```

#### Upload example only setting the code

```xml
<salutation>
    <code>Mr.</code>
</salutation>
```

## Example XML
Note, as contacts are only used as part of customer download or upload the example is shown within the context of a customer record but with all other fields removed.  See [Sage 200 Online Customer XML](sage-200-online-customer-xml) for full sample.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Customers xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customer>
    ...
    <contacts>
      <contact>
        <id>27008</id>
        <salutation_id>1</salutation_id>
        <name>Mr. Andrew Bryan Snape</name>
        <first_name>Andrew</first_name>
        <middle_name>Bryan</middle_name>
        <last_name>Snape</last_name>
        <is_default>true</is_default>
        <default_telephone />
        <default_email />
        <salutation>
          <id>1</id>
          <date_time_updated>2015-10-30T22:33:25.81</date_time_updated>
          <code>Mr.</code>
          <description>Mr.</description>
          <is_default>false</is_default>
        </salutation>
        <date_time_updated>2017-06-02T14:14:35.04</date_time_updated>
        <customer_id>27006</customer_id>
      </contact>
    </contacts>
    ...
  </Customer>
</Customers>
```