---
slug: using-c-sharp-code-in-xslt
title: Using C# Code in XSLT
---
You may sometimes find that its not possible to do something you require using XSLT, such as checking whether an external file exists before attempting to load it. You often get around limitations in XSLT by writing a C# script to perform the function instead, which can then be called in your XSLT. An example XSLT is shown below which includes a C# script to check if a file exists.

```xml
<?xml version="1.0" encoding="utf-8"?>
<xsl:stylesheet  version="1.0" 
  xmlns:xsl="http://www.w3.org/1999/XSL/Transform" 
  xmlns:msxsl="urn:schemas-microsoft-com:xslt"
  xmlns:cs="urn:cs" 
  exclude-result-prefixes="msxsl cs">

  <xsl:output method="html" indent="yes"/>

  <xsl:param name="OrderSuccessFile"/>
  <xsl:param name="OrderFailFile"/>

  <msxsl:script language ="C#" implements-prefix="cs">
    <![CDATA[
    public bool Valid(string fileName)
    {
      // Check if the file exists
      if (System.IO.File.Exists(fileName))
      {
        // Check the file is parsable
        System.Xml.XmlDocument xmlDoc = new System.Xml.XmlDocument();
        try
        {
          xmlDoc.Load(fileName);
          xmlDoc = null;
          return true;
        }
        catch
        {
          return false;
        }
      }
      else
      {
        return false;
      }
    }
    ]]>
  </msxsl:script>

  <xsl:template match="/">
    <html>
        <head>
        <style>
          * {  font-family:verdana; }
          body,td,th { font-size: 75%; }
          h1 {font-size: 150%; font-weight:normal; margin-top:10; text-align: center;}
          h2 {font-size: 120%; font-weight:normal; margin-top:25;}
        </style>
      </head>

      <body>

        <h1>Zynk Automation Report</h1>

        <!-- Output successful order imports if a valid success file is provided -->
        <xsl:if test="cs:Valid($OrderSuccessFile)">
          <xsl:call-template name="ProcessSalesOrders">
            <xsl:with-param name="file" select="$OrderSuccessFile" />
          </xsl:call-template>
        </xsl:if>

        <!-- Output failed order imports if a valid fail file is provided -->
        <xsl:if test="cs:Valid($OrderFailFile)">
          <xsl:call-template name="ProcessSalesOrders">
            <xsl:with-param name="file" select="$OrderFailFile" />
          </xsl:call-template>
        </xsl:if>
      </body>
    </html>
  </xsl:template>

  <xsl:template name="ProcessSalesOrders">
    <xsl:param name="file" />

    <xsl:variable name="count" select="count(document($file)/Company/SalesOrders/SalesOrder)" />

    <xsl:if test="$count > 0">
      <table width="100%" bgcolor="#ffffff" border="0" cellspacing="1" cellpadding="2">
        <tr>
          <th bgcolor="#eeeeee" align="left"><xsl:value-of select="concat($ExternalSystem, &#39; Order Id&#39;)" /></th>
          <th bgcolor="#eeeeee" align="left">Sales Order Number</th>
          <th bgcolor="#eeeeee" align="left">Account</th>
          <th bgcolor="#eeeeee" align="left">Date</th>
        </tr>

        <xsl:for-each select="document($file)/Company/SalesOrders/SalesOrder">
          <!-- Output key order info -->
          <tr>
            <td bgcolor="#ffffff"><xsl:value-of select="Id"/></td>
            <td bgcolor="#ffffff"><xsl:value-of select="SalesOrderNumber"/></td>
            <td bgcolor="#ffffff"><xsl:value-of select="AccountReference"/></td>
            <td bgcolor="#ffffff"><xsl:value-of select="SalesOrderDate"/></td>
          </tr>

          <!-- Output error information (if any) -->
          <xsl:if test="count(Errors/Error) > 0">
            <tr>
              <td bgcolor="#ffd0d0">
                <strong>Error Name</strong>
              </td>
              <td bgcolor="#ffd0d0">
                <xsl:attribute name="colspan">3</xsl:attribute>
                <strong>Error Description</strong>
              </td>
            </tr>

            <xsl:for-each select="Errors/Error">
              <tr>
                <td bgcolor="#ffd0d0"><xsl:value-of select="Name"/></td>
                <td bgcolor="#ffd0d0">
                  <xsl:attribute name="colspan">3</xsl:attribute>
                  <xsl:value-of select="Description"/>
                </td>
              </tr>
            </xsl:for-each>
          </xsl:if>
        </xsl:for-each>
      </table>
      <br />
    </xsl:if>
  </xsl:template>
</xsl:stylesheet>
```

In order to use C# scripts within an XSLT, you first need to add the msxsl and cs namespaces as shown in the example above. The example shows a method called `Valid` which is in the `<msxsl:script language ="C#" implements-prefix="cs">` node. It checks the file path provided in the `fileName` parameter exists and can be parsed as XML. It is called when required using the XPath `cs:Valid($OrderSuccessFile)`.