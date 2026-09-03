---
title: Update_Item_Inventory_per_Ship_Node
category: Inventory_Management
api_name: Update_Item_Inventory_per_Ship_Node
method: PUT
path: /v3/inventories/{sku}
---

**Category:** Inventory_Management
**API:** Update_Item_Inventory_per_Ship_Node

**Method:** PUT
**HTTP Path:** https://marketplace.walmartapis.com/v3/inventories/{sku}

## API Description
Update Item Inventory per Ship Node

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| sku (path) | string | Yes | An arbitrary alphanumeric unique ID, specified by the seller, which identifies each item. This will be used by the seller in the XSD file to refer to each item. Special characters in the sku needing encoding are: ':', '/', '?', '#', '[', ']', '@', '!', '$', '&', "'", '(', ')', '*', '+', ',', ';', '= |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| inventories | object | Yes |  |
| inventories.nodes | array<object> | No |  |
| inventories.nodes.shipNode | string | No | ShipNode Id of the ship node for which the inventory is requested |
| inventories.nodes.inputQty | object | No | Quantity that has been ordered by the customers but not yet shipped |
| inventories.nodes.inputQty.unit | string | No | The unit of measurement. Example: 'EACH' (EACH) |
| inventories.nodes.inputQty.amount | number | No | Inventory Count |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| sku | string | No | An arbitrary alphanumeric unique ID, specified by the seller, which identifies each item. |
| nodes | array<object> | No |  |
| nodes.shipNode | string | No | ShipNode Id of the ship node for which the inventory is requested |
| nodes.status | string | No | Node Update status. Example: 'Success' |
| nodes.errors | array<object> | No | Node Update Error description. |
| nodes.errors.code | string | No |  |
| nodes.errors.field | string | No |  |
| nodes.errors.description | string | No |  |
| nodes.errors.info | string | No |  |
| nodes.errors.severity | string | No |  (INFO, WARN, ERROR) |
| nodes.errors.category | string | No |  (APPLICATION, SYSTEM, REQUEST, DATA) |
| nodes.errors.causes | array<object> | No |  |
| nodes.errors.causes.code | string | No |  |
| nodes.errors.causes.field | string | No |  |
| nodes.errors.causes.type | string | No |  |
| nodes.errors.causes.description | string | No |  |
| nodes.errors.errorIdentifiers | object | No |  |
