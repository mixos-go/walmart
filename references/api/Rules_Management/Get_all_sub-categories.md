---
title: Get_all_sub-categories
category: Rules_Management
api_name: Get_all_sub-categories
method: GET
path: /v3/rules/subcategories
---

**Category:** Rules_Management
**API:** Get_all_sub-categories

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/rules/subcategories

## API Description
Get all sub-categories

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| status | string | No |  |
| payload | array<object> | No |  |
| payload.category | string | No | category |
| payload.subcategory | array<object> | No | subCategory |
| payload.subcategory.subCategoryName | string | No | Name of specific kind of category |
| payload.subcategory.subCategoryId | string | No | ID of specific kind of category |
