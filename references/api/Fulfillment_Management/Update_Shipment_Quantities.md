---
title: Update_Shipment_Quantities
category: Fulfillment_Management
api_name: Update_Shipment_Quantities
method: PUT
path: /v3/fulfillment/shipment-quantities
---

**Category:** Fulfillment_Management
**API:** Update_Shipment_Quantities

**Method:** PUT
**HTTP Path:** https://marketplace.walmartapis.com/v3/fulfillment/shipment-quantities

## API Description
Update Shipment Quantities

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
| shipmentId | string | Yes | Unique ID identifying inbound shipment |
| orderItems | array<object> | No | update shipment qty line items |
| orderItems.sku | string | No | Seller Item ID |
| orderItems.updatedShipmentQty | integer | No | updated quantity |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| status | string | Yes |  (OK, CREATED, ACCEPTED, NO_CONTENT, PARTIAL, MOVED_PERMANENT, FOUND, SEE_OTHER, NOT_MODIFIED, TEMPORARY_REDIRECT, BAD_REQUEST, UNAUTHORIZED, FORBIDDEN, NOT_FOUND, METHOD_NOT_ALLOWED, NOT_ACCEPTABLE, REQUEST_TIMEOUT, CONFLICT, REQUEST_ENTITY_TOO_LARGE, UNSUPPORTED_MEDIA_TYPE, UNPROCESSABLE_ENTITY, FAIL, BAD_GATEWAY, SERVICE_UNAVAILABLE, GATEWAY_TIMEOUT) |
| header | object | No |  |
| header.headerAttributes | object | No |  |
| errors | array<object> | No |  |
| errors.code | string | No |  |
| errors.field | string | No |  |
| errors.description | string | No |  |
| errors.info | string | No |  |
| errors.severity | string | No |  (INFO, WARN, ERROR) |
| errors.category | string | No |  (APPLICATION, SYSTEM, REQUEST, DATA) |
| errors.causes | array<object> | No |  |
| errors.causes.code | string | No |  |
| errors.causes.field | string | No |  |
| errors.causes.type | string | No |  |
| errors.causes.description | string | No |  |
| payload | object | No |  |
