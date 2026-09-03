---
title: Get_Inbound_Shipment_errors
category: Fulfillment_Management
api_name: Get_Inbound_Shipment_errors
method: GET
path: /v3/fulfillment/inbound-shipment-errors
---

**Category:** Fulfillment_Management
**API:** Get_Inbound_Shipment_errors

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/fulfillment/inbound-shipment-errors

## API Description
Get Inbound Shipment errors

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| offset (query) | string | No | offset is the number of records you wish to skip before selecting records. |
| limit (query) | string | No | The number of Purchase Orders to be returned. |
| shipmentId (query) | string | No | Unique ID identifying each shipment. |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| headers | object | No |  |
| headers.totalCount | integer | No | total number of POs for provided GET request. |
| headers.limit | integer | No | provided limit value in the request |
| headers.offset | integer | No | provided offset value in the request. |
| payload | array<object> | No | response payload |
| payload.inboundOrderId | string | No | Unique ID identifying inbound shipment requests |
| payload.createdDate | date-time | No | created date for the request |
| payload.returnAddress | object | No | return address of seller |
| payload.returnAddress.addressLine1 | string | No | Address details |
| payload.returnAddress.addressLine2 | string | No | Address details continuation |
| payload.returnAddress.city | string | No | City name |
| payload.returnAddress.stateCode | string | No | State Code |
| payload.returnAddress.countryCode | string | No | Country code |
| payload.returnAddress.postalCode | string | No | Zip code |
| payload.orderItems | array<object> | No | inbound shipment request line items |
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
| payload.errors | array<object> | No | Error in inbound shipment creation |
| payload.errors.code | string | No |  |
| payload.errors.field | string | No |  |
| payload.errors.description | string | No |  |
| payload.errors.info | string | No |  |
| payload.errors.severity | string | No |  (INFO, WARN, ERROR) |
| payload.errors.category | string | No |  (APPLICATION, SYSTEM, REQUEST, DATA) |
| payload.errors.causes | array<object> | No |  |
| payload.errors.causes.code | string | No |  |
| payload.errors.causes.field | string | No |  |
| payload.errors.causes.type | string | No |  |
| payload.errors.causes.description | string | No |  |
