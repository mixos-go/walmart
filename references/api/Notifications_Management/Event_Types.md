---
title: Event_Types
category: Notifications_Management
api_name: Event_Types
method: GET
path: /v3/webhooks/eventTypes
---

**Category:** Notifications_Management
**API:** Event_Types

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/webhooks/eventTypes

## API Description
Event Types

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
| eventTypes | array<object> | No | List of event types |
| eventTypes.resourceName | string | No | Delegated access scope that event type is mapped to. |
| eventTypes.eventType | string | No | Event that you want to subscribe to. |
| eventTypes.eventVersion | string | No | Version of the specific event type |
| eventTypes.description | string | No | Description of the specific event type |
