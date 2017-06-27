---
slug: sage-50-payroll-employee-payments-xml
title: Sage 50 Payroll Employee Payments XML
---

The [[Import Employee Payments|Importing Employee Payments Into Sage 50 Payroll]] task allows you to insert or update Payments associated with Employees in Sage 50 Payroll.

For an Employee Payment to be imported, the Employee and the Payment must already exist in Sage 50 Payroll.

## Employee Matching
The Employee is matched based on the provided `EmployeeReference` in the XML.

```xml
<?xml version="1.0"?>
<Company>
	<EmployeePayments>
		<EmployeePayment>
			<EmployeeReference>1</EmployeeReference>
		</EmployeePayment>
	</EmployeePayments>
</Company>
```

### EmployeeReference
_Required_  
**Employee Reference**  
The numeric identifier of the Employee that you would like to associate the Payment with.

## Payment Matching
The Payment is matched based on the provided `PaymentReference` or `PaymentName` in the XML.

```xml
<?xml version="1.0"?>
<Company>
	<EmployeePayments>
		<EmployeePayment>
			<PaymentReference>1</PaymentReference>
			<PaymentName>Expense</PaymentName>
		</EmployeePayment>
	</EmployeePayments>
</Company>
```

### PaymentReference
_Optional_  
**Ref**  
The numeric identifier of the Payment that you would like to associate with the Employee.

### PaymentName
_Optional_  
**Payment Name**  
The name of the Payment that you would like to associate with the Employee.

## Employee Payment Fields
The following Employee Payment fields can be set using Zynk.

```xml
<?xml version="1.0"?>
<Company>
	<EmployeePayments>
		<EmployeePayment>
			<Hours>7.5</Hours>
			<Rate>10</Rate>
		</EmployeePayment>
	</EmployeePayments>
</Company>
```

### Hours
_Optional_  
**Hours/No.**  
The number of hours to set on the Employee Payment.

### Rate
_Optional_  
**Rate**  
The hourly rate to set on the Employee Payment.

## Samples

Sample import file for [[creating a new|Sage-50-Payroll-XML#record-operations]] Employee Payment  
_If the Payment is already associated with the Employee then the import of the record will fail_  

```xml
<?xml version="1.0"?>
<Company>
	<EmployeePayments>
		<EmployeePayment RecordOperation="Insert">
			<EmployeeReference>1</EmployeeReference>
			<PaymentName>Expense</PaymentName>
			<Hours>7.5</Hours>
			<Rate>15</Rate>
		</EmployeePayment>
	</EmployeePayments>
</Company>
```

Sample import file for [[updating an existing|Sage-50-Payroll-XML#record-operations]] Employee Payment   
_If the Payment isn't already associated with the Employee then the import of the record will fail_  

```xml
<?xml version="1.0"?>
<Company>
	<EmployeePayments>
		<EmployeePayment RecordOperation="Update">
			<EmployeeReference>1</EmployeeReference>
			<PaymentName>Expense</PaymentName>
			<Hours>7.5</Hours>
			<Rate>15</Rate>
		</EmployeePayment>
	</EmployeePayments>
</Company>
```

Sample import file for [[upserting|Sage-50-Payroll-XML#record-operations]] a Employee Payment  
_If the Payment isn't already associated with the Employee then one will be created, otherwise the existing Employee Payment will be updated_

```xml
<?xml version="1.0"?>
<Company>
	<EmployeePayments>
		<EmployeePayment RecordOperation="Upsert">
			<EmployeeReference>1</EmployeeReference>
			<PaymentName>Expense</PaymentName>
			<Hours>7.5</Hours>
			<Rate>10</Rate>
		</EmployeePayment>
	</EmployeePayments>
</Company>
```

## Task Links
- [[Introduction to the Sage 50 Payroll Connector|Sage-50-Payroll]]
- [[Connecting to Sage 50 Payroll]]
- [[Importing Employee Absences Into Sage 50 Payroll]]
- [[Importing Employee Deductions Into Sage 50 Payroll]]
- [[Importing Employee Payments Into Sage 50 Payroll]]

## XML Links
- [[Introduction to the Sage 50 Payroll XML|Sage-50-Payroll-XML]]
- [[Sage 50 Payroll Employee Absences XML]]
- [[Sage 50 Payroll Employee Deductions XML]]
- [[Sage 50 Payroll Employee Payments XML]]