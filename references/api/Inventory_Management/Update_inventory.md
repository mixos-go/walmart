---
title: Update_inventory
category: Inventory_Management
api_name: Update_inventory
method: PUT
path: /v3/inventory
---

**Category:** Inventory_Management
**API:** Update_inventory

**Method:** PUT
**HTTP Path:** https://marketplace.walmartapis.com/v3/inventory

## API Description
Update inventory

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| sku (query) | string | Yes | An arbitrary alphanumeric unique ID, specified by the seller, which identifies each item. This will be used by the seller in the XSD file to refer to each item. Special characters in the sku needing encoding are: ':', '/', '?', '#', '[', ']', '@', '!', '$', '&', "'", '(', ')', '*', '+', ',', ';', '= |
| shipNode (query) | string | No | The shipNode for which the inventory is to be updated. |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| sku | string | Yes | A seller-provided Product ID. Response will have decoded value. |
| quantity | object | Yes | Quantity that has been ordered by the customers but not yet shipped |
| quantity.unit | string | No | The unit of measurement. Example: 'EACH' (EACH) |
| quantity.amount | number | No | Inventory Count |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| sku | string | Yes | A seller-provided Product ID. Response will have decoded value. |
| quantity | object | Yes | Quantity that has been ordered by the customers but not yet shipped |
| quantity.unit | string | No | The unit of measurement. Example: 'EACH' (EACH) |
| quantity.amount | number | No | Inventory Count |
