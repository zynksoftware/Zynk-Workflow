---
slug: querying-records-in-sugarcrm
redirect_from: "/article/324-querying-records-in-sugarcrm"
title: Querying Records in SugarCRM
---


This task will execute a read query against the SugarCRM system and return the data in XML format. Nested queries, custom modules and custom fields are all supported.



Depending on the amount of data returned from the query this task will download in pages, each returning a maximum of 200 records.  The output file will contain all data downloaded from all pages.


## Settings

### Connection 
_Required_  
The SugarCRM Connection to use for querying records. See [Connecting to SugarCRM](connecting-to-sugarcrm).

### Maximum Records
_Required_  
Use this property to specify a maximum number of records to be returned in a Query. Setting this to -1 will return all records

### Output File
_Required_  
The file to saved queried records to.

### Query -> Criteria
_Optional_  
Enter any special criteria for limiting the results returned e.g. `accounts.name LIKE "A%"`. Note that you must provide the module name, unless the field is a custom field created in Studio.

### Query -> Fields
_Required_  
Configure the module name and list of the fields you want the query to return.

### Query -> Include Deleted Records
_Required_  
Set to True if you want the results to include deleted records.

### Query -> Order
_Optional_  
Use this to specify the order in which you require the results to be returned e.g. 	`accounts.name ASC` would sort the data by name in ascending alphabetical order. Note that you must provide the module name, unless the field is a custom field created in Studio.

### Query -> Sub Queries
_Optional_  
A list of further queries used to read data from related modules in SugarCRM. For example, when querying the opportunities module, you could use a sub query to get the account associated with each opportunity, and another to get the items.

### Query -> XML Root Name
_Required_  
Name to use for the XML root e.g. Customers.

### Query -> XML Row Name
_Required_  
Name to use for the XML row name e.g. Customer.

### Record Offset
_Required_  
Offset to start the query if you are returning "pages" of records. Setting this to 0 will return records starting from the first result.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Field Settings


Field settings are used to specify a SugarCRM module to query, and the list of fields to return. You will see a window like the one below when editing the Fields setting.



[![Field Settings](http://www.zynk.com/images/v2/sugar_crm/field_list.png)](http://www.zynk.com/images/v2/sugar_crm/field_list.png)



| 	Setting | 	Required | 	Description |
| --- | --- | --- |
| 	Module Name | 	Required | 	Select the name of the module to query from the drop down. If you are querying a custom module, it will not be listed in the drop down, so you will need to type it in. You can find a list of modules in your SugarCRM system under Admin > Studio. Please note that the module name is case sensitive. |
| 	Link Field | 	Dependant | 	This setting will only be displayed when editing the fields for a sub-query. This setting determines which field will be used to link (i.e. relate) records from this module to the parent query's module. We've provided a list of some of the commonly used 	[Link Fields](link-fields), please refer to the Sugar CRM documentation or contact your Sugar CRM provider for a complete list of the link field names available on each module. |
| 	Fields | 	Required | 	Enter the list of fields that should be returned by the query. Note that the field names are case sensitive. You can find the list of available field names for a module under Admin > Studio > [	*Module Name*] > Fields. You can use the 'Add Standard Fields' button to add all standard fields to the list. Please note that this will only work if you have selected a standard module from the 'Module Name' drop down box. You can remove selected fields from the list using the 'Delete' key, or click the 'Clear Fields' button to clear the list completely. |

## Examples


You can find an example of how to use this task in the [Sugar CRM to Sage 50 Integration](sugar-crm-to-sage-50-integration) article.



Sample output file, when selecting the id and name fields from the Accounts module, with the XML Root Name set to 'Rows' and the XML Row Name set to 'Row':


```xml
<?xml version="1.0" standalone="yes"?>
<Rows>
  <Row id="371d9b28-b7ab-8f28-f098-51a481e42e0d" Name="DataMining Ltd" />
  <Row id="4662fe3e-5457-054a-0195-51a481411e49" Name="Nelson Inc" />
  <Row id="52828444-a7fc-4ecc-72f8-51a48143b6ed" Name="Internetware Ltd" />
</Rows>
```


Sample output file, when selecting the id, name and amount fields from the Opportunities module with the XML Root Name set to 'Opportunities' and XML Row Name set to 'Opportunity', and a sub-query selecting the name, billing\_address\_street and billing\_address\_city fields from the Accounts module with the XML Root Name set to 'Accounts' and the XML Row Name set to 'Account':


```xml	
<?xml version="1.0" encoding="utf-8"?>
<Opportunities>
  <Opportunity id="168ae1cb-15b1-1fca-1959-51a481ab8a6a" name="AB Drivers Limited - 1000 units" amount="25,000.00">
	<Accounts>
	  <Account name="AB Drivers Limited" billing_address_street="345 Sugar Blvd." billing_address_city="Ohio" />
	</Accounts>
  </Opportunity>
  <Opportunity id="23ac1d05-f5f8-3078-729f-51a4812b13e5" name="Ink Conglomerate Inc - 1000 units" amount="10,000.00">
	<Accounts>
	  <Account name="Ink Conglomerate Inc" billing_address_street="1715 Scott Dr" billing_address_city="San Francisco" />
	</Accounts>
  </Opportunity>
</Opportunities>
```
