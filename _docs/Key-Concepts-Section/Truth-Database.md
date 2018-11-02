---
slug: truth-database
title: Truth Database
---
This article will outline detailed information regarding the truth database that Zynk uses. Typically, this is stored in the default data directory (C:\ProgramData\Zynk Software\Zynk\2.0\Data), although if you have specified a bespoke data directory in Tools -> Options the database file will be located in that directory.

You can configure the archive of historical data in this database via your workflow. By default, this is set to retain the previous 90 days of workflow and application history.

Please note, if you lower this to save disk space and our support team cannot locate error logs it's highly unlikely we will be able to support you.

You can interrogate your database using the free-to-use Zynk extension [Zynk Log Manager (ZLM)](zynk-log-manager-zlm).

## Tables
### Connection
The connection table will store all of the connections you have set up within Zynk. For more information on creating an managing connectiong from Zynk please see [here](managing-connections)

The following fields are exposed in the connections table:

* __Id__ The unique identifier for the connection table entry.
* __Data__ Serialized XML data of the connection. This can be used to view specific properties on the connection.
* __Title__ The name you have given to identify the connection.
* __Type__ The external system you have connected to, e.g Magento, Sage 50.
* __IsDefault__ This field identifies whether or not you have made the connection default or not. Default connections will automatically be selected as the connection for new tasks added to your workflows.

### Truth
The truth table will maintain the integrity of data transitioned through Zynk. It is used mainly for duplicate prevention, although it can also be used for traceability purposes.

Each record with an identifier you pass through Zynk will be logged to this table.

The following fields are exposed in the truth table:
* __Id__ The unique identifier of the truth record.
* __Profile__ This field defines the unique identifier of the workflow the record passed through. 
* __Type__ The object name of the record you have processed. For example, if you import a sales order into Sage 50 the type will be 'Zynk.Connect.Sage50.Objects.SalesOrder'
* __InternalId__ The unique identifier given by the parent system
* __ExternalId__ The unique identifer given by the external system.
* __Hash__ - The hash of the truth table entry. 
* __Created__ - This field will indicate the date and time that the truth table entry was created.
* __Modified__ - This field will indicate the date and time the truth table entry was created.
