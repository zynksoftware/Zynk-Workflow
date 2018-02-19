---
slug: using-odbc-driver-with-microsoft-office-applications
redirect_from: "/article/401-using-odbc-driver-with-microsoft-office-applications"
title: Using ODBC driver with Microsoft Office applications
---
**Please Note:** *For the most up to date information on using the ODBC driver for linking Sage 50 Accounts and Microsoft Excel, please refer to Ask Sage Article 11564.  This information is a sample from the Sage 50 help documentation and is provided for reference.*

## To use the ODBC driver to link your Sage 50 Accounts data to Microsoft Excel.
1. Start Microsoft Excel from Windows.

2. Open the Data menu from the Microsoft Excel menu bar and choose the Get External Data option.

- *If the option is not visible, open the Tools menu and then choose the Add-Ins option. In the Add-Ins window, if the MS Query Add-In check box is de-selected, you should check your Excel/Office installation.*
- *If the MSQuery Add-Ins option is not available you must install it. For further information about this see your Microsoft Excel help.*

3. Choose Create New Query.

*The Choose Data Source window appears.*

4. Select the Sage 50 Accounts data source and click OK.

**Note:** *If the accounts data source is not shown in this list box, click New Data Source and then click OK.*

- The ODBC Data Sources window appears.
- When prompted, enter a name for your data source, for example Sage 50 Accounts.
- Next, when prompted, select a driver for the type of database you want to access, for example Sage 50 Accounts v20, from the drop-down list.
- Then click Connect to finish connecting to the data source.

5. If you have activated Access Rights in Sage 50 Accounts, then the User ID and Password you enter here should be the same as the logon name and password you have entered there.

*If your password is for the whole company - that is, your Sage 50 Accounts Access Rights are turned off, then enter MANAGER in the User ID box and your password in the Password box.*

6. Click OK.

*If you click OK without entering anything, the driver tries to use Manager as the User ID without a password. If Manager does have a password, an Incorrect User ID or Password window appears.*

*The Add Tables window appears.*

7. From the Add Tables window, select the table you require and click Add.

8. Click Close when you have made your selection.

*The Tables you have selected appear in list boxes.*

*Using your mouse, drag the right edge of this box to expand it, revealing the fields.*

9. Select the fields you require from the list by double-clicking on each field in turn until you have all the fields required. The fields, as you select them, appear in the database.

10. Open the File menu from the menu bar and choose the Return Data to Microsoft Excel option.

*The Get External Data window appears.*

11. Click OK to accept the options selected and to continue.

*The fields you have selected appear in the Excel spreadsheet.*

12. You can now use the spreadsheet containing the Sage 50 Accounts data.