---
slug: importing-customers-to-magnetichq
redirect_from: "/article/importing-customers-to-magnetichq"
title: Importing Customers to Magnetic HQ
---
This task will import customers that are supplied in an XML format.

## Settings
### Connection
_Required_  
The MagneticHQ connection to use. See the [Connecting to MagentoHQ](connecting-to-magnetichq) if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of a file for "failed" imports to be sent to.

### Input File
_Required_  
The source file that you want to import in Zynk XML format.

### Success File
_Required_  
The name of a file for "successful" imports to be sent to. 

### Zynk Settings
See [Common Task Settings](common-task-settings).

## Examples
A sample input file is shown below.
```xml
<?xml version="1.0" encoding="utf-8"?>
<MagneticHQData xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
  <Customers>
   <Customer>
      <Name>Test Input Company</Name>
      <Owner>
        <Id>53090727</Id>
      </Owner>
     <ApprovedAccountsCustomer>false</ApprovedAccountsCustomer>
     <ApprovedAccountsSupplier>true</ApprovedAccountsSupplier>
    </Customer>
    </Customers>
    </MagneticHQData>
```
