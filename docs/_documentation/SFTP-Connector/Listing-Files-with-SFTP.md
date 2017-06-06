---
slug: listing-files-with-sftp
redirect_from: "/article/303-listing-files-with-sftp"
title: Listing Files with SFTP
---
This task will provide a list of files contained within a directory on a remote SFTP server.

If you need to repeat a process for each of the files in a directory, you can use the [SFTP Repeater](sftp-repeater) task instead.

## Settings
### Connection
_Required_  
The SFTP Connection to delete from.  See the [Connecting to an SFTP Server](connecting-to-an-sftp-server) if you require more information on how to create/manage connections.

### Recursively
_Required_  
Set to true to list files in sub-directories of the directory specified.

### Search Pattern
_Optional_  
Specify a search pattern to filter the files listed e.g. `*.xml` would list all files with the xml extension

### Directory
_Required_  
The directory to move to on SFTP Server e.g. `/webdata`.  It is important that you use the 'Text or script' data type instead of   'Folder, HTTP or FTP location' for this setting. This will prevent Zynk  treating it as a relative path and converting it to an  absolute path on  the local file system.

### Output File 
_Required_  
The name of the file to create on the local file system

### Zynk Settings
See [Common Task Settings](common-task-settings)