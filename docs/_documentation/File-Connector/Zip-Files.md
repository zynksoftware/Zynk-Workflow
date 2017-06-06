---
slug: zip-files
redirect_from: "/article/241-unzip-files"
title: Zip Files
---
This task will Zip a collection of files and create an industry standard Zip file.

## Settings
### Compression Level
_Required_  
Select a compression level - higher is better, defaults to highest setting.

### Password
_Optional_  
The password to encrypt Zip file with.

### Files
_Required_  
The files to zip up. There are different ways to provide this, depending on the data type selected:	  

 * List - Allows you to enter a list of files to zip.
 * File - Allows you to enter a single file to zip.
 * Folder, HTTP or FTP location - Allows you to zip the contents of a folder.
 * Output from the previous task - Use in conjunction with the [List Files](list-files) task to dynamically build a list of files to zip.

### Output File
_Required_  
Name of the Zip file to create.

### Prepend Timestamp
_Required_  
Set to true to add a timestamp to the start of filename. e.g. `20010214120000_filename.xml`

### Timestamp Format
_Required_  
The format to use for the timestamp (e.g. dd-MM-yy_HH-mm-ss-ffff) the default is yyyyMMddHHmmssffff

### Zynk Settings
See [Common Task Settings](common-task-settings)