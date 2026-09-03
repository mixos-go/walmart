---
title: Get_Shipping_Configurations
category: Settings_Management
api_name: Get_Shipping_Configurations
method: GET
path: /v3/settings/shippingprofile
---

**Category:** Settings_Management
**API:** Get_Shipping_Configurations

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/settings/shippingprofile

## API Description
Get Shipping Configurations

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
| partner | object | No | Details of partner |
| partner.partnerId | string | No | The seller ID |
| partner.partnerName | string | No | The seller's legal name |
| partner.partnerDisplayName | string | No | The seller name shown on walmart.com |
| partner.partnerStoreId | string | No | Partner/Seller ID for Walmart store URL |
| configurations | array<object> | No | List of seller configurations like Lag Time |
| configurations.configurationName | string | No | Name of the configuration (LAG_TIME) |
| configurations.configuration | object | No |  |
| configurations.configuration.categories | array<object> | No | List of item setup category level lag time exceptions configured for seller |
| configurations.configuration.categories.name | string | No | Name of the item setup category which was used to request lag time exception |
| configurations.configuration.categories.fulfillmentLagTime | integer | No | Maximum lag time configured for the item setup category |
