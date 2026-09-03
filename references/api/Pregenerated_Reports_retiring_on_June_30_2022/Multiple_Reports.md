---
title: Multiple_Reports
category: Pregenerated_Reports_retiring_on_June_30_2022
api_name: Multiple_Reports
method: GET
path: /v3/getReport
---

**Category:** Pregenerated_Reports_retiring_on_June_30_2022
**API:** Multiple_Reports

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/getReport

## API Description
Multiple Reports

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| type (query) | string | Yes | Type of report to be requested |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
_No documented response fields._
