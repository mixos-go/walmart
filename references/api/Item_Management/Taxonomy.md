---
title: Taxonomy
category: Item_Management
api_name: Taxonomy
method: GET
path: /v3/items/taxonomy
---

**Category:** Item_Management
**API:** Taxonomy

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/items/taxonomy

## API Description
Taxonomy

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
| payload.category | string | No | Type of item |
| payload.subcategory | array<object> | No | Specific kind of category |
| payload.subcategory.subCategoryName | string | No | Name of specific kind of category |
| payload.subcategory.subCategoryId | string | No | ID of specific kind of category |
