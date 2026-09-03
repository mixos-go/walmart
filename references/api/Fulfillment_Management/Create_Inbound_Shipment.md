---
title: Create_Inbound_Shipment
category: Fulfillment_Management
api_name: Create_Inbound_Shipment
method: POST
path: /v3/fulfillment/inbound-shipments
---

**Category:** Fulfillment_Management
**API:** Create_Inbound_Shipment

**Method:** POST
**HTTP Path:** https://marketplace.walmartapis.com/v3/fulfillment/inbound-shipments

## API Description
Create Inbound Shipment

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
| inboundOrderId | string | Yes | Unique ID identifying inbound shipment request |
| returnAddress | object | Yes | return address of seller |
| returnAddress.addressLine1 | string | No | Address details |
| returnAddress.addressLine2 | string | No | Address details continuation |
| returnAddress.city | string | No | City name |
| returnAddress.stateCode | string | No | State Code |
| returnAddress.countryCode | string | No | Country code |
| returnAddress.postalCode | string | No | Zip code |
| orderItems | array<object> | No | inbound shipment request line items |
| orderItems.productId | string | No | Unique ID identifying product |
| orderItems.productType | string | No | Supported product types are GTIN,UPC,EAN |
| orderItems.sku | string | No | Seller Item ID |
| orderItems.itemDesc | string | No | Item description |
| orderItems.itemQty | integer | No | Total number of sellable units |
| orderItems.vendorPackQty | integer | No | Total number of cases |
| orderItems.innerPackQty | integer | No | Total number of sellable units per case |
| orderItems.expectedDeliveryDate | date-time | No | expected delivery date for shipment |
| orderItems.addOnServices | array<string> | No | Indicate whether add-on services (e.g. item labeling or poly bagging) are needed |
| orderItems.itemNbr | integer | No |  |
| orderItems.dimensions | array<number> | No |  |
| orderItems.itemWeightQty | number | No |  |
| orderItems.nonSortItem | boolean | No |  |
| orderItems.shipNode | string | No |  |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| status | string | No |  |
| payload | array<object> | No | response payload |
| payload.shipmentId | string | No | Unique ID identifying each shipment |
| payload.shipToAddress | object | No | The address to which sellers need to inbound items |
| payload.shipToAddress.fcName | string | No | Facility name |
| payload.shipToAddress.addressLine1 | string | No | Address details |
| payload.shipToAddress.addressLine2 | string | No | Address details continuation |
| payload.shipToAddress.city | string | No | City name |
| payload.shipToAddress.stateCode | string | No | State code |
| payload.shipToAddress.countryCode | string | No | Country code |
| payload.shipToAddress.postalCode | string | No | Zip code |
| payload.shipmentItems | array<object> | No | The items which needs to be send in the shipment |
| payload.shipmentItems.vendorSku | string | No | Seller Item ID |
| payload.shipmentItems.itemQty | integer | No | Total number of sellable units |
| payload.expectedDeliveryDate | date-time | No | expected delivery date for inbounding shipment. Can be different from provided in the rquest based on network capacity |
