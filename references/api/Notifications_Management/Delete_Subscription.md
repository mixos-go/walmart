---
title: Delete_Subscription
category: Notifications_Management
api_name: Delete_Subscription
method: DELETE
path: /v3/webhooks/subscriptions/{subscriptionId}
---

**Category:** Notifications_Management
**API:** Delete_Subscription

**Method:** DELETE
**HTTP Path:** https://marketplace.walmartapis.com/v3/webhooks/subscriptions/{subscriptionId}

## API Description
Delete Subscription

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| subscriptionId (path) | string | Yes | Unique ID for the subscription |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| subscriptionId | string | No | Subscription Id of the subscription that is deleted |
| message | string | No | Message confirming that the subscription has been deleted |
