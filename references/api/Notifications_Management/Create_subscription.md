---
title: Create_subscription
category: Notifications_Management
api_name: Create_subscription
method: POST
path: /v3/webhooks/subscriptions
---

**Category:** Notifications_Management
**API:** Create_subscription

**Method:** POST
**HTTP Path:** https://marketplace.walmartapis.com/v3/webhooks/subscriptions

## API Description
Create subscription

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
| events | array<object> | No |  |
| events.eventType | string | No | Event that you want to subscribe to. For all allowed eventType(s) see Event Payload section or use GET Event Types API |
| events.eventVersion | string | No | Version of the specific event type. For all eventVersion(s) for each eventType, see Event Payload section or use GET Event Types API |
| events.resourceName | string | No | Delegated access scope that event type is mapped to. For all allowed resourceName(s) for each eventType, see Event Payload section or use GET Event Types API |
| events.eventUrl | string | No | Destination URL where notification will be received by seller |
| events.authDetails | object | No | Authentication details for accessing the destination URL, if URL is protected |
| events.authDetails.authMethod | string | No | enumeration: BASIC_AUTH,OAUTH,HMAC |
| events.authDetails.userName | string | No | UserName to access destination URL |
| events.authDetails.password | string | No | Password to access destination URL |
| events.authDetails.authHeaderName | string | No | authHeaderName , using which authorization header will be passed |
| events.authDetails.authUrl | string | No | OAUTH URL |
| events.authDetails.clientSecret | string | No | Client Secret for OAUTH URL / HMAC |
| events.authDetails.clientId | string | No | ClientId for OAUTH URL |
| events.headers | object | No | Headers required for accessing the destination URL |
| events.headers.content-type | string | No |  |
| events.status | string | No | Status of the subscription. Allowed values are ACTIVE or INACTIVE. To create subscription, use status = ACTIVE. Notification will be triggered only if subscription is in ACTIVE status |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| event | array<object> | No |  |
| event.eventType | string | No | Event for which the subscription is created |
| event.subscriptionId | string | No | Unique ID for the subscription that can be used for fetching details, editing or deleting the subscription |
| event.partnerId | string | No | Partner ID of the seller who created the subscription |
| event.eventVersion | string | No | Version of the event type for which the subscription is created |
| event.resourceName | string | No | Delegated access scope that event type is mapped to. |
| event.status | string | No | ACTIVE or INACTIVE status of the subscription |
| event.eventUrl | string | No | Destination URL where notification will be received by seller |
| event.authDetails | object | No | Authentication details for accessing the destination URL, if URL is protected |
| event.authDetails.authMethod | string | No | enumeration: BASIC_AUTH,OAUTH,HMAC |
| event.authDetails.userName | string | No | UserName to access destination URL |
| event.authDetails.password | string | No | Password to access destination URL |
| event.authDetails.authHeaderName | string | No | authHeaderName , using which authorization header will be passed |
| event.authDetails.authUrl | string | No | OAUTH URL |
| event.authDetails.clientSecret | string | No | Client Secret for OAUTH URL / HMAC |
| event.authDetails.clientId | string | No | ClientId for OAUTH URL |
| event.headers | object | No | Headers required for accessing the destination URL |
| event.headers.content-type | string | No |  |
