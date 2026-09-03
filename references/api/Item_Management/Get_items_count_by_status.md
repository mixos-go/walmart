---
title: Get_items_count_by_status
category: Item_Management
api_name: Get_items_count_by_status
method: GET
path: /v3/items/count
---

**Category:** Item_Management
**API:** Get_items_count_by_status

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/items/count

## API Description
Get items count by status

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| status (query) | string | No | Status of Item |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
_No documented response fields._
