---
title: All_subscriptions
category: Notifications_Management
api_name: All_subscriptions
method: GET
path: /v3/webhooks/subscriptions
---

**Category:** Notifications_Management
**API:** All_subscriptions

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/webhooks/subscriptions

## API Description
All subscriptions

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| subscriptionId (query) | string | No | Use this to get details of a specific subscription |
| eventType (query) | string | No | Use this to get list of all subscriptions for a specific event type. Refer to Events section for list of available eventType. |
| resourceName (query) | string | No | Use this to get list of all subscriptions for a specific resource. Refer to Events section for list of available resourceName. |
| status (query) | string | No | Use this to get list of all subscriptions in ACTIVE or INACTIVE status |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| events | array<object> | No | List of events |
| events.event | array<object> | No |  |
| events.event.eventType | string | No | Event for which the subscription is created |
| events.event.subscriptionId | string | No | Unique ID for the subscription that can be used for fetching details, editing or deleting the subscription |
| events.event.partnerId | string | No | Partner ID of the seller who created the subscription |
| events.event.eventVersion | string | No | Version of the event type for which the subscription is created |
| events.event.resourceName | string | No | Delegated access scope that event type is mapped to. |
| events.event.status | string | No | ACTIVE or INACTIVE status of the subscription |
| events.event.eventUrl | string | No | Destination URL where notification will be received by seller |
| events.event.authDetails | object | No | Authentication details for accessing the destination URL, if URL is protected |
| events.event.authDetails.authMethod | string | No | enumeration: BASIC_AUTH,OAUTH,HMAC |
| events.event.authDetails.userName | string | No | UserName to access destination URL |
| events.event.authDetails.password | string | No | Password to access destination URL |
| events.event.authDetails.authHeaderName | string | No | authHeaderName , using which authorization header will be passed |
| events.event.authDetails.authUrl | string | No | OAUTH URL |
| events.event.authDetails.clientSecret | string | No | Client Secret for OAUTH URL / HMAC |
| events.event.authDetails.clientId | string | No | ClientId for OAUTH URL |
| events.event.headers | object | No | Headers required for accessing the destination URL |
| events.event.headers.content-type | string | No |  |
