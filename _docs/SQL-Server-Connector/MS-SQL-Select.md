---
slug: ms-sql-select
redirect_from: "/article/322-ms-sql-select"
title: MS SQL Select
---
This task will execute a Query and return a data set back in XML format using the Root and Row settings for the XML.

## Settings
### Export As Elements
_Required_  
Set to true to export the data as XML elements, or false to export as XML attributes.

### Output File
_Required_  
Name of the XML file to output results to.

### Root
_Required_  
Name of the XML root e.g. Customers

### Row
_Required_  
Name of the XML row e.g. Customer

### Operation Timeout
_Required_  
The maximum time to wait for the query to execute.

### Parameter Field
_Optional_  
Parameter to use when building the output file.

### Parameter Input File
_Optional_  
The file containing the parameters that will be replaced in the query.

### Parameter Output File
_Optional_  
The file that will contain the parameters created form the query.

### Query
_Required_  
The SQL Query to be executed e.g. 	`SELECT * FROM Customers`.  You can use the [Query Designer](using-the-query-designer) to build the query visually.

### Connection
_Required_  
The SQL Connection to use.  See the [[Connecting to SQL Server](connecting-to-sql-server) article if you require more information on how to create/manage connections.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample SQL query:

```sql
SELECT CustomerAccountNumber, CustomerAccountName, AccountBalance, CreditLimit FROM SLCustomerAccount
```

Sample output file if you do not specify any values for the Root and Row XML field names, and set Export As Elements to false. The output defaults to using "Rows" for the root and "Row" for each row in the result set.

```xml
<?xml version="1.0" standalone="yes"?>
<Rows>
  <Row CustomerAccountNumber="INT01" CustomerAccountName="Merchant Solutions plc" AccountBalance="0.00" CreditLimit="10000.00"  />
  <Row CustomerAccountNumber="INT02" CustomerAccountName="AG Electronics Ltd"  AccountBalance="0.00" CreditLimit="10000.00"  />
  <Row CustomerAccountNumber="INTE001" CustomerAccountName="Internetware Limited" AccountBalance="0.00" CreditLimit="0.00"  />
</Rows>
```

Sample output file when Export As Elements is set to false and the Root and Row properties have been as "Customers" and "Customer" to give us more specific XML.

```xml
<?xml version="1.0" standalone="yes"?>
<Customers>
  <Customer CustomerAccountNumber="INT01" CustomerAccountName="Merchant Solutions plc" AccountBalance="0.00" CreditLimit="10000.00"  />
  <Customer CustomerAccountNumber="INT02" CustomerAccountName="AG Electronics Ltd"  AccountBalance="0.00" CreditLimit="10000.00"  />
  <Customer CustomerAccountNumber="INTE001" CustomerAccountName="Internetware Limited" AccountBalance="0.00" CreditLimit="0.00"  />
</Customers>
```

Sample output file when Export As Elements is set to true and the Root and Row properties have been as "Customers" and "Customer" to give us more specific XML.

```xml
<?xml version="1.0" standalone="yes"?>
<Customers>
  <Customer>
    <CustomerAccountNumber>INT01</CustomerAccountNumber>
    <CustomerAccountName>Merchant Solutions plc</CustomerAccountName>
    <AccountBalance>0.00</AccountBalance>
    <CreditLimit>10000.00</CreditLimit>
  </Customer>
  <Customer>
    <CustomerAccountNumber>INT02</CustomerAccountNumber>
    <CustomerAccountName>AG Electronics Ltd</CustomerAccountName>
    <AccountBalance>0.00</AccountBalance>
    <CreditLimit>10000.00</CreditLimit>
  </Customer>
  <Customer>
    <CustomerAccountNumber>INTE001</CustomerAccountNumber>
    <CustomerAccountName>Internetware Limited</CustomerAccountName>
    <AccountBalance>0.00</AccountBalance>
    <CreditLimit>0.00</CreditLimit>
  </Customer>
</Customers>
```