---
slug: what-gets-installed
redirect_from: "/article/41-what-gets-installed"
title: What gets Installed
---
By default, Zynk will install to **C:\Program Files (x86)\Zynk Software\Zynk**. 

It will also create directories in locations detailed below. During installation, Zynk will require permissions to install to the program files directory and will also require write permissions to update the ProgramData directory. Zynk requires the Microsoft .NET framework 4.7.2 and Microsoft SQL Sever Compact Edition 4.0 to be installed. 

If these are not already installed, they will be installed automatically as part of the installation process.

**Standard Installation**

C:\Program Files (x86)\Zynk Software\Zynk\2.0 
         
    - Zynk.exe 
    - Zynk Connectors
    - Zynk Extensions Folder
    
C:\ProgramData\Zynk Software\Zynk\2.0
         
    - Data  
    - Logs  
    - My Workflows 
    - Workflow Templates 
    - XSLT
    
**Notes**

 * The Data directory holds the data files used by your workflows, and also the database used by Zynk. It is highly advisable to backup this folder on a regular basis.
 * Logs directory keeps a daily rolling daily log output of all Zynk log files.
 * My Workflows directory holds your Workflow files
 * Workflow Templates directory holds the pre-defined Workflow template files
 * XSLT directory keeps any XSLT data transformation templates used by Zynk
 
 * Each workflow once run will have it's only folder, using the same name as the workflow file.
 * Each workflow folder will have an arhcive folder for storing archives created using the archive workflow task

Most systems will not need any modifications to user permissions, however, in certain more secure environments, permissions may need to be explicitly set for the user that is running Zynk.
