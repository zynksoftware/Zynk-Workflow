---
slug: peoplevox-site-xml
title: Peoplevox Site XML
---

Zynk will import the data using the standard fields under Integration Templates that can be ran configured your Peoplevox web application.  Note, the fields must use the default names, you can import the correct configuration using the file below.

## Tasks

 * [Export Sites from Peoplevox](export-sites-from-peoplevox)

## Fields
### Name  

| Type | Example | XML |
| --- | --- | --- |
| string | Primary | `<Name>Primary</Name>` |

### Reference  

| Type | Example | XML |
| --- | --- | --- |
| string | PrimarySite | `<Reference>PrimarySite</Reference>` |

## Example XML

```xml
<?xml version="1.0" encoding="utf-8"?>
<Sites>
  <Site>
    <Name>Primary</Name>
    <Reference>PrimarySite</Reference>
  </Site>
  <Site>
    <Name>Test</Name>
    <Reference>TestSite</Reference>
  </Site>
</Sites>
```