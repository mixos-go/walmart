---
title: Print_Carrier_Label
category: Fulfillment_Management
api_name: Print_Carrier_Label
method: POST
path: /v3/fulfillment/carrier-label/{shipmentId}
---

**Category:** Fulfillment_Management
**API:** Print_Carrier_Label

**Method:** POST
**HTTP Path:** https://marketplace.walmartapis.com/v3/fulfillment/carrier-label/{shipmentId}

## API Description
Print Carrier Label

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| shipmentId (path) | string | Yes | Unique ID identifying each shipment. |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| shipDate | date-time | Yes |  |

## Response
_No documented response fields._
