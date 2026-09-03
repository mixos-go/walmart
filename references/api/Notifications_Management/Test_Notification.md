---
title: Test_Notification
category: Notifications_Management
api_name: Test_Notification
method: POST
path: /v3/webhooks/test
---

**Category:** Notifications_Management
**API:** Test_Notification

**Method:** POST
**HTTP Path:** https://marketplace.walmartapis.com/v3/webhooks/test

## API Description
Test Notification

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
| eventType | string | Yes | Event that you want to subscribe to |
| eventVersion | string | Yes | Version of the specific event type |
| resourceName | string | Yes | Functional category that event type is mapped to. |
| eventUrl | string | Yes | Destination URL where notification will be received by seller |
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

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| message | string | No | Message confirming that the eventURL is validated |
