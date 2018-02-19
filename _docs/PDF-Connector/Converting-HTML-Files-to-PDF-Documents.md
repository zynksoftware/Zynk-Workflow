---
slug: converting-html-files-to-pdf-documents
redirect_from: "/article/285-converting-html-files-to-pdf-documents"
title: Converting HTML Files to PDF Documents
---
This task will convert an HTML document to PDF format. Specify the Input File or URL as the and the Output File as the name of the PDF to generate. You can also specify a Template File which will be used as the backdrop to any information printed via HTML to PDF task - typically this is used for producing letterheads where you are overprinting a letter which is coming from the HTML file. There are a number of other settings which pertain to margins and document layout for PDF generation. These options generally do not need to be changed.

## Settings
### Input URI
_Required_  
The file name of the HTML file to process.

### Output File
_Required_  
The file name of the PDF to be generated

### Template File
_Required_  
The file name of a PDF containing a template backdrop such as a letterhead.

### Auto Detect Page Break
_Required_  
Set to true to detect page breaks in the HTML and apply these to the PDF.

### Enable Hyper Links
_Required_  
Set to true to include hyper links in the PDF.

### Enable Java Script
_Required_  
Set to true to enable JavaScript on the PDF.

### Keep Width
_Required_  
Set to true if the PDF should be generated with a fixed width or height.

### Margin Bottom
_Required_  
The margin size at the bottom of the page in the PDF.

### Margin Left
_Required_  
The margin size at the left of the page in the PDF.

### Margin Right
_Required_  
The margin size at the right of the page in the PDF.

### Margin Top
_Required_  
The margin size at the top of the page in the PDF.

### Meta File
_Required_  
Set to true if the generator should use a metafile, or false if it should use bitmap.

### Portrait
_Required_  
Set to true to generate the PDF in portrait, or false for landscape.

### Split Images
_Required_  
Set to true if images are allowed to be split across pages.

### Split Text Lines
_Required_  
Set to true if text lines are allowed to be split across pages.

### Zynk Settings
See [Common Task Settings](common-task-settings). 