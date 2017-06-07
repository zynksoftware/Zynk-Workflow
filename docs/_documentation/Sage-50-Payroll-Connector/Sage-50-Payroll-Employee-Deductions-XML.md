---
slug: sage-50-payroll-employee-deductions-xml
redirect_from: ""
title: Sage 50 Payroll Employee Deductions XML
---
The [Importing Employee Deductions Into Sage 50 Payroll](importing-employee-deductions-into-sage-50-payroll) task allows you to insert or update Deductions associated with Employees in Sage 50 Payroll.

For an Employee Deduction to be imported, the Employee and the Deduction must already exist in Sage 50 Payroll.

## Employee Matching
The Employee is matched based on the provided `EmployeeReference` in the XML.

```xml
<?xml version="1.0"?>
<Company>
	<EmployeeDeductions>
		<EmployeeDeduction>
			<EmployeeReference>1</EmployeeReference>
		</EmployeeDeduction>
	</EmployeeDeductions>
</Company>
```

### EmployeeReference
_Required_  
**Employee Reference**  
The numeric identifier of the Employee that you would like to associate the Deduction with.

## Deduction Matching
The Deduction is matched based on the provided `DeductionReference` or `DeductionName` in the XML.

```xml
<?xml version="1.0"?>
<Company>
	<EmployeeDeductions>
		<EmployeeDeduction>
			<DeductionReference>1</DeductionReference>
			<DeductionName>Pension</DeductionName>
		</EmployeeDeduction>
	</EmployeeDeductions>
</Company>
```

### DeductionReference
_Optional_  
**Ref**  
The numeric identifier of the Deduction that you would like to associate with the Employee.

### DeductionName
_Optional_  
**Deduction Name**  
The name of the Deduction that you would like to associate with the Employee.

## Employee Payment Fields
The following Employee Deduction fields can be set using Zynk.

```xml
<?xml version="1.0"?>
<Company>
	<EmployeeDeductions>
		<EmployeeDeduction>
			<Hours>7.5</Hours>
			<Rate>5</Rate>
		</EmployeeDeduction>
	</EmployeeDeductions>
</Company>
```

### Hours
_Optional_  
**Hours/No**  
The number of hours to set on the Employee Deduction.

### Rate
_Optional_  
**Rate**  
The hourly rate to set on the Employee Deduction.

## Samples

Sample import file for importing a new Employee Deduction  
_If the Deduction is already associated with the Employee then the import of the record will fail_  

```xml
<?xml version="1.0"?>
<Company>
	<EmployeeDeductions>
		<EmployeeDeduction RecordOperation="Insert">
			<EmployeeReference>1</EmployeeReference>
			<DeductionName>Pension</DeductionName>
			<Hours>7.5</Hours>
			<Rate>5</Rate>
		</EmployeeDeduction>
	</EmployeeDeductions>
</Company>
```

Sample import file for updating an existing Employee Deduction   
_If the Deduction isn't already associated with the Employee then the import of the record will fail_  

```xml
<?xml version="1.0"?>
<Company>
	<EmployeeDeductions>
		<EmployeeDeduction RecordOperation="Update">
			<EmployeeReference>1</EmployeeReference>
			<DeductionName>Pension</DeductionName>
			<Hours>7.5</Hours>
			<Rate>5</Rate>
		</EmployeeDeduction>
	</EmployeeDeductions>
</Company>
```

Sample import file for updating an existing Employee Deduction otherwise inserting a new Employee Deduction

```xml
<?xml version="1.0"?>
<Company>
	<EmployeeDeductions>
		<EmployeeDeduction RecordOperation="Upsert">
			<EmployeeReference>1</EmployeeReference>
			<DeductionName>Pension</DeductionName>
			<Hours>7.5</Hours>
			<Rate>5</Rate>
		</EmployeeDeduction>
	</EmployeeDeductions>
</Company>
```

## Task Links
- [Introduction to the Sage 50 Payroll Connector](sage-50-payroll)
- [Connecting to Sage 50 Payroll](connecting-to-sage-50-payroll)
- [Importing Employee Absences Into Sage 50 Payroll](importing-employee-absences-into-sage-50-payroll)
- [Importing Employee Deductions Into Sage 50 Payroll](importing-employee-deductions-into-sage-50-payroll)
- [Importing Employee Payments Into Sage 50 Payroll](importing-employee-payments-into-sage-50-payroll)

## XML Links
- [Sage-50-Payroll-XML](sage-50-payroll-xml)
- [Sage 50 Payroll Employee Absences XML](sage-50-payroll-employee-absences-xml)
- [Sage 50 Payroll Employee Deductions XML](sage-50-payroll-employee-deductions-xml)
- [Sage 50 Payroll Employee Payments XML](sage-50-payroll-employee-payments-xml)