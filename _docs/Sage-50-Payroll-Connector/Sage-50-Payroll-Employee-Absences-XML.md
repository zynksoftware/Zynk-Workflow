---
slug: sage-50-payroll-employee-absences-xml
redirect_from: ""
title: Sage 50 Payroll Employee Absences XML
---
The [Importing Employee Absences Into Sage 50 Payroll](importing-employee-absences-into-sage-50-payroll) task allows you to insert or update Absence entries associated with Employees in Sage 50 Payroll.

For an Employee Absence to be imported, the Employee must already exist in Sage 50 Payroll.

## Employee Matching
The Employee is matched based on the provided `EmployeeReference` in the XML.

```xml
<?xml version="1.0"?>
<Company>
	<EmployeeAbsences>
		<EmployeeAbsence>
			<EmployeeReference>1</EmployeeReference>
		</EmployeeAbsence>
	</EmployeeAbsences>
</Company>
```

### EmployeeReference
_Required_  
**Employee Reference**  
The numeric identifier of the Employee that you would like to associate Payments with.

## Absence Matching
Existing Absence entries are matched based on the provided `Date` in the XML.

```xml
<?xml version="1.0"?>
<Company>
	<EmployeeAbsences>
		<EmployeeAbsence>
			<Date>2017-05-24T00:00:00</Date>
		</EmployeeAbsence>
	</EmployeeAbsences>
</Company>
```

### Date
_Optional_  
**Date Range**  
The date of the Employee Absence.

## Employee Absence Fields
The following Employee Absence fields can be set using Zynk.

```xml
<?xml version="1.0"?>
<Company>
	<EmployeeAbsences>
		<EmployeeAbsence>			
			<AbsenceType>HolidayBooked</AbsenceType>
			<DayType>FullDay</DayType>
			<Comment>Annual leave</Comment>
		</EmployeeAbsence>
	</EmployeeAbsences>
</Company>
```

### AbsenceType
_Optional_  
**Absence Type**  
The type of the Employee Absence. The following values are valid for the `AbsenceType`, the description as specified in the Sage 50 Payroll documentation appears in _italic_.  
- `SSPWaiting` - _Waiting day for SSP_
- `SSPQualifyingDay` - _Qualifying day for SSP_
- `SSPNonQualifyingDay` - _SSP Non Qualifying Day_
- `SSPGeneral` - _SSP Day_
- `SSPWithheld` - _SSP Day - Withheld_
- `HolidayTaken` - _Holiday taken_
- `HolidayBooked` - _Holiday booked_
- `Authorised` - _Authorised absence_
- `Unauthorised` - _Unauthorised absence_
- `Medical` - _Medical_
- `Educational` - _Study leave etc_
- `Compassionate` - _Compassionate leave_
- `Maternity` - _Maternity leave_
- `Paternity` - _Paternity leave_
- `Jury` - _Jury Service_
- `Suspension` - _Suspension_
- `Punctuality` - _Lateness_
- `Custom1` - _Custom 1_
- `Custom2` - _Custom 2_
- `Custom3` - _Custom 3_
- `Custom4` - _Custom 4_
- `Custom5` - _Custom 5_
- `Custom6` - _Custom 6_
- `Custom7` - _Custom 7_
- `Custom8` - _Custom 8_
- `Custom9` - _Custom 9_

### DayType
_Optional_  
Whether this is a half day absence or full day. The following values are valid for the `DayType`, the description as specified in the Sage 50 Payroll documentation appears in _italic_.  
- `FullDay` - _A full days absence_
- `Morning` - _A mornings absence_
- `Afternoon` - _An afternoons absence_

### Comment
_Optional_  
**Comment**  
The comment associated with the Absence entry.

## Samples

Sample import file for importing a new Employee Absence  
_If there is already an Absence associated with the Employee on the specified Date then the import of the record will fail_  

```xml
<?xml version="1.0"?>
<Company>
	<EmployeeAbsences>
		<EmployeeAbsence RecordOperation="Insert">
			<EmployeeReference>1</EmployeeReference>
			<Date>2018-02-09T00:00:00</Date>
			<AbsenceType>HolidayBooked</AbsenceType>
			<DayType>FullDay</DayType>
			<Comment>Annual leave</Comment>
		</EmployeeAbsence>
	</EmployeeAbsences>
</Company>
```

Sample import file for updating an existing Employee Absence   
_If there isn't an Absence associated with the employee for the specified Date then the import of the record will fail_  

```xml
<?xml version="1.0"?>
<Company>
	<EmployeeAbsences>
		<EmployeeAbsence RecordOperation="Update">
			<EmployeeReference>1</EmployeeReference>
			<Date>2018-02-09T00:00:00</Date>
			<AbsenceType>HolidayBooked</AbsenceType>
			<DayType>FullDay</DayType>
			<Comment>Annual leave</Comment>
		</EmployeeAbsence>
	</EmployeeAbsences>
</Company>
```

Sample import file for updating an existing Employee Absence for the specified Date otherwise inserting a new Employee Absence on that Date.

```xml
<?xml version="1.0"?>
<Company>
	<EmployeeAbsences>
		<EmployeeAbsence RecordOperation="Upsert">
			<EmployeeReference>1</EmployeeReference>
			<Date>2018-02-09T00:00:00</Date>
			<AbsenceType>HolidayBooked</AbsenceType>
			<DayType>FullDay</DayType>
			<Comment>Annual leave</Comment>
		</EmployeeAbsence>
	</EmployeeAbsences>
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