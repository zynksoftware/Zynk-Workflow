---
slug: renaming-files-with-ftp
redirect_from: "/article/250-renaming-files-with-ftp"
title: Renaming Files with FTP
---
This task will rename a file on a remote FTP Server

## Settings
### FTP Connection
_Required_  
The FTP Connection to delete from. See the [Connecting to an FTP Server](connecting-to-an-ftp-server) article here if you require more information on how to create/manage connections.  

### Directory
_Required_  
Initial Directory to move to on FTP Server e.g. `/webdata`.  It is important that you use the 'Text or script' data type instead of 'Folder, HTTP or FTP location' for this setting. This will prevent Zynk treating it as a relative path and converting it to an absolute path on the local file system.  

### Filename
_Required_  
The name of file to be renamed e.g. `index.html`.  It is important that you use the 'Text or script' data type instead of 'File' for this setting. This will prevent Zynk treating it as a relative path and converting it to an absolute path on the local file system. 

### Output File
_Optional_  
The new name for the file e.g. `old_index.html`.  It is important that you use the 'Text or script' data type instead of 'File' for this setting. This will prevent Zynk treating it as a relative path and converting it to an absolute path on the local file system.  

### Prepend Timestamp
_Required_  
Set to true to add a timestamp to the output file name.

### Timestamp Format
_Required_  
The format to use for the timestamp e.g. `yyyyMMddHHmmss`

### Zynk Settings
See [Common Task Settings](common-task-settings)