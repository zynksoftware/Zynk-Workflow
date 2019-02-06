---
slug: peoplevox-service-types-xml
title: Peoplevox Service Types XML
---

Zynk will export the data from the "Service types" report in XML format.  All columns documented below will appear in the output file. 

## Tasks

 * [Export Service Types from Peoplevox](export-service-types-from-peoplevox)

## Fields
### Carrier

| Type | Example | XML |
| --- | --- | --- |
| string | DHL | `<Carrier>DHL</Carrier>` |

### Name  

| Type | Example | XML |
| --- | --- | --- |
| string | 123 | `<Name>123</Name>` |

### Code  

| Type | Example | XML |
| --- | --- | --- |
| string | 123 | `<Code>123</Code>` |

## Example XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<ServiceTypes xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <ServiceType>
    <Carrier>DHL</Carrier>
    <Name>123</Name>
    <Code>123</Code>
  </ServiceType>
  <ServiceType>
    <Carrier>DHL</Carrier>
    <Name>321</Name>
    <Code>321</Code>
  </ServiceType>
</ServiceTypes>
```
