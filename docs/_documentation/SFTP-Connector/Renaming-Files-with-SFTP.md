---
slug: renaming-files-with-sftp
redirect_from: "/article/304-renaming-files-with-sftp"
title: Renaming Files with SFTP
---
This task will rename a file on a remote FTP Server.

## Settings
### Connection
_Required_  
The SFTP Connection to delete from.  See the [Connecting to an SFTP Server](connecting-to-an-sftp-server) if you require more information on how to create/manage connections.

### Directory
_Required_  
The directory to move to on SFTP Server e.g. `/webdata`.  It is important that you use the 'Text or script' data type instead of   'Folder, HTTP or FTP location' for this setting. This will prevent Zynk  treating it as a relative path and converting it to an  absolute path on  the local file system.  

### Filename
_Required_  
The name of file to be renamed e.g. `web_orders.xml`.  It is important that you use the 'Text or script' data type instead of   'File' for this setting. This will prevent Zynk  treating it as a relative path and converting it to an  absolute path on  the local file system.  

### Output File
_Required_  
The new name the file should be renamed to.  It is important that you use the 'Text or script' data type instead of 'File' for this setting. This will prevent Zynk treating it as a relative path and converting it to an absolute path on the local file system.

### Prepend Timestamp
_Required_  
Set to true to add a timestamp to the start of the output file name.

### Timestamp Format
_Required_  
The format to use for the timestamp e.g. `yyyy-MM-dd\_HH-mm-ss`

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
You can find an example of how to use this task in the [SFTP to Sage 50 Integration](sftp-to-sage-50-integration) article.