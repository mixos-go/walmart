---
title: Cancel_Customer_Order
category: Fulfillment_Management
api_name: Cancel_Customer_Order
method: POST
path: /v3/orders-fulfillments/cancel
---

**Category:** Fulfillment_Management
**API:** Cancel_Customer_Order

**Method:** POST
**HTTP Path:** https://marketplace.walmartapis.com/v3/orders-fulfillments/cancel

## API Description
Cancel Customer Order

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
| header | object | Yes | header to support build and martId |
| header.headerAttributes | object | No | Header attributes |
| header.headerAttributes.martId | string | No | martId of the seller |
| header.headerAttributes.buId | string | No | buId of the seller |
| payload | object | No | request payload |
| payload.sellerOrderId | string | No |  |
| payload.orderItems | array<object> | No |  |
| payload.orderItems.sellerLineId | string | No |  |
| payload.orderItems.qty | object | No |  |
| payload.orderItems.qty.unitOfMeasure | string | No |  |
| payload.orderItems.qty.measurementValue | number | No |  |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| status | string | No | status |
| header | object | No | header to support build and martId |
| header.headerAttributes | object | No | Header attributes |
| header.headerAttributes.martId | string | No | martId of the seller |
| header.headerAttributes.buId | string | No | buId of the seller |
| payload | object | No | response payload |
| payload.requestId | string | No | Unique ID identifying each request |
