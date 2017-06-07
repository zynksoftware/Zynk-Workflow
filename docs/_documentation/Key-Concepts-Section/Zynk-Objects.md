---
slug: zynk-objects
redirect_from: "/article/47-zynk-objects"
title: Zynk Objects
---
Zynk Objects are a flexible way to handle both static and dynamic content such as text values, file names, URL's or lists. Most of the [Tasks](tasks) settings in Zynk accept a Zynk Object. [Variables](variables) values are also Zynk Objects.

## Editing the Value of a Zynk Object
From the task settings list or variable collection editor, click on the setting to edit, then either click the ellipsis (...) button or press F4.

[![Zynk Objects](http://www.zynk.com/images/v2/zynk_object/zynk_object_ellipsis.png "Task Settings")](http://www.zynk.com/images/v2/zynk_object/zynk_object_ellipsis.png)

The Zynk Object editor window will appear, as shown below.

[![](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b094109033603f7da36fde/file-mychizEoSZ.png)](https://s3.amazonaws.com/helpscout.net/docs/assets/565effd4c697915b26a5c620/images/56b094109033603f7da36fde/file-mychizEoSZ.png)

1. Select the appropriate data type from the drop down list. See the list of data types below for more information on each type.
2. Enter the value for the setting into the 'Value' box. You can also use the 'Edit' and 'Browse' buttons to enter a value, depending on the data type selected. See below for more information.
3. Choose any additional options from the 'Options' list. Please note that certain options are only available for certain data types, see the options section below for more information.

## Data Types
### Text or Script
This represents a single text value which can be manually entered at design time. For example, a username, a path to a file, a website address - any static piece of text. Static text objects support the use of [environment variables](http://en.wikipedia.org/wiki/Environment_variable#System_path_variables). For instance, you can use %USERNAME% to return the username of the user currently logged on the the computer.

**Available Options**
When using static objects the Edit button will launch a text editor window which will allow you to edit the value of the setting. You can optionally set the language used for the text editor for syntax highlighting, this will default to C#. The static object will allow the Use Razor Engine setting to dynamically calculate the value to use.

**Processing**
Static objects are calculated with the following process:-

1. Will read the value at the setting level
2. If Use Razor Engine is enabled the value will be ran through the Razor engine and environmental variables will be expanded, the result of which is used as the value

### File Data Type
A file object can be either a full or relative path of a file, for example C:\Exports\Invoices.xml or customers.xml. If you need to enter a directory, use the URI object instead. You can use the browse button to locate the required file on your system, instead of entering the full path manually. File objects support the use of [environment variables](http://en.wikipedia.org/wiki/Environment_variable#System_path_variables). For instance, you can use %AppData% to return the path of the AppData folder on your computer.

**Absolute Paths**
You can either use a full or relative path for file object types. If you use a use a relative path Zynk will use the base directory of the application data path using the current Workflow name. For example:

 * A file of orders.xml in a workflow called My Workflow will be treated as either:
 * C:\Documents and Settings\All Users\Application Data\Internetware\Zynk\1.0\Data\My Workflow\orders.xml (Windows XP, Windows Server 2003)
 * C:\ProgramData\Internetware\Zynk\1.0\Data\My Workflow\orders.xml (Windows Vista and higher, Windows Server 2008 and higher)

**Available Options**
When using file objects the Edit button will launch a text editor window which will allow you to edit the contents of the file (note, this is not enabled if using Use Razor Engine). The file object will allow the Use Razor Engine setting to dynamically calculate the file path to use. You can use the Read Contents of File setting to read the text contents of the file rather than the file path.

**Processing**
File objects are calculated with the following process:-

1. Will read the value at the setting level
2. If Use Razor Engine is enabled the value will be ran through the Razor engine and environmental variables will be expanded, the result of which is used as the value
3. If the file path is not rooted, the workflow's data directory will be used as the root
4. If the folder structure of the file does not exist it will be created
5. If Read Contents of File is enabled the text contents of the file will be read, the result of which is used as the value. Note, the contents of the file will not be ran through the Razor engine.

### Folder HTTP or FTP Location Data Type
A URI object in simple terms represents the address or location of a Website, FTP site or a Folder on your system or server. You can use the browse button to locate a specific folder. If you want to read the URL into memory, tick the Read Contents of File checkbox. URI objects also support the use of environment variables.

**Available Options**
When using URI objects you can enable the Use Razor Engine setting to dynamically calculate the value to use. You can use the Read Contents of File setting to read text value of the URI end point rather than the URI itself.

**Processing**
URI objects are calculated with the following process:-

1. Will read the value at the setting level
2. If Use Razor Engine is enabled the value will be ran through the Razor engine and environmental variables will be expanded, the result of which is used as the value
3. If the value is a directory and the path is not rooted, the workflow's data directory will be used as the root
4. If the value is a directory and the parent folder structure does not exist it will be created
5. If Read Contents of File is enabled the text contents of the URI will be read (note, this will only read the contents of HTTP URI's without Authentication)

### Variable Data Type
If you have configured any variables they will be shown in this drop down list. The list will only show System, Application and Workflow variables. Task and Current variables are only accessible via the razor engine or Razor Template task. See [Accessing Variables in Tasks](accessing-variables-in-tasks) for more information. The value of the variable will be replaced at run time.

**Available Options**
When using variable objects you can enable the Use Razor Engine setting to dynamically calculate the value to use.

**Processing**
Variable objects are calculated with the following process:-

1. Will read the variable name from the setting
2. Will check the Workflow Variables to find a match based on the value from step 1, the result of which is used as the value
3. If no value found from step 2, will check the Global Variables to find a match based on the value from step 1, the result of which is used as the value
4. If no value found from step 3, will check System Variables to find a match based on the value from step 1, the result of which is used as the value
5. If a value was found, and the Use Razor Engine option is enabled, the value will be ran through the Razor engine and environmental variables will be expanded, the result of which is used as the value

### List Data Type
A List object is a "collection" of items - for example the output from a FTP or Directory Listing. The following Tasks support the List object as an input.

 * Email Connector > Send Email
 * File Connector > List Files
 * File Connector > Zip Files
 * File Connector > Delete Files
 * FTP Connector > Upload Files
 * FTP Connector > Download Files
 * XML Connector > XML Merge

**Available Options**
There are no additional options available for this data type.

**Processing**
Each item in the list is itself a Zynk Object, and will be processed according to its type. If the type of an item is set to a list, the items within it will be processed recursively.

### Output from the Previous Task Data Type
This will take the output of the previous and use it as the value for this property. An example of this would be the file location from a previous task.

## Options
### Use Razor Engine
The "Use Razor Engine" option pre-processes the field value through the built-in razor engine allowing you to dynamically create values at run time. An example of this would be where you need to create a filename on the fly at runtime based on the output of a variable. An example of this would be where you are processing a list of orders in a database and need to generate a collection of files based on the order number. For example adding `@(Context.Current["OrderId"]).xml` would result in the system creating a file named 100234.xml. Razor supports the use of [environment variables](http://en.wikipedia.org/wiki/Environment_variable#System_path_variables). For instance, you can use %AppData% to return the path of the AppData folder on your computer.

### Read Contents of File
The "Read Contents of File" option will read a file name or data from a URI location e.g. Website, FTP File and use that data as the value. You can also use the Razor Engine to perform any additional modifications to the data.