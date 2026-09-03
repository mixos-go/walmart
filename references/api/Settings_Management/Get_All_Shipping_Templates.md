---
title: Get_All_Shipping_Templates
category: Settings_Management
api_name: Get_All_Shipping_Templates
method: GET
path: /v3/settings/shipping/templates
---

**Category:** Settings_Management
**API:** Get_All_Shipping_Templates

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/settings/shipping/templates

## API Description
Get All Shipping Templates

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
| shippingTemplates | array<object> | No | Array of Shipping Templates |
| shippingTemplates.id | string | No | Shipping Template ID |
| shippingTemplates.name | string | No | Shipping Template Name |
| shippingTemplates.type | string | No | Shipping Template Type (DEFAULT, CUSTOM, DELIVERR) |
| shippingTemplates.status | string | No | Shipping Template/ Configurations active or inactive status (ACTIVE, INACTIVE) |
| shippingTemplates.rateModelType | string | No |  (TIERED_PRICING, PER_SHIPMENT_PRICING) |
| shippingTemplates.createdBy | string | No |  |
| shippingTemplates.modifiedBy | string | No |  |
| shippingTemplates.createdDate | number | No | Template Creation Date |
| shippingTemplates.modifiedDate | number | No | Template Modified Date |
| totalRecords | number | No | Total Number of records in the response of the API |
