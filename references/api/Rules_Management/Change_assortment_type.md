---
title: Change_assortment_type
category: Rules_Management
api_name: Change_assortment_type
method: PUT
path: /v3/rules/assortment
---

**Category:** Rules_Management
**API:** Change_assortment_type

**Method:** PUT
**HTTP Path:** https://marketplace.walmartapis.com/v3/rules/assortment

## API Description
Change assortment type

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| enable (query) | boolean | Yes |  |
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
| status | string | No |  |
| payload | object | No |  |
| payload.id | string | No | Unique identifier of the rule created for custom rule assortment. |
