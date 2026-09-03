---
title: Third_party_fulfillment_center_association
category: Settings_Management
api_name: Third_party_fulfillment_center_association
method: POST
path: /v3/settings/shipping/3plshipnodes
---

**Category:** Settings_Management
**API:** Third_party_fulfillment_center_association

**Method:** POST
**HTTP Path:** https://marketplace.walmartapis.com/v3/settings/shipping/3plshipnodes

## API Description
Third party fulfillment center association

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| shipNodeHeader | object | No |  |
| shipNodeHeader.version | string | No |  |
| shipNode | array<object> | No |  |
| shipNode.shipNode | string | No | The fulfillment center or ship node which uniquely identifies each facility and is retrieved from the Get all third party fulfillment providers API. |
| shipNode.status | string | No | Status of fulfillment center. Allowed values: ACTIVE, INACTIVE. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| shipNode | string | No | The fulfillment center or ship node which uniquely identifies each facility and is retrieved from the Get all third party fulfillment providers API. |
| status | string | No | Status of fulfillment center. Allowed values: ACTIVE, INACTIVE. |
