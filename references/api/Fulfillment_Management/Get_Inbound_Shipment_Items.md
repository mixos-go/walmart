---
title: Get_Inbound_Shipment_Items
category: Fulfillment_Management
api_name: Get_Inbound_Shipment_Items
method: GET
path: /v3/fulfillment/inbound-shipment-items
---

**Category:** Fulfillment_Management
**API:** Get_Inbound_Shipment_Items

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/fulfillment/inbound-shipment-items

## API Description
Get Inbound Shipment Items

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
| payload.inboundOrderId | string | No | Unique ID identifying inbound shipment request |
| payload.shipmentId | string | No | Unique ID identifying each shipment |
| payload.gtin | string | No | Item barcode |
| payload.sku | string | No | Seller Item ID |
| payload.itemDesc | string | No | Item description |
| payload.itemQty | integer | No | Total number of sellable units |
| payload.vendorPackQty | integer | No | Total number of cases |
| payload.innerPackQty | integer | No | Total number of sellable units per case |
| payload.receivedQty | integer | No | Qty received in FC |
| payload.damagedQty | integer | No | Qty damaged while receiving in FC |
| payload.fillRate | number | No | Fill rate for this shipment item |
| payload.expectedDeliveryDate | date-time | No | expected delivery date provided by seller |
| payload.updatedExpectedDeliveryDate | date-time | No | update expected delivery date based on network capacity |
| payload.shipNodeName | string | No | FC name |
