---
title: Get_Shipping_Template_Activation_Status
category: Settings_Management
api_name: Get_Shipping_Template_Activation_Status
method: GET
path: /v3/settings/shipping/templates/activationStatus
---

**Category:** Settings_Management
**API:** Get_Shipping_Template_Activation_Status

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/settings/shipping/templates/activationStatus

## API Description
Get Shipping Template Activation Status

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| activationStatus | string | No | Shipping Template Activation Status, possible values can be NOT_ACTIVATED or ACTIVATED |
| createdDate | number | No | Activation Date |
| modifiedDate | number | No | Activation Status Last Modified Date |
