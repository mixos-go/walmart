---
title: Gets_all_exceptions
category: Rules_Management
api_name: Gets_all_exceptions
method: GET
path: /v3/rules/exceptions
---

**Category:** Rules_Management
**API:** Gets_all_exceptions

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/rules/exceptions

## API Description
Gets all exceptions

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
| skuIds | array<string> | No | A seller-provided Product ID. |
| status | string | No |  |
