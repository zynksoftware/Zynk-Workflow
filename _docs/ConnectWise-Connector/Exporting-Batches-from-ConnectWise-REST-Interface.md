---
slug: exporting-batches-from-connectwise-rest-interface
title: Exporting Batches from ConnectWise REST Interface
---
This task will export accounting batches from ConnectWise in an XML format. The results can be filtered if required. See below for a sample output file.

## Settings
### Connection
_Required_  
The ConnectWise REST Interface connection to use. See the [Connecting to ConnectWise REST Interface](connecting-to-connectwise-rest-interface) article if you require more information on how to create/manage connections.

### Conditions
_Optional_  
Use this setting to specify where clauses to filter the records returned. This setting is used to specify conditions surrounding standard fields.

#### Condition > Comparison
_Required_  
The following types of filter are available:

* __Contains__ - Returns records where the field contains the specified value.
* __Equal__ - Returns records where the field matches the specified value.
* __GreaterThan__ - Returns records where the field is greater than the specified value.
* __GreaterThanOrEqual__ - Returns records where the field is greater than or equal to the specified value.
* __In__ - Returns records where the field matches one of the specified values.
* __Like__ - Returns records where the field contains the specified value.
* __LessThan__ - Returns records where the field is less than the specified value.
* __LessThanOrEqual__ - Returns records where the field is less than or equal to the specified value.
* __NotContains__ - Returns records where the field does not contain the specified value.
* __NotEqual__ - Returns records where the field does not match the specified value.
* __NotIn__ - Returns records where the field does not match one of the specified values.
* __NotLike__ - Returns records where the field does not contain the specified value.

#### Condition > Field
_Required_  
The name of the field the condition is to be based upon. The name should match the API field name, as seen in the output file. If using a reference field, include the name of the reference field followed by a slash, then the field to filter on. e.g. `defaultContact/name`

#### Condition > Logic Operator
_Optional_  
The logic operator to use with the next condition when building the where clause. Choose from:

* __And__ - Will return records which meet all of the conditions specified.
* __Or__ - Will return records which meet at least one of the conditions specified.

#### Condition > Value
_Optional_  
The value the filter is to be based upon.

* String values should be surrounded by quotes. e.g. `"John"`
* Boolean values should be specified as either `True` or `False`, with no quotes.
* Datetime values should be specified in ISO8601 format, surrounded by square brackets. e.g. `[2000-01-31T14:51:00Z]`
* Null is specified as `null`.
* When using the In or NotIn comparison, specify a comma separated list of values surrounded by brackets. e.g. `("John", "Ben")`

### Export Settings > Date Created
_Required_  
When the 'Export Modified, New or All Records' setting is set to 'New', only batches created after this date will be exported. This date will update automatically each time the task runs, to ensure only new batches are exported each time.

### Export Settings > Date Modified
_Required_  
When the 'Export Modified, New or All Records' setting is set to 'Modified', only batches updated after this date will be downloaded. This date will update automatically each time the task runs, to ensure only modified batches are exported each time.

### Export Settings > Export Modified, New or All Records
_Required_  
Choose which records should be downloaded. The available options are:

* __Modified__ - Only records updated after the date shown in the 'Date Modified' setting will be downloaded.
* __New__ - Only records created after the date shown in the 'Date Created' setting will be downloaded.
* __All__ - All records will be downloaded, regardless of when they were created or updated.

### Export Settings > Page Size
_Required_  
The number of records to include in each page of results. Defaults to 100. Increasing this value will reduce the number of requests made to the API. The maximum value is 1000.

### Output File
_Required_  
The name of the file to export the batches to.

### References To Fetch
_Optional_  
The exported data may include fields which reference other records in ConnectWise. If you specify the reference field names here, and the task will fetch the related records and include them in the exported data. The supported fields are listed below: 

* This task does not return any references that can be fetched

### References To Fetch Page Size
_Required_  
The number of referenced records to fetch per page. Defaults to 100. Increasing this value will reduce the number of requests made to the API. The maximum value is 1000.

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample output file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<Batches xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Batch>
    <id>284</id>
    <externalId />
    <_info>
      <lastUpdated>2019-10-16T08:31:19Z</lastUpdated>
      <updatedBy>Admin1</updatedBy>
    </_info>
    <batchIdentifier>20191015172525</batchIdentifier>
    <exportInvoicesFlag>false</exportInvoicesFlag>
    <exportExpensesFlag>true</exportExpensesFlag>
    <exportProductsFlag>false</exportProductsFlag>
  </Batch>
</Batches>
```
