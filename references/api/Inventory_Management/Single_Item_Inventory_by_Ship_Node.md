---
title: Single_Item_Inventory_by_Ship_Node
category: Inventory_Management
api_name: Single_Item_Inventory_by_Ship_Node
method: GET
path: /v3/inventories/{sku}
---

**Category:** Inventory_Management
**API:** Single_Item_Inventory_by_Ship_Node

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/inventories/{sku}

## API Description
Single Item Inventory by Ship Node

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| sku (path) | string | Yes | An arbitrary alphanumeric unique ID, specified by the seller, which identifies each item. This will be used by the seller in the XSD file to refer to each item. Special characters in the sku needing encoding are: ':', '/', '?', '#', '[', ']', '@', '!', '$', '&', "'", '(', ')', '*', '+', ',', ';', '= |
| shipNode (query) | string | No | ShipNode Id of the ship node for which the inventory is requested |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| sku | string | No | An arbitrary alphanumeric unique ID, specified by the seller, which identifies each item. |
| nodes | array<object> | No |  |
| nodes.shipNode | string | No | ShipNode Id of the ship node for which the inventory is requested |
| nodes.inputQty | object | No | Quantity of an item that is input by the seller |
| nodes.inputQty.unit | string | No | The unit of measurement. Example: 'EACH' (EACH) |
| nodes.inputQty.amount | number | No | Inventory Count |
| nodes.availToSellQty | object | No | Quantity of an item that is available to be allocated to orders |
| nodes.availToSellQty.unit | string | No | The unit of measurement. Example: 'EACH' (EACH) |
| nodes.availToSellQty.amount | number | No | Inventory Count |
| nodes.errors | array<object> | No |  |
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
| nodes.reservedQty | object | No | Quantity that has been ordered by the customers but not yet shipped |
| nodes.reservedQty.unit | string | No | The unit of measurement. Example: 'EACH' (EACH) |
| nodes.reservedQty.amount | number | No | Inventory Count |
