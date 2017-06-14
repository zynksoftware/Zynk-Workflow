---
slug: sage-200-online-xml
title: Sage 200 Online XML
---

To integrate with [Sage 200 Online](sage-200-online) using Zynk you will need to import and export data using XML.  The field names and types used are the same as the [Sage 200 Online API Documentation](https://developer.columbus.sage.com/docs#/uk/sage200/accounts), but are in an XML format rather than JSON 

The format for downloading and uploading are the same for each record type, but there are certain fields that only used when creating a record for the first time, updating an existing record, or when downloading a record.  These are highlighted on each page, along with the data types and field length restrictions.

## Country Codes
[Sage 200 Online Country Code XML](sage-200-online-country-code-xml)  
All countries each have a specific code to identify accounts that belong to that country.

### Tasks
 * [Exporting Country Codes from Sage 200 Online](exporting-country-codes-from-sage-200-online)

## Currencies
[Sage 200 Online Currency XML](sage-200-online-currency-xml)  
Sage 200 works in multiple currencies and each company can configure up to 99 currencies to use., and all can be configured to use a single exchange rate, period exchange rates, or both. One currency must be configured as the base currency and this cannot be changed once transactions have been entered.

### Tasks
 * [Exporting Currencies from Sage 200 Online](exporting-currencies-from-sage-200-online)

## Customers
[Sage 200 Online Customer XML](sage-200-online-customer-xml)  
Customers are one of the most important entities within Sage 200 as they are associated with many important resources within the application and underpin most of the main features (e.g. sales orders, payment receipts, etc). 

### Tasks
 * [Exporting Customers From Sage 200 Online](exporting-customers-from-sage-200-online)
 * [Importing Customers To Sage 200 Online](importing-customers-to-sage-200-online)

## Sales Orders
[Sage 200 Online Sales Order XML](sage-200-online-sales-order-xml)  
Sales orders are used to represent the sale of goods or services to a customer. They are central to a business and define the terms (price, quantity and times) by which the products or services will be delivered.

### Tasks
 * [Exporting Sales Orders From Sage 200 Online](exporting-sales-orders-from-sage-200-online)
 * [Importing Sales Orders To Sage 200 Online](importing-sales-orders-to-sage-200-online)

## Sales Receipts
[Sage 200 Online Sales Receipt XML](sage-200-online-sales-receipt-xml)   
Receipts are used to record a sales receipt against a particular customer's account.

### Tasks
 * [Exporting Sales Transactions from Sage 200 Online](exporting-sales-transactions-from-sage-200-online)
 * [Importing Sales Receipts to Sage 200 Online](importing-sales-receipts-to-sage-200-online)

## Sales Transactions
[Sage 200 Online Sales Transaction XML](sage-200-online-sales-transaction-xml)   
Sales posted transactions are created when transactions, such as orders invoiced, receipts, refunds or credit notes, are posted against the sales ledger.

### Tasks
 * [Exporting Sales Transactions from Sage 200 Online](exporting-sales-transactions-from-sage-200-online)
 * [Importing Sales Receipts to Sage 200 Online](importing-sales-receipts-to-sage-200-online)

## Stock Levels
[Sage 200 Online Stock Level XML](sage-200-online-stock-level-xml)  
All stock within Sage 200 regardless of type (Stock, Service/labour, or Miscellaneous), require a holding location. The location indicates where an item is stored and the stock level settings for each product in the warehouse i.e. the re-order level, the minimum and maximum stock levels. Items with a type of 'Stock' have levels recorded for each warehouse location and the levels are used when allocating, issuing and receiving stock. 

### Tasks
 * [Exporting Stock Levels from Sage 200 Online](exporting-stock-levels-from-sage-200-online)
 * [Exporting Stock Records From Sage 200 Online](exporting-stock-records-from-sage-200-online)
 * [Importing Stock Records To Sage 200 Online](importing-stock-records-to-sage-200-online)

## Stock Records
[Sage 200 Online Stock Record XML](sage-200-online-stock-record-xml)   
Products are used to track stock within Sage 200. This is not just for physical items, but also for items that are ordered direct from suppliers, services, and time or labour that can be included on customer invoices.  Each stock item has default settings that are used each time the item is bought or sold. Some of these are inherited from the product group and some are set on each item.

### Tasks
 * [Exporting Stock Records from Sage 200 Online](exporting-stock-records-from-sage-200-online)
 * [Importing Stock Records to Sage 200 Online](importing-stock-records-to-sage-200-online)



