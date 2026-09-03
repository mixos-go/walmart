---
title: Available_recon_report_dates_Legacy
category: Pregenerated_Reports_retiring_on_June_30_2022
api_name: Available_recon_report_dates_Legacy
method: GET
path: /v3/report/reconreport/availableReconFiles
---

**Category:** Pregenerated_Reports_retiring_on_June_30_2022
**API:** Available_recon_report_dates_Legacy

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/report/reconreport/availableReconFiles

## API Description
Available recon report dates(Legacy)

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
| availableApReportDates | array<string> | No | All available report dates are returned |
