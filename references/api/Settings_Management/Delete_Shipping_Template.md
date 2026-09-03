---
title: Delete_Shipping_Template
category: Settings_Management
api_name: Delete_Shipping_Template
method: DELETE
path: /v3/settings/shipping/templates/{templateId}
---

**Category:** Settings_Management
**API:** Delete_Shipping_Template

**Method:** DELETE
**HTTP Path:** https://marketplace.walmartapis.com/v3/settings/shipping/templates/{templateId}

## API Description
Delete Shipping Template

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| templateId (path) | string | Yes | Shipping Template ID of the template to be deleted |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| id | string | No | Shipping Template ID |
