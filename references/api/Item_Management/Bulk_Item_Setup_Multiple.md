---
title: Bulk_Item_Setup_Multiple
category: Item_Management
api_name: Bulk_Item_Setup_Multiple
method: POST
path: /v3/feeds
---

**Category:** Item_Management
**API:** Bulk_Item_Setup_Multiple

**Method:** POST
**HTTP Path:** https://marketplace.walmartapis.com/v3/feeds

## API Description
Bulk Item Setup (Multiple)

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| feedType (query) | string | Yes | The feed Type |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Request Body
_No documented request body._

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| feedId | string | No | A unique ID, returned from the Bulk Upload API, used for tracking the feed file |
| additionalAttributes | object | No |  |
| errors | object | No |  |
