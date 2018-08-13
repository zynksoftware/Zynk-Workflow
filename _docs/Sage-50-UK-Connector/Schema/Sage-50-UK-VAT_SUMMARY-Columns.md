---
slug: sage-50-uk-vat-summary-columns
title: Sage 50 UK VAT_SUMMARY Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| VAT_BOX | SMALLINT | 2 | 5 | Box on VAT Return |  |
| VAT_BOX_NAME | VARCHAR | 63 | 63 | Box description on VAT reports |  |
| TAX_CODE | VARCHAR | 3 | 3 | Tax code (T0 to T99) |  |
| AMOUNT_INVOICE | DOUBLE | 8 | 15 | Amount from Invoices |  |
| AMOUNT_CREDIT | DOUBLE | 8 | 15 | Amount from Credits |  |
| AMOUNT_BANK | DOUBLE | 8 | 15 | Amount from Bank payments and receipts |  |
| AMOUNT_JOURNAL | DOUBLE | 8 | 15 | Amount from Journals |  |
| AMOUNT_REFUND | DOUBLE | 8 | 15 | Amount from Sales Payments or Purchase Receipts (SP or PR) |  |
| AMOUNT_DISCOUNT | DOUBLE | 8 | 15 | Amount from discounts (SD) |  |
| AMOUNT_REVALUATION | DOUBLE | 8 | 15 | Amount from Revaluations |  |
| HEADING_INVOICE | VARCHAR | 63 | 63 | Heading for invoice transactions on VAT reports |  |
| HEADING_CREDIT | VARCHAR | 63 | 63 | Heading for credit transactions on VAT reports |  |
| HEADING_BANK | VARCHAR | 63 | 63 | Heading for bank transactions on VAT reports |  |
| HEADING_JOURNAL | VARCHAR | 63 | 63 | Heading for journal transactions on VAT reports |  |
| HEADING_REVALUATION | VARCHAR | 63 | 63 | Heading for journal transactions on VAT reports |  |
| HEADING_REFUND | VARCHAR | 63 | 63 | Heading for Sales Payments or Purchase Receipts (SP or PR) on VAT reports |  |
