---
slug: zynk-log-manager-zlm
redirect_from: "/article/759-zynk-log-manager-zlm"
title: Zynk Log Manager (ZLM)
---
![ZLM Icon](/assets/images/logmanager.ico)  

You can use Zynk Log Manager (ZLM) to perform a variety of operations on your two Zynk databases (Zynk.sdf and Log.sdf). 

The two database files are located in your data directory, typically this is C:\ProgramData\Zynk Software\Zynk\2.0, although if you have configured a custom data directory in 'Tools -> Options' your database files will be located there. You can browse to your custom data directory if necessary.

As the Sql CE version was updated to 4.0 in version 2.16 of Zynk Workflow, you can select whether to use a Sql CE 3.5 connection or a Sql CE 4.0 connection. For clarification, please see the below: -

* __Versions 2.16 or higher__ use the Sql CE 4.0 connection
* __Versions lower than 2.16__ use the Sql CE 3.5 connection

If you enter the correct Sql CE version, the full path to your database file, your password (if required), size and click connect, you can query the database you've selected for information.

If you enter all the above information and don't click connect, you can verify (test the connection), compact, repair and shrink your database.

* __Verify__ - This method will test the connection details you have entered into ZLM. For further information please visit [MSDN article](https://msdn.microsoft.com/en-us/library/a0a5czch(v=vs.100).aspx) related to verifying a database.
* __Compact__ - This action will reclaim wasted space in the database by recreating the file. For further information please visit [MSDN article](https://msdn.microsoft.com/en-us/library/system.data.sqlserverce.sqlceengine.compact(v=vs.100).aspx) related to compacting a database.
* __Repair__ - This method will attempt to repair a broken database. For further information please visit [MSDN article](https://msdn.microsoft.com/en-us/library/system.data.sqlserverce.sqlceengine.repair(v=vs.100).aspx) related to repairing a database.
* __Shrink__ - This method will attempt to recover wasted space in the database by removing empty page files. For further information please visit [MSDN article](https://msdn.microsoft.com/en-us/library/system.data.sqlserverce.sqlceengine.shrink(v=vs.100).aspx) related to shrinking a database.

## General Settings
### Database
_Required_  
The database (.sdf) file you are looking to repair, shrink, verify or query.

### Password
_Optional_  
If your Zynk database is password protected, enter the password in this setting.

### Size
_Required_  
The maximum size of the database you're connecting to (4091 default).

### Compact To
_Optional_  
If you're compacting your database, optionally write the resulting .sdf file to a different location.

### Size (Manage)
_Optional_  
The maximum size of the database your compacting to.

## Records Settings
Please note, you must be connected to a database to configure and use these settings.

### Keep the logs for the last 
_Optional_  
Optionally remove log files for a period of workflow runs or time.

* __Days or Runs__ select if you would like to remove records based on the number of days or the number of workflow runs.
* __Number__ enter the amount of days or workflow runs you'd like to remove.

### Remove all logs
_Optional_  
This setting will erase all log entries from the database when enabled.

### Remove orphaned logs
_Optional_  
This setting will remove orphaned logs from the database when enabled. An orphaned log is an entry in either the Log or JobItem table that has no related entry in the Job table.

### Remove all truth entries
_Optional_  
This setting will remove all truth entries from the truth database when enabled.

## Query Settings
Please note, you must be connected to a database to configure and use these settings.

### Workflow
_Optional_  
If you are looking to query a specific workflow, and are unsure how to do so, select a workflow from the drop down list and then select one of the available query templates.

### Query Template
_Optional_  
Optionally use one of the available query templates and click 'Send to Query Editor' to run and edit the query.

### Query
_Required_  
Enter your query manually or select one of the available query templates and click 'Execute'. Your results will appear in the window below which you can export or send in csv, xml or html.

## Exporting and Sending Query Data
Once you have successfully executed a query in Zynk Log Manager (ZLM) you can choose to export and/or send the data in one of the following formats:

* __CSV__
* __XML__
* __HTML__

If you choose to send an email with an attachment of the data, you can use the default Zynk Workflow SMTP connection, but we'd prefer you to use your own if possible.

## Examples
Please see below a series of screenshots of the Zynk Log Manager (ZLM). 

![Zynk Log Manager General Tab](/assets/images/extensions/ZLM1.png)  
_* Not connected to database_

![Zynk Log Manager Records Tab](/assets/images/extensions/ZLM2.png)  
_* Connected to database_

![Zynk Log Manager Query Tab](/assets/images/extensions/ZLM3.png)  
_* Connected to database_

![Zynk Log Manager Query](/assets/images/extensions/ZLM5.png)  
_* Connected to database_

## CSV

```csv
Id,Profile,Type,InternalId,ExternalId,Hash,Created,Modified,Purge,Collection
164,d3f9adfe-6002-41f2-bb98-fd0bc6e6154c,Zynk.SAAS.Peoplevox.Objects.ItemType,1152593,01152593,757602046,26/09/2018 14:41:20,26/09/2018 14:41:20,,
```

## XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<QueryResults>
  <QueryResult>
    <Id>164</Id>
    <Profile>d3f9adfe-6002-41f2-bb98-fd0bc6e6154c</Profile>
    <Type>Zynk.SAAS.Peoplevox.Objects.ItemType</Type>
    <InternalId>1152593</InternalId>
    <ExternalId>01152593</ExternalId>
    <Hash>757602046</Hash>
    <Created>26/09/2018 14:41:20</Created>
    <Modified>26/09/2018 14:41:20</Modified>
    <Purge />
  </QueryResult>
</QueryResults>
```

## HTML
![Zynk Log Manager HTML Example](/assets/images/extensions/ZLM4.png)
_* Right click and open image in new tab for better viewing_
