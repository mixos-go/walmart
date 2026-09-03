---
title: WFS_Inventory
category: Inventory_Management
api_name: WFS_Inventory
method: GET
path: /v3/fulfillment/inventory
---

**Category:** Inventory_Management
**API:** WFS_Inventory

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/fulfillment/inventory

## API Description
WFS Inventory

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| sku (query) | string | No | An arbitrary alphanumeric unique ID, specified by the seller, which identifies each item. This will be used by the seller in the XSD file to refer to each item. Special characters in the sku needing encoding are: ':', '/', '?', '#', '[', ']', '@', '!', '$', '&', "'", '(', ')', '*', '+', ',', ';', '= |
| fromModifiedDate (query) | string | No | last inventory modified date - starting range. |
| toModifiedDate (query) | string | No | last inventory modified date - starting range. |
| limit (query) | string | No | Number of Sku to be returned. Cannot be larger than 300. |
| offset (query) | string | No | Offset is the number of records you wish to skip before selecting records. |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| headers | object | No |  |
| headers.totalCount | integer | No | Total number of results for query. |
| headers.limit | integer | No | Information about the quantity in inventory |
| headers.offset | integer | No | Offset is the number of records you wish to skip before selecting results. |
| payload | object | No |  |
| payload.inventory | array<object> | No |  |
| payload.inventory.sku | string | No | An arbitrary alphanumeric unique ID, specified by the seller, which identifies each item. |
| payload.inventory.shipNodes | array<object> | No |  |
| payload.inventory.shipNodes.modifiedDate | string | No | Last changes date for the item. |
| payload.inventory.shipNodes.availToSellQty | integer | No | The available quantity is the quantity of an item that is available to be allocated to orders. |
| payload.inventory.shipNodes.onHandQty | integer | No | The on-hand balance is the quantity of active inventory stored at the warehouse.Active inventory is defined as the usable amount of an item that is in the warehouse.Inventory is active if it is not damaged, expired or being inspected. |
| payload.inventory.shipNodes.shipNodeType | string | No | Identifies fulfillment aspect of invetory. Walmart, seller or 3PL fulfilled. Possible value is 'WFSFulfilled'. In later phase we will also add seller fulfilled inventory. |
