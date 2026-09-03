---
title: Get_all_areas
category: Rules_Management
api_name: Get_all_areas
method: GET
path: /v3/rules/areas
---

**Category:** Rules_Management
**API:** Get_all_areas

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/rules/areas

## API Description
Get all areas

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
| status | string | No | Status of the rule post the rule creation. |
| payload | object | No |  |
| payload.entities | array<object> | No |  |
| payload.entities.states | array<object> | No | states. |
| payload.entities.states.stateSubregions | array<object> | No | statesubregions |
| payload.entities.states.stateSubregions.stateSubregionCode | string | No | stateSubregionCode |
| payload.entities.states.stateSubregions.stateSubregionName | string | No | stateSubregionName |
| payload.entities.regionCode | string | No | regionCode |
| payload.entities.regionName | string | No | regionName |
