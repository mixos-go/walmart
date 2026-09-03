---
title: Get_Partner_Configurations
category: Settings_Management
api_name: Get_Partner_Configurations
method: GET
path: /v3/settings/partnerprofile
---

**Category:** Settings_Management
**API:** Get_Partner_Configurations

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/settings/partnerprofile

## API Description
Get Partner Configurations

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
| configurations | array<object> | No | List of seller configurations like Seller Account & feed throttling values |
| configurations.configurationName | string | No | Name of the configuration. Allowed value is ACCOUNT |
| configurations.configuration | object | No |  |
| configurations.configuration.status | string | No | Status of Seller Account (ACTIVE, ONBOARDING_ACTIVE, ONBOARDING_INACTIVE, SUSPENDED, TNS_DECLINED, TERMINATED) |
