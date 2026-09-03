---
title: Issue_refund
category: Returns_Management
api_name: Issue_refund
method: POST
path: /v3/returns/{returnOrderId}/refund
---

**Category:** Returns_Management
**API:** Issue_refund

**Method:** POST
**HTTP Path:** https://marketplace.walmartapis.com/v3/returns/{returnOrderId}/refund

## API Description
Issue refund

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| returnOrderId (path) | string | Yes | The return order ID |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| customerOrderId | string | Yes | A unique ID associated with the sales order for specified customer |
| refundLines | array<object> | Yes | Array of refund lines. |
| refundLines.returnOrderLineNumber | integer | No | A line number associated with each individual line in the return order. If return order has only one return order line and it is not provided in the request, the only available return order line is auto-selected. If return order has multiple return order lines, the required return order line must be |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| returnOrderId | string | No | The return order id |
| customerOrderId | string | No | A unique ID associated with the sales order for specified customer |
| refundLines | array<object> | No | Array of refund lines |
| refundLines.returnOrderLineNumber | integer | No | A line number associated with each individual line in the return order. If return order has only one return order line and it is not provided in the request, the only available return order line is auto-selected. If return order has multiple return order lines, the required return order line must be |
