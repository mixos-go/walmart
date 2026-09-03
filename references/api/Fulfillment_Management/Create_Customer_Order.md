---
title: Create_Customer_Order
category: Fulfillment_Management
api_name: Create_Customer_Order
method: POST
path: /v3/orders-fulfillments
---

**Category:** Fulfillment_Management
**API:** Create_Customer_Order

**Method:** POST
**HTTP Path:** https://marketplace.walmartapis.com/v3/orders-fulfillments

## API Description
Create Customer Order

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
| payload | object | Yes | request payload |
| payload.orderChannelId | string | No | Unique ID identifying channels from where the orders have been generated |
| payload.sellerOrderId | string | No | Unique ID identifying customer order request |
| payload.orderPlacedTime | date-time | No | Order placed time at respective channels |
| payload.needsConfirmation | boolean | No | Flag to identify if confirmation is needed |
| payload.partialFulfillments | boolean | No | Flag to identify if partial fulfilment is allowed |
| payload.customer | object | No |  |
| payload.customer.customerId | string | No |  |
| payload.customer.customerName | string | No |  |
| payload.orderItems | array<object> | No | Order items details |
| payload.orderItems.productId | string | No | Unique ID identifying product |
| payload.orderItems.productType | string | No | Supported product types are GTIN,UPC,EAN |
| payload.orderItems.sku | string | No | Seller Item ID |
| payload.orderItems.itemDesc | string | No | Item description |
| payload.orderItems.itemQty | integer | No | Total number of sellable units |
| payload.orderItems.vendorPackQty | integer | No | Total number of cases |
| payload.orderItems.innerPackQty | integer | No | Total number of sellable units per case |
| payload.orderItems.expectedDeliveryDate | date-time | No | expected delivery date for shipment |
| payload.orderItems.addOnServices | array<string> | No | Indicate whether add-on services (e.g. item labeling or poly bagging) are needed |
| payload.orderItems.itemNbr | integer | No |  |
| payload.orderItems.dimensions | array<number> | No |  |
| payload.orderItems.itemWeightQty | number | No |  |
| payload.orderItems.nonSortItem | boolean | No |  |
| payload.orderItems.shipNode | string | No |  |

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
