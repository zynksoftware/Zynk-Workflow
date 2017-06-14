---
slug: sage-200-online-warehouse-xml
title: Sage 200 Online Warehouse XML
---

All stock within Sage 200, regardless of type (Stock, Service/labour, or Miscellaneous), requires a holding location. By default, the HOME warehouse is created within Sage 200, you can then create your own warehouses.  Further information can be found on the [Sage 200 Online Warehouse API Documentation](https://developer.columbus.sage.com/docs#/uk/sage200/accounts/v1/warehouses).

## Tasks
Zynk does not currently support exporting or importing warehouses directly, but can be used within [Sage 200 Online Stock Level XML](sage-200-online-stock-level-xml) as part of the export of stock level records.

 * [Exporting Stock Levels from Sage 200 Online](exporting-currencies-from-sage-200-online)

## Fields for Download Only
### id
 _Read Only_  
Warehouse record Id.

| Type | Example | XML |
| --- | --- | --- |
| integer(int64) | 1 | `<id>1</id>` |

### name
 _Read Only_  
Warehouse name.

| Type | Example | XML |
| --- | --- | --- |
| string(20) | HOME | `<name>HOME</name>` |

### date_time_updated
 _Read Only_  
The date and time this entity was last updated (UTC).

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2017-05-15T16:04:40.42 | `<date_time_updated>2017-05-15T16:04:40.42</date_time_updated>` |

## Example XML
Note, as warehouses are only used as part of stock level download the example is shown within the context of a stock level record but with all other fields removed.  See [Sage 200 Online Stock Level XML](sage-200-online-stock-level-xml) for full sample.

```xml
<?xml version="1.0" encoding="utf-8"?>
<WarehouseHoldings xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <WarehouseHolding>
    ...
    <warehouse>
      <id>1</id>
      <name>HOME</name>
      <date_time_updated>2017-05-15T16:04:40.42</date_time_updated>
    </warehouse>
    ...
  </WarehouseHolding>
</WarehouseHoldings>
```