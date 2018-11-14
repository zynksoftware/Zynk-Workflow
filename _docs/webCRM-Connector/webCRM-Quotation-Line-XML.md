---
slug: webcrm-quotation-line-xml
title: webCRM Quotation Line XML
---
Quotation lines are used to track products sold on deliveries.  The

## Tasks
Zynk does not support exporting or importing quotation lines directly, but is used within [webCRM Delivery XML](webcrm-delivery-xml) as part of the export of deliveries.
- [Exporting Deliveries from webCRM](exporting-deliveries-from-webcrm)

## Fields
### Id
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| int | 1 | `<Id>9</Id>` |

### CreatedAt
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2018-02-27T14:16:54+00:00 | `<CreatedAt>2018-02-27T14:16:54+00:00</CreatedAt>` |

### UpdatedAt
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| datetime | 2018-02-27T14:20:25+00:00 | `<UpdatedAt>2018-02-27T14:20:25+00:00</UpdatedAt>` |

### Comment
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<Comment></Comment>` |

### CostPrice
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| numeric | 50 | `<CostPrice>50</CostPrice>` |

### CreatedBy
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string | James Shaw | `<CreatedBy>James Shaw</CreatedBy>` |

### Data1
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string | End User | `<Data1>End User</Data1>` |

### Data2
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string | Product 1 | `<Data2>Product 1</Data2>` |

### Data3
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string | 12345 | `<Data3>12345</Data3>` |

### Discount
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| numeric | 0 | `<Discount>0</Discount>` |

### ListPrice
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| numeric | 100 | `<ListPrice>100</ListPrice>` |

### Memo
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string | Product 1 - Description Here | `<Memo>Product 1 - Description Here</Memo>` |

### OpportunityId
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| int | 2 | `<OpportunityId>2</OpportunityId>` |

### OrganisationId
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| int | 1 | `<OrganisationId>1</OrganisationId>` |

### PersonId
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| int | 0 | `<PersonId>0</PersonId>` |

### Price
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| numeric | 100 | `<Price>100</Price>` |

### Quantity
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| numeric | 2 | `<Quantity>2</Quantity>` |

### SortOrder
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| int | 10 | `<SortOrder>10</SortOrder>` |

### StockStatus
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string |  | `<StockStatus />` |

### UpdatedBy
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| string | James Shaw | `<UpdatedBy>James Shaw</UpdatedBy>` |

### VatPercentage
_Read Only_  

| Type | Example | XML |
| --- | --- | --- |
| numeric | 20 | `<VatPercentage>20</VatPercentage>` |

## Example XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<Deliveries xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Delivery ExactMatch="true">
    ...
    <Lines>
      <QuotationLine ExactMatch="true">
        <Id>8</Id>
        <CreatedAt>2018-08-07T10:47:16+01:00</CreatedAt>
        <UpdatedAt>2018-08-07T10:47:16+01:00</UpdatedAt>
        <Comment />
        <CostPrice>50</CostPrice>
        <CreatedBy>James Shaw</CreatedBy>
        <Data1>End User</Data1>
        <Data2>Product 1</Data2>
        <Data3>12345</Data3>
        <Discount>0</Discount>
        <ListPrice>100</ListPrice>
        <Memo>Product 1 - Description Here</Memo>
        <OpportunityId>2</OpportunityId>
        <OrganisationId>1</OrganisationId>
        <PersonId>0</PersonId>
        <Price>100</Price>
        <Quantity>2</Quantity>
        <SortOrder>10</SortOrder>
        <StockStatus />
        <UpdatedBy>James Shaw</UpdatedBy>
        <VatPercentage>20</VatPercentage>
      </QuotationLine>
    </Lines>
    ...
  </Delivery>
</Deliveries>
```
