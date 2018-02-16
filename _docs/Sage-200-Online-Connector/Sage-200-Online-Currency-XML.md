---
slug: sage-200-online-currency-xml
title: Sage 200 Online Currency XML
---

Sage 200 works in multiple currencies and each company can configure up to 99 currencies to use., and all can be configured to use a single exchange rate, period exchange rates, or both. One currency must be configured as the base currency and this cannot be changed once transactions have been entered.  Further information can be found on the [Sage 200 Online Currency API Documentation](https://developer.columbus.sage.com/docs#/uk/sage200/accounts/v1/currencies).

## Tasks
 * [Exporting Currencies from Sage 200 Online](exporting-currencies-from-sage-200-online)

## Fields for Download Only
### id
 _Read Only_  
Currency record Id.

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 1 | `<id>1</id>` |

### symbol
 _Read Only_  
Currency symbol.

| Type | Example | XML |
| --- | --- | --- |
| string(4) | £ | `<symbol>£</symbol>` |

### name
 _Read Only_  
Currency name.

| Type | Example | XML |
| --- | --- | --- |
| string(30) | Pound Sterling | `<name>Pound Sterling</name>` |

### core_currency_rate
 _Read Only_  
Currency rate in use against base.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 6dp) | 1.000000 | `<core_currency_rate>1.000000</core_currency_rate>` |

### euro_currency_rate
 _Read Only_  
Euro rate.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 6dp) | 1.000000 | `<euro_currency_rate>0.860000</euro_currency_rate>` |

### currency_iso_code_id
 _Read Only (see [currency](#currency))_  
ISO Currency Code Record Id. 

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 49 | `<currency_iso_code_id>49</currency_iso_code_id>` |

### is_base_currency
 _Read Only_  
Flag to indicate if the currency is the base currency.

| Type | Example | XML |
| --- | --- | --- |
| boolean | true | `<is_base_currency>true</is_base_currency>` |

#### Available Values
 * true
 * false

### is_euro_currency
 _Read Only_  
Flag to indicate if the currency is Euro.

| Type | Example | XML |
| --- | --- | --- |
| boolean | false | `<is_euro_currency>false</is_euro_currency>` |

#### Available Values
 * true
 * false

### is_base_currency
 _Read Only_  
Flag to indicate if the currency is the base currency.

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2016-07-08T09:28:40.9 | `<date_time_updated>2016-07-08T09:28:40.9</date_time_updated>` |

## Expandable Fields
Related information linked to currencies are also included in the downloaded XML.

### currency_iso_code
_Read Only (see [currency_iso_code_id](#currency_iso_code_id))_  
The currencies ISO code.  On a download all the related information of the ISO code will be included in the XML.

#### id
 _Read Only_  
 Currency ISO code record Id.

 | Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 49 | `<id>49</id>` |

#### code
 _Read Only_  
 ISO currency code.

 | Type | Example | XML |
| --- | --- | --- |
| string(3) | GBP | `code>GBP</code>` |

#### name
 _Read Only_  
 ISO currency name.

 | Type | Example | XML |
| --- | --- | --- |
| string(100) | UNITED KINGDOM, Pound Sterling | `<name>UNITED KINGDOM, Pound Sterling</name>` |

#### date_time_updated
 _Read Only_  
The date and time this entity was last updated (UTC).

 | Type | Example | XML |
| --- | --- | --- |
| datetime | 2015-10-30T22:33:17.707 | `<date_time_updated>2015-10-30T22:33:17.707</date_time_updated>` |

## Example XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<Currencies xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Currency>
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
  </Currency>
  <Currency>
    <id>2</id>
    <date_time_updated>2015-10-30T22:33:17.53</date_time_updated>
    <symbol>€</symbol>
    <name>Euro</name>
    <core_currency_rate>1.000000</core_currency_rate>
    <euro_currency_rate>1.000000</euro_currency_rate>
    <currency_iso_code_id>46</currency_iso_code_id>
    <is_base_currency>false</is_base_currency>
    <is_euro_currency>true</is_euro_currency>
    <currency_iso_code>
      <id>46</id>
      <date_time_updated>2015-10-30T22:33:17.707</date_time_updated>
      <code>EUR</code>
      <name>Euro Member Countries, Euro</name>
    </currency_iso_code>
  </Currency>
</Currencies>
```
