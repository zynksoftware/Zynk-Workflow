---
slug: using-global-variables
redirect_from: "/article/75-using-global-variables"
title: Using Global Variables
---
Global variables can be accessed by any task in any workflow. This differs from workflow variables, which can only be accessed by the tasks in that workflow. Any command line arguments that are passed to Zynk on start-up are automatically stored in global variables. This feature can be used to help integrate Zynk with other applications.

## Creating Global Variables
New global variables can be created by clicking the 'Global Variables' button in the main Zynk toolbar. You will then be presented with a window like the one below.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b09a5a9033603f7da36ffe/file-gt6dIRcowB.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b09a5a9033603f7da36ffe/file-gt6dIRcowB.png)

1. Click the 'Add' button to add a new global variable.
2. Enter a name for the variable in the 'Key' field.
3. Enter a value for the variable in the 'Value' field. The value is a [Zynk Object](zynk-objects), so it can store both static and dynamic values.
4. When you are finished adding global variables, click the OK button.

## Accessing Global Variables
The value of a global variable can be used any task setting which accepts a [Zynk Object](zynk-objects). To use a variable for a task setting, click on the '...' button at the edge of the field. You will then see the following window.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b09a60c6979143615648d2/file-75Xmv3BIiP.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b09a60c6979143615648d2/file-75Xmv3BIiP.png)

1. Select 'Variable' from the Data Type drop down menu.
2. Select the variable you would like to use from the list. Global variables are listed under the '-- Application Variables --' section.

## Command Line Arguments
Any command line arguments that are passed to Zynk are stored in global variables, prefixed with "Command Line ", followed with a zero based index of the argument.  As an example, calling Zynk with the following: -

`Zynk.exe "/r" "C:\ProgramData\Zynk Software\Zynk\2.0\My Workflows\Global.wkf" "import.xml"`

Would store as: -

1. Command Line 0 = /r
2. Command Line 1 = C:\ProgramData\Zynk Software\Zynk\2.0\My Workflows\Global.wkf
3. Command Line 2 = import.xml

To use within Zynk, you could set the Input File of a task to use the following (with Razor enabled), which at runtime would be the file passed as the third argument to Zynk: -

`@Context.Application["Command Line 2"]`