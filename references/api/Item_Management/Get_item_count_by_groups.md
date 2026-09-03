---
title: Get_item_count_by_groups
category: Item_Management
api_name: Get_item_count_by_groups
method: GET
path: /v3/items/groups/count
---

**Category:** Item_Management
**API:** Get_item_count_by_groups

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/items/groups/count

## API Description
Get item count by groups

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| variantGroupId (query) | string | No | Variant Id to retrieve |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| status | string | No | Response Status |
| payload | array<object> | No | Items included in the response list |
| payload.variantGroupId | string | No | variant group id used to create the groups |
| payload.count | string | No | count of items having the same variant group id |
