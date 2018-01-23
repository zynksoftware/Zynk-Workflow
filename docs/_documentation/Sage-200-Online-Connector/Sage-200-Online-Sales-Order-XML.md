---
slug: sage-200-online-sales-order-xml
title: Sage 200 Online Sales Order XML
---
Sales orders are used to represent the sale of goods or services to a customer. They are central to a business and define the terms (price, quantity and times) by which the products or services will be delivered.  Further information can be found on the [Sage 200 Online Sales Order API Documentation](https://developer.columbus.sage.com/docs#/uk/sage200extra/accounts/v1/sop_orders).

## Tasks
 * [Exporting Sales Orders from Sage 200 Online](exporting-sales-orders-from-sage-200-online)
 * [Importing Sales Orders to Sage 200 Online](importing-sales-orders-to-sage-200-online)

## Identifiers
### external_id
_Optional (recommended)_  
To prevent duplicates sales orders being imported into Sage 200 we would recommend to always set the external_id field to a unique id from the source system.  When the field is provided it will be stored within Zynks internal database along with the sales order number assigned by Sage 200.

| Type | Example | XML |
| --- | --- | --- |
| string(255) | 12345 | `<external_id>12345</external_id>` |

## Fields for Download and Upload
### customer_id
_Dependant (see [customer](#customer))_  
Customer record Id, can also be set using customer reference, see [customer](#customer).

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 27006 | `<customer_id>27006</customer_id>` |

### document_no
_Dependant_  
Sales order document number.  Note: If the SOP setting in Sage 200 Extra is to NOT automatically generate numbers, then this property MUST be set.  If the SOP setting in Sage 200 Extra is to automatically generate numbers, or you are using Sage 200 Standard (which doesn't allow you to set this option), then this setting should not be provided. 

| Type | Example | XML |
| --- | --- | --- |
| string(20) | 12345 | `<document_no>12345</document_no>` |

### document_date
_Optional_  
Sales order document date.

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2017-06-05T00:00:00 | `<document_date>2017-06-05T00:00:00</document_date>` |

### customer_document_no
_Optional_  
Customer document number.

| Type | Example | XML |
| --- | --- | --- |
| string(30) | Order #12345 | `<customer_document_no>Order #12345</customer_document_no>` |

### use_invoice_address
_Optional_  
True if this order uses the customer invoice address, else False.

| Type | Example | XML |
| --- | --- | --- |
| boolean | false | `<use_invoice_address>false</use_invoice_address>` |

#### Available Values
 * true
 * false

### settlement_discount_days
_Optional_  
Settlement discount days.

| Type | Example | XML |
| --- | --- | --- |
| integer(int16) | 0 | `<settlement_discount_days>0</settlement_discount_days>` |

### settlement_discount_percent
_Optional_  
Settlement discount percent.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 0.00 | `<settlement_discount_percent>0.00</settlement_discount_percent>` |

### requested_delivery_date
_Optional_  
Requested delivery date.

| Type | Example | XML |
| --- | --- | --- |
| datetime  | 2017-06-10T00:00:00 | `<requested_delivery_date>2017-06-10T00:00:00</requested_delivery_date> ` |

### promised_delivery_date
_Optional_  
Promised delivery date.

| Type | Example | XML |
| --- | --- | --- |
| datetime  | 2017-06-09T00:00:00 | `<promised_delivery_date>2017-06-09T00:00:00</promised_delivery_date>` |

### Analysis codes

Analysis codes are only supported on SOP Orders from version 2016.sp3 (12/09/2017).

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

### lines
_Optional_  
The sales order lines collection.  See [Sage 200 Online Sales Order Line XML](sage-200-online-sales-order-line-xml) for full details.

### delivery_address
_Optional_  
The sales order delivery address.  The `<delivery_address>` node is an object which contains the address fields, all of following fields must be inside the node, see full example XML below.

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

## Fields for Download Only
### id
_Read Only_  
Sales order record Id. 

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 27766 | `<id>27766</id>` |

### document_status
_Read Only_  
Document status.

| Type | Example | XML |
| --- | --- | --- |
| string(20) | EnumDocumentStatusLive | `<document_status>EnumDocumentStatusLive</document_status>` |

#### Available Values
 * EnumDocumentStatusLive
 * EnumDocumentStatusOnHold
 * EnumDocumentStatusComplete
 * EnumDocumentStatusDispute
 * EnumDocumentStatusCancelled
 * EnumDocumentStatusDraft
 * EnumDocumentStatusPrinted

### exchange_rate
_Read Only_  
Exchange rate.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 6dp) | 1.0 | `<exchange_rate>1.0</exchange_rate>` |

### subtotal_goods_value
_Read Only_  
Goods value (sum of stock items and free text).

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 40.0 | `<subtotal_goods_value>40.0</subtotal_goods_value>` |

### total_net_value
_Read Only_  
Net value (sum of all line types).

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 40.0 | `<total_net_value>40.0</total_net_value>` |

### total_tax_value
_Read Only_  
Tax value.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 8.0 | `<total_tax_value>8.0</total_tax_value>` |

### total_gross_value
_Read Only_  
Gross value.

| Type | Example | XML |
| --- | --- | --- |
| number(decimal 2dp) | 48.0 | `<total_gross_value>48.0</total_gross_value>` |

### date_time_updated
_Read Only_  
The date and time this entity was last updated (UTC).

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2017-06-05T15:24:29.44 | `<date_time_updated>2017-06-05T15:24:29.44</date_time_updated>` |

## Expandable Fields
Related information linked to sales orders are also included in the downloaded XML, these can also be used to set certain fields on sales order uploads using lookups rather than needing to know the internal id of the related record.

### customer
_Dependant (see [customer_id](#customer_id))_  
The sales orders customer. On a download all the related information of the customer will be included in the XML, see [Sage 200 Online Customer XML](sage-200-online-customer-xml). On an upload you can set the reference of the customer to use for the sales order and Zynk will lookup the correct internal id from Sage.

#### Export example showing related information

```xml
<customer>
    <id>27006</id>
    <date_time_updated>2017-06-05T15:24:29.723</date_time_updated>
    <reference>ZYNK001</reference>
    <name>Zynk Software Ltd.</name>
    <short_name>Zynk</short_name>
    <balance>-480.00</balance>
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
    <duns_code>424458615</duns_code>
</customer>
```

#### Import example only setting the reference

```xml
<customer>
    <reference>ZYNK001</reference>
</customer>
```

## Example XML
### Minimal Example

```xml
<?xml version="1.0" encoding="utf-8"?>
<SalesOrders 
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
    xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <SalesOrder>
        <customer>
            <reference>ZYNK001</reference>
        </customer>
        <lines>
            <line>
                <line_quantity>1</line_quantity>
                <product>
                    <code>TEST001</code>
                </product>
            </line>
        </lines>
    </SalesOrder>
</SalesOrders>
```

### Full Example

```xml
<?xml version="1.0" encoding="utf-8"?>
<SalesOrders 
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
    xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <SalesOrder>
        <id>27766</id>
        <external_id>12345</external_id>
        <customer_id>27006</customer_id>
        <document_no>12345</document_no>
        <document_date>2017-06-05T00:00:00</document_date>
        <customer_document_no>Order #12345</customer_document_no>
        <use_invoice_address>false</use_invoice_address>
        <settlement_discount_days>0</settlement_discount_days>
        <settlement_discount_percent>0.00</settlement_discount_percent>
        <requested_delivery_date>2017-06-10T00:00:00</requested_delivery_date>
        <promised_delivery_date>2017-06-09T00:00:00</promised_delivery_date>
        <customer>
            <reference>ZYNK001</reference>
        </customer>
        <delivery_address>
            <address_1>i6</address_1>
            <address_2>6 - 8 Charlotte Square</address_2>
            <address_3 />
            <address_4 />
            <city>Newcastle</city>
            <county>Tyne and Wear</county>
            <postcode>NE1 4XF</postcode>
            <address_country_code>
                <code>GB</code>
            </address_country_code>
        </delivery_address>
        <analysis_code_1>North</analysis_code_1>
        <analysis_code_2>Software</analysis_code_2>
        <analysis_code_3>01/01/2005</analysis_code_3>
        <analysis_code_4>10</analysis_code_4>
        <analysis_code_5>true</analysis_code_5>
        <lines>
            <line>
                <line_number>1</line_number>
                <line_type>EnumLineTypeStandard</line_type>
                <description>Test Product</description>
                <line_quantity>4.0</line_quantity>
                <selling_unit_price>10.0</selling_unit_price>
                <unit_discount_percent>0.0</unit_discount_percent>
                <unit_discount_value>0.0</unit_discount_value>
                <show_on_customer_docs>true</show_on_customer_docs>
                <show_on_picking_list_type>Show</show_on_picking_list_type>
                <product>
                    <code>TEST001</code>
                </product>
                <tax_code>
                    <code>1</code>
                </tax_code>
            </line>
        </lines>
    </SalesOrder>
</SalesOrders>
```
