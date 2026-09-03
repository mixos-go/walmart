---
title: Set_up_CAP_SKU_All
category: Price_Management
api_name: Set_up_CAP_SKU_All
method: POST
path: /v3/cppreference
---

**Category:** Price_Management
**API:** Set_up_CAP_SKU_All

**Method:** POST
**HTTP Path:** https://marketplace.walmartapis.com/v3/cppreference

## API Description
Set up CAP SKU All

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| subsidyEnrolled | boolean | No | A Boolean parameter that allows all sellers to completely enroll in or out of the Competitive Price Adjustment program |
| subsidyPreference | boolean | No | A Boolean parameter that determines whether offer level subsidy setting override seller level subsidy setting |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| martId | string | No | A unique ID that a user or seller uses for a marketplace. |
| statusInfo | object | No |  |
| statusInfo.subsidyEnrolled | boolean | No | A Boolean parameter that allows all sellers to completely enroll in or out of the Competitive Price Adjustment program |
| statusInfo.subsidyPreference | boolean | No | A Boolean parameter that determines whether offer level subsidy setting override seller level subsidy setting |
