---
slug: downloading-customers-from-ekm-powershop
redirect_from: "/article/217-downloading-customers-from-ekm-powershop"
title: Downloading Customers from EKM Powershop
---
This task will download details of all customers to an XML file.

## Settings
### Connection
_Required_  
The EKM Powershop connection to use.  See the [Connecting to EKM Powershop](connecting-to-ekm-powershop) article if you require more information on how to create/manage connections.

### Customer Details
_Required_  
Set to true to download full details about each customer (this might be slow if there are a lot of customers to download). Set to false to download only basic information on each customer.

### Output File
_Required_  
The name of the file to export the data to.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Samples
Sample output file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
    <soap:Body>
        <GetCustomersResponse xmlns="http://publicapi.ekmpowershop.com/">
            <GetCustomersResult>
                <Status>Success</Status>
                <Errors />
                <Date>2012-08-02T10:44:01.3888561+01:00</Date>
                <TotalCustomers>1</TotalCustomers>
                <Customers>
                    <CustomerItem>
                        <CustomerID>1</CustomerID>
                        <EmailAddress>support@zynk.com</EmailAddress>
                        <FirstName>John</FirstName>
                        <LastName>Smith</LastName>
                        <CompanyName>Zynk Software</CompanyName>
                        <TimesOrdered>3</TimesOrdered>
                        <SignUpDate>18/07/2012 14:43:42</SignUpDate>
                    </CustomerItem>
                </Customers>
            </GetCustomersResult>
        </GetCustomersResponse>
    </soap:Body>
</soap:Envelope>
```
