---
slug: sage-200-online-country-code-xml
title: Sage 200 Online Country Code XML
---

All countries each have a specific code to identify accounts that belong to that country.  Further information can be found on the [Sage 200 Online Country Code API Documentation](https://developer.columbus.sage.com/docs#/uk/sage200/accounts/v1/country_codes).

## Tasks
 * [Exporting Country Codes from Sage 200 Online](exporting-country-codes-from-sage-200-online)

## Fields for Download Only
### id
 _Read Only_  
Country code record Id.

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 2 | `<id>2</id>` |

### code
 _Read Only_  
Country code.

| Type | Example | XML |
| --- | --- | --- |
| string(2) | AT | `<code>AT</code>` |

### name
 _Read Only_  
Country name.

| Type | Example | XML |
| --- | --- | --- |
| string(60) | Austria | `<name>Austria</name>` |

### eu_member
 _Read Only_  
Flag to indicate if the country is a member of the EU.

| Type | Example | XML |
| --- | --- | --- |
| boolean | true | `<eu_member>true</eu_member>` |

#### Available Values
 * true
 * false

### date_time_updated
 _Read Only_  
The date and time this entity was last updated (UTC).

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2015-10-30T22:33:16.67 | `<date_time_updated>2015-10-30T22:33:16.67</date_time_updated>` |

## Example XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<CountryCodes xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <CountryCode>
  <CountryCode>
    <id>2</id>
    <date_time_updated>2015-10-30T22:33:16.67</date_time_updated>
    <name>Austria</name>
    <code>AT</code>
    <eu_member>true</eu_member>
  </CountryCode>
  <CountryCode>
    <id>3</id>
    <date_time_updated>2015-10-30T22:33:16.67</date_time_updated>
    <name>Belgium</name>
    <code>BE</code>
    <eu_member>true</eu_member>
  </CountryCode>
</CountryCodes>
```