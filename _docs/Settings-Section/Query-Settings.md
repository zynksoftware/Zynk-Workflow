---
slug: query-settings
redirect_from: "/article/62-query-settings"
title: Query Settings
---
Query settings are used to export additional data from Sage that is not included in the standard Zynk exports. It is also used to set criteria to filter the data exported. All the settings below are SQL based.

## Settings
### Columns
_Optional_  
Used to enter the column names to export from the Sage database. Be sure to include the table name eg. `SLCustomerAccount].[CustomerAccountNumber]` 

### Joins
_Optional_  
Allows data to be exported from other tables in the Sage database. Required when exporting data from tables not included in the standard export.

### Where Clauses
_Optional_  
Allows filters to be set to limit the data that is exported.

## Articles
See the [Sage 200 Custom Exports](using-sage-200-custom-export) tutorial for examples of how to use the query settings.