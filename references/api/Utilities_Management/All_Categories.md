---
title: All_Categories
category: Utilities_Management
api_name: All_Categories
method: GET
path: /v3/utilities/taxonomy/departments/{departmentId}
---

**Category:** Utilities_Management
**API:** All_Categories

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/utilities/taxonomy/departments/{departmentId}

## API Description
All Categories

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| departmentId (path) | string | Yes | departmentId |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| status | string | No |  |
| response | object | No |  |
| response.departmentName | string | No | The department name for which the categories have to be fetched |
| response.departmentId | string | No | The department id for which the categories have to be fetched |
| response.category | array<object> | No |  |
| response.category.categoryName | string | No | The category name for which the top trending items have to be fetched |
| response.category.categoryId | string | No | The category id for which the top trending items have to be fetched |
