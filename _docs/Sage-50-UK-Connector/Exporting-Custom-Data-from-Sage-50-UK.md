---
slug: exporting-custom-data-from-sage-50-uk
redirect_from: "/article/400-exporting-custom-data-from-sage-50-uk"
title: Exporting Custom Data from Sage 50 UK
---
This task will export data from Sage 50 UK as specified in the Query, it will export to XML format. This is useful when there is no task which exports the data required.

The table and column names that can be used in the Query are determined by the Sage 50 UK ODBC Driver.  We would advise that you connect to Sage 50 UK via Excel (or similar utility) to list the table and column names available on your version, or for reference view article [Sage 50 UK Database Documentation](sage-50-uk-database-documentation).

There is a section within the Sage Accounts Help file which details how to connect up to the Sage 50 UK ODBC via Excel, simply open the Sage help, click 'Index' and search for 'ODBC'.  You can view an extract of the document in the article [Using ODBC driver with Microsoft Office applications](using-odbc-driver-with-microsoft-office-applications).

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Date Modified
_Dependant_  
The rolling date to use when exporting modified records. Will update automatically when the task runs.

### Date Modified Tables
_Optional_  
The list of tables to check for modified records in. Use when the query is joining to multiple tables, and you need to check the modified date in one or more of the tables you are joining to.	  

### Export As Elements
_Required_  
Set to true to export the data as XML elements, or false to export as XML attributes. See the samples below to see the difference between the two formats.

### Export Modified, New or All Records
_Required_  
Specify whether to export new, modified or all records from Sage. Note that the 'Modified' setting also includes new records.	  
  
This setting will only take effect when the query is specified using the 'Select', 'From', 'Where', 'Group By' and 'Order By' settings. When using the 'Custom Query' setting, the task will always return all data.

### Output File
_Required_  
The name of the file to export to. 

### Root
_Required_  
The name of the XML root element, defaults to Rows

### Row
_Required_  
The name of XML rows, defaults to Row

### Custom Query
_Dependant_  
The SQL query to run against Sage 50. This setting takes precedence over the individual 'Select', 'From', 'Where', 'Group By' and 'Order By' settings.  E.g.  `SELECT * FROM STOCK`  

### From
_Dependant_  
The from statement of your SQL query. The FROM keyword should not be included. Not required when specifying the query using the Custom Query setting.  E.g.  `SALES_LEDGER`  

### Group By
_Dependant_  
The group by statement of your SQL query. The GROUP BY keyword should not be  included. Not required when specifying the query using the Custom Query  setting.  E.g.  `SALES_LEDGER.ACCOUNT_REF`  

### Order By
_Dependant_  
The order by statement of your SQL query. The ORDER BY keyword should not be  included. Not required when specifying the query using the Custom Query  setting.  E.g. `SALES_LEDGER.ACCOUNT_REF`

### Select
_Dependant_  
The select statement of your SQL query. The SELECT keyword should not be  included. Not required when specifying the query using the Custom Query  setting.  E.g. `SALES_LEDGER.ACCOUNT_REF, SALES_LEDGER.NAME, SALES_LEDGER.BALANCE`

### Where
_Dependant_  
The where statement of your SQL query. The WHERE keyword should not be  included. Not required when specifying the query using the Custom Query  setting.  E.g.  `SALES_LEDGER.ACCOUNT_REF = 'ABS001'`

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Example query, which selects the name and balance fields from the sales ledger, for the account ABS001:

```sql
SELECT ACCOUNT_REF, NAME, BALANCE FROM sales_ledger WHERE ACCOUNT_REF='ABS001'
```

Example output file, when the 'Export As Elements' setting is false:

```xml
<?xml version="1.0" standalone="yes"?>
<Rows>
  <Row ACCOUNT_REF="ABS001" NAME="ABS Garages Ltd" BALANCE="2533.31" />
</Rows>
```

Example output file, when the 'Export As Elements' setting is true:

```xml
<?xml version="1.0" standalone="yes"?>
<Rows>
  <Row>
    <ACCOUNT_REF>ABS001</ACCOUNT_REF>
    <NAME>ABS Garages Ltd</NAME>
    <BALANCE>2533.31</BALANCE>
  </Row>
</Rows>
```