---
title: Recon_report_Legacy
category: Pregenerated_Reports_retiring_on_June_30_2022
api_name: Recon_report_Legacy
method: GET
path: /v3/report/reconreport/reconFile
---

**Category:** Pregenerated_Reports_retiring_on_June_30_2022
**API:** Recon_report_Legacy

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/report/reconreport/reconFile

## API Description
Recon report(Legacy)

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| reportDate (query) | string | Yes | The date for which the reconcilation file is available |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
_No documented response fields._
