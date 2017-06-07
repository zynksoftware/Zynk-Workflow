---
slug: downloading-files-with-sftp
redirect_from: "/article/302-downloading-files-with-sftp"
title: Downloading Files with SFTP
---
This task will download a file from a remote SFTP server to the local PC or networked drive.

## Settings
### Connection
_Required_  
The SFTP Connection to delete from.  See the [Connecting to an SFTP Server](connecting-to-an-sftp-server) if you require more information on how to create/manage connections.

### Directory
_Required_  
The directory to move to on SFTP Server e.g. `/webdata`.  It is important that you use the 'Text or script' data type instead of   'Folder, HTTP or FTP location' for this setting. This will prevent Zynk  treating it as a relative path and converting it to an  absolute path on  the local file system.  

### Filename
_Required_  
The name of file to be downloaded e.g. `web_orders.xml`.  It is important that you use the 'Text or script' data type instead of   'File' for this setting. This will prevent Zynk  treating it as a relative path and converting it to an  absolute path on  the local file system.  

### Output File
_Required_  
The name of the file to create on the local file system.

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
You can find an example of how to use this task in the [SFTP to Sage 50 Integration](sftp-to-sage-50-integration) article.