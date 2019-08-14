---
slug: downloading-files-with-ftp
redirect_from: "/article/248-downloading-files-with-ftp"
title: Exporting Files with FTP
---
This task will export a file from a remote FTP server to the local PC or networked drive.

## Settings
### FTP Connection
_Required_  
The FTP Connection to use. See the [Connecting to an FTP Server](connecting-to-an-ftp-server) article here if you require more information on how to create/manage connections.  

### Directory
_Required_  
Initial Directory to move to on FTP Server e.g. `/webdata`.  It is important that you use the 'Text or script' data type instead of 'Folder, HTTP or FTP location' for this setting. This will prevent Zynk treating it as a relative path and converting it to an absolute path on the local file system.  

### Filename
_Required_  
Name of file to be exported e.g. `web_orders.xml`.  It is important that you use the 'Text or script' data type instead of 'File' for this setting. This will prevent Zynk treating it as a relative path and converting it to an absolute path on the local file system.

### Zynk Settings
See [Common Task Settings](common-task-settings)