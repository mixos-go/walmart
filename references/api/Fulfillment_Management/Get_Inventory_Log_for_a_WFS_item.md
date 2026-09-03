---
title: Get_Inventory_Log_for_a_WFS_item
category: Fulfillment_Management
api_name: Get_Inventory_Log_for_a_WFS_item
method: GET
path: /v3/fulfillment/inventory-log
---

**Category:** Fulfillment_Management
**API:** Get_Inventory_Log_for_a_WFS_item

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/fulfillment/inventory-log

## API Description
Get Inventory Log for a WFS item

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| gtin (query) | string | Yes | GTIN. |
| shipmentId (query) | string | No | Shipment Id. |
| transactionType (query) | string | No | Transaction Type. |
| transactionLocation (query) | string | No | Transaction Location. |
| startDate (query) | string | No | Inventory log transaction time starting range (Date in YYYY-MM-DD format). |
| endDate (query) | string | No | Inventory log transaction time ending range (Date in YYYY-MM-DD format). |
| sort_by (query) | string | No | Sort By Attribute (Supported Attributes: gtin, changedUnits, transactionReasonCode, transactionType, shipmentId). |
| sort_order (query) | string | No | Sort Order (ASC or DESC). |
| offset (query) | string | No | Offset is the number of records you wish to skip before selecting records. |
| limit (query) | string | No | limit is the number of records to be returned. |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| headers | object | No | Headers Section |
| headers.limit | integer | No | Number of records to be returned |
| headers.offset | integer | No | Number of records you wish to skip before selecting records |
| headers.totalCount | integer | No | Total Count of records this request yields |
| payload | object | No | Payload Section |
| payload.gtin | string | No | GTIN |
| payload.vendorSku | string | No | Vendor SKU |
| payload.productName | string | No | Product Name |
| payload.inventoryLog | array<object> | No | Inventory Log records |
| payload.inventoryLog.id | string | No | Unique Event Id |
| payload.inventoryLog.fcName | string | No | Fulfillment Center Short Name |
| payload.inventoryLog.changedUnits | integer | No | Number of inventory units changed +/- in FC as a result of this transaction |
| payload.inventoryLog.transactionTime | date-time | No | Timestamp of transaction |
| payload.inventoryLog.transactionLocation | string | No | Transaction Location |
| payload.inventoryLog.transactionReasonCode | string | No | Transaction Reason Code |
| payload.inventoryLog.transactionReasonDesc | string | No | Transaction Reason Description |
| payload.inventoryLog.transactionType | string | No | Transaction Type |
| payload.inventoryLog.shipmentId | string | No | Shipment Id |
