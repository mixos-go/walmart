---
title: Unpublished_Item_Counts
category: Insights_Management
api_name: Unpublished_Item_Counts
method: GET
path: /v3/insights/items/unpublished/counts
---

**Category:** Insights_Management
**API:** Unpublished_Item_Counts

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/insights/items/unpublished/counts

## API Description
Unpublished Item Counts

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| fromDate (query) | string | Yes | Returns all unpublished items count with reason codes since the given date |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| payload | array<object> | No |  |
| payload.unpublishedCount | string | No | total count for unpublished Item |
| payload.unpublishedValue | string | No | total value for unpublished Item |
| payload.unpublishedReasonCode | string | No | the reason why item is unpublished |
