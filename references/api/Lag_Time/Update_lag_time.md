---
title: Update_lag_time
category: Lag_Time
api_name: Update_lag_time
method: POST
path: /v3/feeds
---

**Category:** Lag_Time
**API:** Update_lag_time

**Method:** POST
**HTTP Path:** https://marketplace.walmartapis.com/v3/feeds

## API Description
Update lag time

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| feedType (query) | string | Yes | Use 'lagtime' |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| lagTimeHeader | object | Yes |  |
| lagTimeHeader.version | string | No |  |
| lagTimeHeader.feedDate | string | No |  |
| lagTime | array<object> | No |  |
| lagTime.sku | string | No | A seller-provided Product ID. Response will have decoded value. |
| lagTime.fulfillmentLagTime | integer | No | The number of days between when the item is ordered and when it is shipped |
| lagTime.additionalAttributes | array<object> | No |  |
| lagTime.additionalAttributes.name | string | No |  |
| lagTime.additionalAttributes.value | string | No |  |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| feedId | string | No | A unique ID, returned from the Bulk Upload API, used for tracking the Feed File. |
