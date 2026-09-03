---
title: All_Departments
category: Utilities_Management
api_name: All_Departments
method: GET
path: /v3/utilities/taxonomy/departments
---

**Category:** Utilities_Management
**API:** All_Departments

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/utilities/taxonomy/departments

## API Description
All Departments

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
| status | string | No |  |
| payload | array<object> | No |  |
| payload.superDepartment | string | No | The super-department name for which the department have to be fetched |
| payload.superDepartmentId | string | No | The super-department id for which the department have to be fetched |
| payload.departments | array<object> | No |  |
| payload.departments.departmentName | string | No | The department name for which the categories have to be fetched |
| payload.departments.departmentId | string | No | The department id for which the categories have to be fetched |
