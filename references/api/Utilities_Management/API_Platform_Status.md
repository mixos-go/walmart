---
title: API_Platform_Status
category: Utilities_Management
api_name: API_Platform_Status
method: GET
path: /v3/utilities/apiStatus
---

**Category:** Utilities_Management
**API:** API_Platform_Status

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/utilities/apiStatus

## API Description
API Platform Status

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
| apiStatuses | array<object> | No | A-List of all API statuses |
| apiStatuses.apiGroup | string | No | The marketplace api group (Returns, Items, Sandbox, Lagtime, Promos, Orders, Authentication, Price, Refunds, Authorization, Inventory) |
| apiStatuses.status | string | No | The current status of marketplace api group (OPERATIONAL, SERVICE_DEGRADATION, SERVICE_OUTAGE, UNKNOWN) |
| apiStatuses.lastUpdatedTime | string | No | The time at which the status of api group collected. This datetime field is in the ISO 8601 format. |
