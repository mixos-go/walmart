---
title: Update_Subscription
category: Notifications_Management
api_name: Update_Subscription
method: PATCH
path: /v3/webhooks/subscriptions/{subscriptionId}
---

**Category:** Notifications_Management
**API:** Update_Subscription

**Method:** PATCH
**HTTP Path:** https://marketplace.walmartapis.com/v3/webhooks/subscriptions/{subscriptionId}

## API Description
Update Subscription

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| subscriptionId (path) | string | Yes | Unique ID for the subscription |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| eventType | string | No | Event that is subscribed for notifications. |
| eventVersion | string | No | Version of the specific event type |
| resourceName | string | No | Delegated access scope that event type is mapped to. |
| eventUrl | string | No | Destination URL where notification will be received by seller |
| authDetails | object | No | Authentication details for accessing the destination URL, if URL is protected |
| authDetails.authMethod | string | No | enumeration: BASIC_AUTH,OAUTH,HMAC |
| authDetails.userName | string | No | UserName to access destination URL |
| authDetails.password | string | No | Password to access destination URL |
| authDetails.authHeaderName | string | No | authHeaderName , using which authorization header will be passed |
| authDetails.authUrl | string | No | OAUTH URL |
| authDetails.clientSecret | string | No | Client Secret for OAUTH URL / HMAC |
| authDetails.clientId | string | No | ClientId for OAUTH URL |
| headers | object | No | Headers required for accessing the destination URL |
| headers.content-type | string | No |  |
| status | string | No | Status of the subscription. Allowed values are ACTIVE or INACTIVE |

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
