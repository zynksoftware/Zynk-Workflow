---
slug: connectwise
redirect_from: "/article/923-introduction-to-the-connectwise-connector"
title: ConnectWise
---
The ConnectWise connector provides tasks that expose some of the functions available via the Accounting Interface, SOAP and REST APIs.  

## REST
The REST tasks allow you to import and export various information from ConnectWise, using the latest version of the API. This often provides access to fields not available via the older Accounting Interface and SOAP APIs. We recommend using the REST versions of the tasks wherever possible.  

- [Connecting to ConnectWise REST Interface](connecting-to-connectwise-rest-interface)
- [Exporting Activities from ConnectWise REST Interface](exporting-activities-from-connectwise-rest-interface)
- [Exporting Companies from ConnectWise REST Interface](exporting-companies-from-connectwise-rest-interface)
- [Exporting GL Batches from ConnectWise REST Interface](exporting-gl-batches-from-connectwise-rest-interface)
- [Exporting Invoices from ConnectWise REST Interface](exporting-invoices-from-connectwise-rest-interface)
- [Exporting Members from ConnectWise REST Interface](exporting-members-from-connectwise-rest-interface)
- [Exporting Purchase Orders from ConnectWise REST Interface](exporting-purchase-orders-from-connectwise-rest-interface)
- [Importing Activities via ConnectWise REST Interface](importing-activities-via-connectwise-rest-interface)
- [Importing Companies via ConnectWise REST Interface](importing-companies-via-connectwise-rest-interface)
- [Importing Invoice Payments via ConnectWise REST Interface](importing-invoice-payments-via-connectwise-rest-interface)
- [Updating GL Batches via ConnectWise REST Interface](updating-gl-batches-via-connectwise-rest-interface)

## Accounting Interface
The Accounting Interface tasks let you download GL batches (unposted Invoices, expenses and procurement information) from ConnectWise, and update GL batches, adding records to the batch on ConnectWise, preventing them from being downloaded again. You can also upload invoice payments to ConnectWise. Each of these tasks requires a ConnectWise Accounting Interface connection, for more information on setting up and managing this type of connection, see the page [Connecting to ConnectWise Accounting Interface](connecting-to-connectwise-accounting-interface).  

- [Connecting to ConnectWise Accounting Interface](connecting-to-connectwise-accounting-interface)
- [Downloading GL Batches from ConnectWise Accounting Interface](downloading-gl-batches-from-connectwise-accounting-interface)
- [Recreating GL Batches from ConnectWise Accounting Interface](recreating-gl-batches-from-connectwise-accounting-interface)
- [Updating GL Batches to ConnectWise Accounting Interface](updating-gl-batches-to-connectwise-accounting-interface)
- [Updating Invoice Payments to ConnectWise Accounting Interface](updating-invoice-payments-to-connectwise-accounting-interface)

## SOAP
The SOAP tasks expose some of the reporting functionality available on ConnectWise, such as listing reports available to be ran and running reports. The other SOAP tasks available allow you to download various information from ConnectWise, such as agreements, companies, invoices, opportunities and purchase orders. Each of these tasks requires a ConnectWise connection, for more information on setting up and managing this type of connection, see the page [Connecting to ConnectWise](connecting-to-connectwise). Documentation on the SOAP tasks will be coming soon!  

- [Connecting to ConnectWise SOAP Interface](connecting-to-connectwise)

## Links
- [ConnectWise Integrations - Frequently Asked Questions](connectwise-integrations-frequently-asked-questions)
- [ConnectWise Integrations](connectwise-integrations)
- [ConnectWise Product Invoice Integration - Field Mapping](connectwise-product-invoice-integration-field-mapping)