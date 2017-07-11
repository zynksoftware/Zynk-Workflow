---
slug: prosku-pre-receipts-xml
title: ProSKU Pre Receipt XML
---
Import pre receipt allows you to create new pre receipts in ProSKU. 

Any ProSKU fields not documented below are not supported with our uploads. 

Sample upload file for creating a pre receipt in ProSKU:

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<pre_receipts>
    <pre_receipt>
        <additional_ref>AddRef1</additional_ref>
        <date_of_receipt>22/02/2016</date_of_receipt>
        <notes>receipt through api</notes>
        <supplier_detail>CON001</supplier_detail>
        <pre_receipt_lines>
            <line>
                <product_code>Phantom</product_code>
                <quantity>4</quantity>
                <pallet_ref></pallet_ref>
                <rotation_date>12/07</rotation_date>
                <batch_no>17</batch_no>
                <location></location>
                <stock_status></stock_status>
            </line>
        </pre_receipt_lines>
    </pre_receipt>
</pre_receipts>
```

## Pre Receipt Details
The below information shows the fields available when creating a pre receipt.

| XML Field | Example | Field Type | Input |
| --- | --- | --- | --- |
| Additional_ref | AddRef1 | string | Required |
| date_of_receipt | 22/02/2016 | string/date  | Optional |
| marshalling_zone | DefMarshal1 | string | Optional |
| notes | receipt through api | string | Optional |
| supplier_detail | Supp01 | string   | Optional |

## Product Details
The below information shows the fields available for specifying a product on the pre receipt.

| XML Field | Example | Field Type | Input |
| --- | --- | --- | --- |
| Product_code | Phantom | string | Required |
| Quantity | 1 | integer | Required |
| Pallet_ref | PAL001 | string | Optional |
| Rotation_date | 12/07 | string/date | Required |
| Batch_no | 17 | string | Required |
| Location | 01A01C | string | Optional |
| Stock_status | Good | string | Optional |