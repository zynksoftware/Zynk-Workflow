---
slug: prosku-orders-xml
title: ProSKU Orders XML
---
Import orders allows you to create new orders in ProSKU. 

Any ProSKU fields not documented below are not supported with our uploads. 

Sample upload file for creating an order in ProSKU:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<orders>
  <order>
    <order_reference>order_reference1</order_reference>
    <order_date>29/07/2016</order_date>
    <order_type>Sales</order_type>
    <customer>
      <delivery_name>name</delivery_name>
      <notes>notes</notes>
      <shipping>
        <company_name>company_name</company_name>
        <carrier_code>Example Courier Company</carrier_code>
        <service_code>same_day</service_code>
        <address_line_1>23, Address Line</address_line_1>
        <address_line_2>Address Line 2</address_line_2>
        <address_line_3>
        </address_line_3>
        <address_line_4>
        </address_line_4>
        <town>
        </town>
        <post_code>PO5 C0D</post_code>
        <phone_number>12345678</phone_number>
        <email>
        </email>
        <delivery_date>10/08/2016</delivery_date>
        <delivery_time>20:00</delivery_time>
        <country>
          <country_name>United Kingdom</country_name>
          <iso_2_code>GB</iso_2_code>
          <iso_3_code>GBR</iso_3_code>
        </country>
      </shipping>
    </customer>
    <order_lines>
      <line>
        <product_code>Phantom</product_code>
        <quantity>5</quantity>
        <stock_status>Good</stock_status>
        <rotation_date>
        </rotation_date>
        <batch>
        </batch>
        <pallet_ref>
        </pallet_ref>
      </line>
      <line>
        <product_code>0028B001AA</product_code>
        <quantity>5</quantity>
        <stock_status>Good</stock_status>
        <rotation_date>
        </rotation_date>
        <batch>
        </batch>
        <pallet_ref>
        </pallet_ref>
      </line>
    </order_lines>
  </order>
</orders>
```

## Order Details
The below information shows the fields available when creating a pre receipt.

| XML Field | Example | Field Type | Input |
| --- | --- | --- | --- |
| Order_reference | AddRef1 | string | Required |
| Marshalling_zone | m1 | string | Optional |
| Order_date | 10/07/2017 | string/date | Optional |
| Order_type | Sales | string | Optional |
| Notes | notes | string   | Optional |
| Delivery_name | name | string   | Required |
| Company_name | company_name | string   | Optional |
| Carrier_code | Example Courier Company | string   | Optional |
| Service_code | same_day | string   | Optional |
| Phone_number | 07123456789 | string   | Optional |
| Email | example@example.com | string   | Optional |
| Address_line_1 | 23, Address Line | string   | Optional |
| Address_line_2 | Address Line 2 | string   | Optional |
| Address_line_3 | Address Line 3 | string   | Optional |
| Address_line_4 | Address Line 4 | string   | Optional |
| Post_code | PO5 C0D | string   | Optional |
| Town | Newcastle | string   | Optional |
| Delivery_date | 11/07/2017 | string/date   | Optional |
| Delivery_time | 20:00 | string/date   | Optional |
| Country_name | United Kingdom | string   | Optional |
| Iso_2_code | GB | string   | Optional |
| Iso_3_code | GBR | string   | Optional |

## Product Details
The below information shows the fields available for specifying a product on the pre receipt.

| XML Field | Example | Field Type | Input |
| --- | --- | --- | --- |
| Product_code | Phantom | string | Required |
| Quantity | 5 | integer | Required |
| Stock_status | Good | string | Optional |
| Rotation_date | 10/07 | string/date | Optional |
| Batch | 17 | string | Optional |
| Pallet_ref | PAL001 | string | Optional |
