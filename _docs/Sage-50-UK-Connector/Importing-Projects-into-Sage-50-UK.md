---
slug: importing-projects-into-sage-50-uk
redirect_from: "/article/414-importing-projects-into-sage-50-uk"
title: Importing Projects into Sage 50 UK
---
This task will import projects to Sage 50 that is supplied in Zynk XML format.

## Settings
### Sage 50 Connection
_Required_  
The connection to Sage 50 UK to use.  See the [Connecting to Sage 50 UK](connecting-to-sage-50-uk) article if you require more information on how to create/manage connections.

### Fail File
_Required_  
The name of a file for "failed" imports to be sent to   

### Input File
_Required_  
The source file that you want to import in Zynk XML format   

### Success File
_Required_  
The name of a file for "successful" imports to be sent to.  

### Zynk Settings
See [Common Task Settings](common-task-settings)

## Examples
Sample input file, for full documentation and samples see [Sage 50 UK Project XML](sage-50-uk-project-xml):  



    &lt;?xml version="1.0" encoding="utf-8"?&gt;
    &lt;Company&gt;
      &lt;Projects&gt;
        &lt;Project&gt;
          &lt;Id&gt;1&lt;/Id&gt;
          &lt;Reference&gt;ZYNK&lt;/Reference&gt;
          &lt;Name&gt;ZYNK PROJECT&lt;/Name&gt;
          &lt;Description&gt;ZYNK PROJECT - INTEGRATION&lt;/Description&gt;
          &lt;StartDate&gt;2014-01-13T00:00:00&lt;/StartDate&gt;
          &lt;EndDate&gt;2014-01-14T00:00:00&lt;/EndDate&gt;
          &lt;Status&gt;ACTIVE&lt;/Status&gt;
          &lt;AccountReference&gt;CUST0001&lt;/AccountReference&gt;
          &lt;SecondReference&gt;SECONDREF&lt;/SecondReference&gt;
          &lt;ProjectAddress&gt;
            &lt;ContactName&gt;Mr Chris Hotchkiss&lt;/ContactName&gt;
            &lt;Address1&gt;Nelson House, Fleming Business Centre&lt;/Address1&gt;
            &lt;Address2&gt;Jesmond&lt;/Address2&gt;
            &lt;Town&gt;Newcastle upon Tyne&lt;/Town&gt;
            &lt;County&gt;Tyne &amp;amp; Wear&lt;/County&gt;
            &lt;Postcode&gt;NE2 3AE&lt;/Postcode&gt;
            &lt;Telephone&gt;0845 123 2920&lt;/Telephone&gt;
            &lt;Fax&gt;0845 123 2921&lt;/Fax&gt;
            &lt;Email&gt;support@zynk.com&lt;/Email&gt;
            &lt;Country&gt;GB&lt;/Country&gt;
          &lt;/ProjectAddress&gt;
          &lt;QuotedPrice&gt;6778&lt;/QuotedPrice&gt;
          &lt;Analysis1&gt;ANALYSIS1&lt;/Analysis1&gt;
          &lt;Analysis2&gt;ANALYSIS2&lt;/Analysis2&gt;
          &lt;Analysis3&gt;ANALYSIS3&lt;/Analysis3&gt;
        &lt;/Project&gt;
      &lt;/Projects&gt;
    &lt;/Company&gt;

