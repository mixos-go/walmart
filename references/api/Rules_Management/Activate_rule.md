---
title: Activate_rule
category: Rules_Management
api_name: Activate_rule
method: PUT
path: /v3/rules/activate
---

**Category:** Rules_Management
**API:** Activate_rule

**Method:** PUT
**HTTP Path:** https://marketplace.walmartapis.com/v3/rules/activate

## API Description
Activate rule

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
| ruleHeader | object | No |  |
| ruleHeader.version | string | No |  |
| rules | array<object> | No |  |
| rules.ruleId | string | No | Unique identifier of the rule created for custom rule assortment. |
| rules.ruleStatus | string | No | Status of the rule post the rule creation. Allowed values are Active, Inactive, Submitted. |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| message | string | No | Message and ruleId |
| status | string | No | status |
