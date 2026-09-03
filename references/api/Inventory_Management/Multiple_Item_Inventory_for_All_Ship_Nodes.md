---
title: Multiple_Item_Inventory_for_All_Ship_Nodes
category: Inventory_Management
api_name: Multiple_Item_Inventory_for_All_Ship_Nodes
method: GET
path: /v3/inventories
---

**Category:** Inventory_Management
**API:** Multiple_Item_Inventory_for_All_Ship_Nodes

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/inventories

## API Description
Multiple Item Inventory for All Ship Nodes

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| limit (query) | string | No | The number of items returned. Cannot be more than 50. |
| nextCursor (query) | string | No | String returned from initial API call to indicate pagination. Specify nextCursor value to retrieve the next 50 items. |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| meta | object | No |  |
| meta.totalCount | number | No | Total number of Skus of the Seller. Example: '235' |
| meta.nextCursor | string | No | Used for pagination to fetch the next set of items. |
| elements | object | No |  |
| elements.inventories | array<object> | No |  |
| elements.inventories.sku | string | No | An arbitrary alphanumeric unique ID, specified by the seller, which identifies each item. |
| elements.inventories.nodes | array<object> | No |  |
| elements.inventories.nodes.shipNode | string | No | ShipNode Id of the ship node for which the inventory is requested |
| elements.inventories.nodes.inputQty | object | No | Quantity of an item that is input by the seller |
| elements.inventories.nodes.inputQty.unit | string | No | The unit of measurement. Example: 'EACH' (EACH) |
| elements.inventories.nodes.inputQty.amount | number | No | Inventory Count |
| elements.inventories.nodes.availToSellQty | object | No | Quantity of an item that is available to be allocated to orders |
| elements.inventories.nodes.availToSellQty.unit | string | No | The unit of measurement. Example: 'EACH' (EACH) |
| elements.inventories.nodes.availToSellQty.amount | number | No | Inventory Count |
| elements.inventories.nodes.reservedQty | object | No | Quantity that has been ordered by the customers but not yet shipped |
| elements.inventories.nodes.reservedQty.unit | string | No | The unit of measurement. Example: 'EACH' (EACH) |
| elements.inventories.nodes.reservedQty.amount | number | No | Inventory Count |
