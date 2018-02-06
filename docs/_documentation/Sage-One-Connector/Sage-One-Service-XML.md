---
slug: sage-one-service-xml
title: Sage One Service XML
---
The [Import Services](uploading-services-to-sage-one) task allows you to create new and update existing service records in Sage One, using the XML format described below. Any Sage One fields not documented below are not supported with our import.   

A complete example of the XML is shown below. This represents the minimum information required to create a service record in Sage One:

```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <services>
    <service>
      <description>Labour (Hourly)</description>
      <sales_ledger_account>
        <nominal_code>4000</nominal_code>
      </sales_ledger_account>
    </service>
  </services>
</sage_one_company>
```

## Service Identification
The following fields are use to identify the service to create/update. At least one of these fields should be provided. If more than one is provided, Zynk will look for a match based on each field in turn, in the order they are listed below.

| Sage Field | XML Field | Example | Field Type | Input | Notes |
| --- | --- | --- | --- | --- | --- |
| Item Information > Item Code | item_code | LABOUR | string | Optional |  |
| - | id | 0dfbbb5d174611e691e20a5d7cf84c3e | GUID | Optional | Sage's unique service ID. |
| - | external_id | LABOUR | string  | Optional | The ID of the service from the source data. |

```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <services>
    <service>
      <item_code>LABOUR</item_code>
      <id>0dfbbb5d174611e691e20a5d7cf84c3e</id>
      <external_id>LABOUR</external_id>
    </service>
  </services>
</sage_one_company>
```

## Service Details
The following service fields can be set using Zynk.

| Sage Field | XML Field | Example | Field Type | Input | Notes |
| --- | --- | --- | --- | --- | --- |
| Item Information > Item Code | item_code | LABOUR | string | Optional |  |
| Item Information > Description | description | Labour (Hourly) | string | Required |  |
| Item Information > Inactive | active | true | string | Optional | Set to true to make the service active, or false to make it inactive |
| Sales > Sales Account | sales_ledger_account/nominal_code | 4000 | string | Dependant | At least one of the `sales_ledger_account` elements must be provided |
| Sales > Sales Account | sales_ledger_account/name | Sales Type A | string | Dependant | At least one of the `sales_ledger_account` elements must be provided |
| Sales > Sales Account | sales_ledger_account/display_name | Sales Type A (4000) | string | Dependant | At least one of the `sales_ledger_account` elements must be provided |
| Sales > VAT Rate | sales_tax_rate/id | GB_STANDARD | string | Optional |  |
| Sales > VAT Rate | sales_tax_rate/name | Standard 20.00% | string | Optional |  |
| Purchases > Purchase Description | purchase_description | Hourly labour rate | string | Optional |  |
| Additional Information > Notes | Notes | Hourly labour rate | string | Optional |  |

```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <services>
    <service>
      <item_code>LABOUR</item_code>
      <description>Labour (Hourly)</description>
      <active>true</active>
      <sales_ledger_account>
        <nominal_code>4000</nominal_code>
        <name>Sales Type A</name>
        <display_name>Sales Type A (4000)</display_name>
      </sales_ledger_account>
      <sales_tax_rate>
        <id>GB_STANDARD</id>
        <name>Standard 20.00%</name>
      </sales_tax_rate>
      <purchase_description>Hourly labour rate</purchase_description>
      <notes>Hourly labour rate</notes>
    </service>
  </services>
</sage_one_company>
```

## Rates
The following rates fields can be set using Zynk. The rate names must already exist in Sage, this task will not create any that do not already exist.

| Sage Field | XML Field | Example | Field Type | Input | Notes |
| --- | --- | --- | --- | --- | --- |
| Price Name | service_rate_type/name | Sales Price | string | Required |  |
| Price | rate | 5.99 | double | Required |  |
| Includes VAT | rate_includes_tax | true | boolean | Optional |  |

```xml
<?xml version="1.0" encoding="utf-8"?>
<sage_one_company xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <services>
    <service>
      <sales_rates>
        <sales_rate>
          <service_rate_type>
            <name>Rate</name>
          </service_rate_type>
          <rate>5.99</rate>
          <rate_includes_tax>false</rate_includes_tax>
        </sales_rate>
      </sales_rates>
    </service>
  </services>
</sage_one_company>
```