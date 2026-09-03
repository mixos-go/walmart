---
title: Get_Shipments
category: Fulfillment_Management
api_name: Get_Shipments
method: GET
path: /v3/fulfillment/inbound-shipments
---

**Category:** Fulfillment_Management
**API:** Get_Shipments

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/fulfillment/inbound-shipments

## API Description
Get Shipments

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| offset (query) | string | No | offset is the number of records you wish to skip before selecting records. |
| limit (query) | string | No | The number of Purchase Orders to be returned. |
| inboundOrderId (query) | string | No | Unique ID identifying inbound shipment request. |
| shipmentId (query) | string | No | Unique ID identifying each shipment. |
| status (query) | string | No | Current shipment status |
| fromCreateDate (query) | string | No | Shipment create date starting range |
| toCreateDate (query) | string | No | Shipment create date starting end range |
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
| payload.shipmentId | string | No | Unique ID identifying inbound shipment |
| payload.shipToAddress | object | No | The address to which sellers need to inbound items |
| payload.shipToAddress.fcName | string | No | Facility name |
| payload.shipToAddress.addressLine1 | string | No | Address details |
| payload.shipToAddress.addressLine2 | string | No | Address details continuation |
| payload.shipToAddress.city | string | No | City name |
| payload.shipToAddress.stateCode | string | No | State code |
| payload.shipToAddress.countryCode | string | No | Country code |
| payload.shipToAddress.postalCode | string | No | Zip code |
| payload.returnAddress | object | No | return address of seller |
| payload.returnAddress.addressLine1 | string | No | Address details |
| payload.returnAddress.addressLine2 | string | No | Address details continuation |
| payload.returnAddress.city | string | No | City name |
| payload.returnAddress.stateCode | string | No | State Code |
| payload.returnAddress.countryCode | string | No | Country code |
| payload.returnAddress.postalCode | string | No | Zip code |
| payload.status | string | No | Current status of the shipment |
| payload.createdDate | date-time | No | creation date for shipment |
| payload.shipmentUnits | integer | No | Total number of units in the shipment |
| payload.receivedUnits | integer | No | Total number of units recived in FC for the shipment |
| payload.expectedDeliveryDate | date-time | No | expected delivery date provided by seller |
| payload.updatedExpectedDeliveryDate | date-time | No | update expected delivery date based on network capacity |
| payload.actualDeliveryDate | date-time | No | Actual delivery date of the shipment at FC |
| payload.trackingNo | array<string> | No | Tracking info for the shipment |
| payload.carrierName | string | No | Carrier of the shipment |
