---
slug: odbc-select
redirect_from: "/article/280-odbc-select"
title: ODBC Select
---
This task will execute an SQL query and return a data set back in XML format.

## Settings
### Output File
_Required_  
The XML file to output results to.

### Root
_Required_  
The name to use for root node in the output XML file (e.g. Customers).

### Row
_Required_  
The name to use for each row in the output XML file (e.g. Customer).

### Parameter Field
_Optional_  
Parameter to use when building the output file.

### Parameter Input File
_Optional_  
The file containing the parameters that will be replaced in the query.

### Parameter Output File
_Optional_  
The file that will contain the parameters created from the query.

### Query
_Required_  
The SQL Query to be executed (e.g. 	`SELECT * FROM Customers`).  You can use the [Query Designer](using-the-query-designer) to build the query visually.

### Connection
_Required_  
The ODBC Connection to use.  See the [Connecting to an ODBC Database](connecting-to-an-odbc-database) article if you require more information on how to create/manage connections.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
You can find an example of how to use this task in the [ODBC Connector](odbc-connector) tutorial.

Sample SQL query:

```sql
SELECT CustomerAccountNumber, AccountBalance FROM SLCustomerAccount
```

Sample output file if you do not specify any values for the Root and Row XML field names. The output defaults to using "Rows" for the root and "Row" for each row in the result set.

```xml
<?xml version="1.0" standalone="yes"?>
<Rows>
  <Row CustomerAccountNumber="INT01" AccountBalance="0.00" />
  <Row CustomerAccountNumber="INT02" AccountBalance="0.00" />
  <Row CustomerAccountNumber="INTE001" CustomerAccountName="Internetware Limited" AccountBalance="0.00" CreditLimit="0.00"  />
</Rows>
```


Sample output file when the Root and Row properties have been as "Customers" and "Customer" to give us more specific XML

```xml
<?xml version="1.0" standalone="yes"?>
<Customers>
  <Customer CustomerAccountNumber="INT01" CustomerAccountName="Merchant Solutions plc" AccountBalance="0.00" CreditLimit="10000.00"  />
  <Customer CustomerAccountNumber="INT02" CustomerAccountName="AG Electronics Ltd"  AccountBalance="0.00" CreditLimit="10000.00"  />
  <Customer CustomerAccountNumber="INTE001" CustomerAccountName="Internetware Limited" AccountBalance="0.00" CreditLimit="0.00"  />
</Customers>
```