---
slug: updating-chart-of-accounts-in-xero
redirect_from: "/article/909-updating-chart-of-accounts-in-xero"
title: Updating Chart of Accounts in Xero
---


This task will update the chart of accounts in Xero using an XML file.


## Settings 

### Connection 
_Required_
The connection entry you'd like to use to run the task.

### Input File
_Required_
The file containing the chart of accounts to imports to Xero.

### Output File
_Required_
The file to save the create setup summary to.

### Zynk Settings
See [Common Task Settings](common-task-settings)


## Examples


Sample input file containing showing the conversion date and balances for accounts:


```xml
<?xml version="1.0" encoding="utf-8"?>
<Setup xmlns:ms="urn:schemas-microsoft-com:xslt" xmlns:zynk="http://www.zynk.com">
	<ConversionDate>
		<Month>11</Month>
		<Year>2015</Year>
	</ConversionDate>
	<ConversionBalances>
		<ConversionBalance>
			<AccountCode>0020</AccountCode>
			<Balance>50000</Balance>
		</ConversionBalance>
		<ConversionBalance>
			<AccountCode>0021</AccountCode>
			<Balance>-3485</Balance>
		</ConversionBalance>
		<ConversionBalance>
			<AccountCode>0040</AccountCode>
			<Balance>16900</Balance>
		</ConversionBalance>
	</ConversionBalances>
</Setup>

```