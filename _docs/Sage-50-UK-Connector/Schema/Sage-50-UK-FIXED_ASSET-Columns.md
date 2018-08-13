---
slug: sage-50-uk-fixed-asset-columns
title: Sage 50 UK FIXED_ASSET Columns
---
| Name | Type  |  Length | Precision  |  Notes  | Example |
| --- | --- | --- | --- | --- | --- |
| ASSET_REF | VARCHAR | 8 | 8 | Fixed asset reference | K562FTF |
| DETAILS_1 | VARCHAR | 60 | 60 | Details 1 | BMW 316Si |
| DETAILS_2 | VARCHAR | 60 | 60 | Details 2 |  |
| DETAILS_3 | VARCHAR | 60 | 60 | Details 3 |  |
| EMPLOYEE | VARCHAR | 15 | 15 | Employee | Garage |
| SERIAL_NUMBER | VARCHAR | 60 | 60 | Serial number | K562FTF |
| PURCHASE_REF | VARCHAR | 8 | 8 | Purchase reference number | QUA001 |
| BAL_SHEET_NOM_CODE | VARCHAR | 8 | 8 | Balance sheet nominal code | 0051 |
| PROFIT_LOSS_NOM_CODE | VARCHAR | 8 | 8 | Profit and Loss nominal code | 8003 |
| DEP_METHOD_CODE | SMALLINT | 2 | 5 | Depreciation method code (1-3) | 1 |
| DEP_METHOD | VARCHAR | 60 | 60 | Depreciation method | Straight |
| DEP_RATE | DOUBLE | 8 | 15 | Depreciation rate | 8 |
| DEPT_NUMBER | SMALLINT | 2 | 5 | Department number | 5 |
| DEPT_NAME | VARCHAR | 60 | 60 | Department name | Marketing |
| ASSET_CAT | SMALLINT | 2 | 5 | Category number | 1 |
| PURCHASE_DATE | DATE | 2 | 10 | Date of purchase | 01/01/2002 00:00:00 |
| COST_PRICE | DOUBLE | 8 | 15 | Cost price | 16500 |
| DEP_LAST | DOUBLE | 8 | 15 | Amount of last depreciation | 110 |
| DEP_NEXT | DOUBLE | 8 | 15 | Amount of next depreciation | 110 |
| DEP_TO_DATE | DOUBLE | 8 | 15 | Amount depreciated to date | 1210 |
| NET_BOOK | DOUBLE | 8 | 15 | Net book value | 15290 |
| RECORD_CREATE_DATE |  | 16 | 0 | Date and time when the record was created. | 27/04/2010 17:16:57 |
| RECORD_MODIFY_DATE |  | 16 | 0 | Date and time when the record was modified. | 04/08/2017 14:18:52 |
| RECORD_DELETED | TINYINT | 2 | 3 | Flag denoting if the record has been deleted or not. | 0 |
