---
title: Get_Feed_Error_Report
category: Feed_Management
api_name: Get_Feed_Error_Report
method: GET
path: /v3/feeds/{feedId}/errorReport
---

**Category:** Feed_Management
**API:** Get_Feed_Error_Report

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/feeds/{feedId}/errorReport

## API Description
Get Feed Error Report

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| feedId (path) | string | Yes | Feed Id of the feed |
| feedType (query) | string | Yes | Feed type for which Error Report needs to be downloaded |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
_No documented response fields._
