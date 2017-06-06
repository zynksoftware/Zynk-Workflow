---
slug: listing-files-with-ftp
redirect_from: "/article/249-listing-files-with-ftp"
title: Listing Files with FTP
---
This task will provide a list of files contained within a directory on a remote FTP server.

## Settings
### FTP Connection
_Required_  
The FTP Connection to delete from. See the [Connecting to an FTP Server](connecting-to-an-ftp-server) article here if you require more information on how to create/manage connections.  

### Directory
_Required_  
Initial Directory to move to on FTP Server e.g. `/webdata`.  It is important that you use the 'Text or script' data type instead of 'Folder, HTTP or FTP location' for this setting. This will prevent Zynk treating it as a relative path and converting it to an absolute path on the local file system.  

### List Recursively
_Required_  
Set to true to list files in sub-directories of the directory specified.

### Output File
_Optional_  
Name of the file to be created with the list of files. The output format is an XML document containing the list of files.

### Search Pattern
_Optional_  
The search pattern to use to filter the results returned. Supports both the `*` and `?` wildcards. For example, `*.xml` will only list files with the .xml extension.

### Zynk Settings
See [Common Task Settings](common-task-settings)