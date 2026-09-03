---
title: Retire_an_item
category: Item_Management
api_name: Retire_an_item
method: DELETE
path: /v3/items/{SKU}
---

**Category:** Item_Management
**API:** Retire_an_item

**Method:** DELETE
**HTTP Path:** https://marketplace.walmartapis.com/v3/items/{SKU}

## API Description
Retire an item

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| SKU (path) | string | Yes | An arbitrary alphanumeric unique ID, specified by the seller, which identifies each item. This will be used by the seller in the XSD file to refer to each item. Special characters in the sku needing encoding are: ':', '/', '?', '#', '[', ']', '@', '!', '$', '&', "'", '(', ')', '*', '+', ',', ';', '= |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| sku | string | Yes | An arbitrary alphanumeric unique ID, specified by the seller, which identifies each item. |
| message | string | No | Message confirming the deletion or retirement of an item from the Walmart Catalog |
