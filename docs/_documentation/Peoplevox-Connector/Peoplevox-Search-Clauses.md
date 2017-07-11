---
slug: peoplevox-search-clauses
title: Peoplevox Search Clauses
---

All Peoplevox Export tasks allow you to set search clauses to limit the data that is returned from the report.  You can build up complex search criteria by using a number of search clauses and sub search clauses.  

Note, if Export All is set to False, an additional clauses will be applied to filter on the modified date of the record using the Modified Since setting on the task as the value.

![Peoplevox Search Clauses](/assets/images/peoplevox/peoplevox-search-clauses.png)

Use the Add and Remove buttons to maintain the search clauses to apply to the filter, and the Sub  Search Clauses for more complex criteria.

## Tasks

- [Export Despatches from Peoplevox](export-despatches-from-peoplevox)
- [Export Goods In from Peoplevox](export-goods-in-from-peoplevox)
- [Export Item Availability from Peoplevox](export-item-availability-from-peoplevox) 
- [Export Item Movements from Peoplevox](export-item-movements-from-peoplevox)

## Settings
### Clause
_Read Only_  
This will update based on the other details added to the search clause to show a visual representation of filter that will be applied.  

### Comparison
_Required_  
The comparison to use for the Field and Value.  Defaults to Equals.

#### Available Values
 * Contains
 * EndWith
 * Equals
 * GreaterThan
 * GreaterThanOrEqualTo
 * LessThan
 * LessThanOrEqualTo
 * NotEqualTo
 * StartsWith

### Field
_Required_  
The name of field you want to compare the Value to, use the column name as it is expressed in the System reports displayed in your Peoplevox web application.

### Literal
_Required_  
Set to False to have the Value quoted as part of the search.  Set to True if the value is numeric and should not be quoted.  Defaults to False.

### Operator
_Required_  
You can use the operator to build up a complex query of multiple search clauses.  Setting to AND will only return records where all the clauses match.  Setting to OR will return records where at least one of the clauses match.  Defaults to AND.

### Sub Search Clauses
_Optional_  
Additional sub search clauses can be used to build up a complex query.  The Operator of the sub clause defines how the query will be built up.  Note the sub clause had identical settings as the main search clause, except does not allow further sub clauses.

### Value
Enter the value you want to use to compare against the given Field.