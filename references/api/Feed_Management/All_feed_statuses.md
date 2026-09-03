---
title: All_feed_statuses
category: Feed_Management
api_name: All_feed_statuses
method: GET
path: /v3/feeds
---

**Category:** Feed_Management
**API:** All_feed_statuses

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/feeds

## API Description
All feed statuses

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| feedId (query) | string | No | A unique ID returned from the Bulk Upload API, used for tracking the Feed File. Special characters must be escaped. (e.g., feedId: '...3456@789...' must be entered in the URL as '...3456%40789). |
| offset (query) | string | No | The object response to start with, where 0 is the first entity that can be requested. It can only be used when includeDetails is set to true. |
| limit (query) | string | No | The number of entities to be returned. It cannot be more than 50 entities. Use it only when the includeDetails is set to true. |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| errors | array<object> | No |  |
| errors.code | string | No |  |
| errors.field | string | No |  |
| errors.description | string | No |  |
| errors.info | string | No |  |
| errors.severity | string | No |  (INFO, WARN, ERROR) |
| errors.category | string | No |  (APPLICATION, SYSTEM, REQUEST, DATA) |
| errors.causes | array<object> | No |  |
| errors.causes.code | string | No |  |
| errors.causes.field | string | No |  |
| errors.causes.type | string | No |  |
| errors.causes.description | string | No |  |
| errors.errorIdentifiers | object | No |  |
| errors.component | string | No |  |
| errors.type | string | No |  |
| errors.serviceName | string | No |  |
| errors.gatewayErrorCategory | string | No |  (INTERNAL_DATA_ERROR, EXTERNAL_DATA_ERROR, SYSTEM_ERROR) |
| totalResults | integer | No | Total number of feeds returned |
| offset | integer | No | The object response to the starting number, where 0 is the first available |
| limit | integer | No | The number of items to be returned |
| results | object | No | The feed status results |
| results.feed | array<object> | No | The feed status results |
| results.feed.feedId | string | No | A unique ID used for tracking the Feed File |
| results.feed.feedSource | string | No | The source of the feed |
| results.feed.feedType | string | No | The feed type |
| results.feed.partnerId | string | No | The seller ID |
| results.feed.itemsReceived | integer | No | The number of items received |
| results.feed.itemsSucceeded | integer | No | The number of items in the feed that have successfully processed |
| results.feed.itemsFailed | integer | No | The number of items in the feed that failed due to a data or system error |
| results.feed.itemsProcessing | integer | No | The number of items in the feed that are still in progress |
| results.feed.feedStatus | string | No | Can be one of the following: RECEIVED, INPROGRESS, PROCESSED, or ERROR. For details, see the definitions listed under 'Feed Statuses' at the beginning of this section. |
| results.feed.feedDate | integer | No | The date and time the feed was submitted. Format: yyyymmddThh:mm:ss.xxxz |
| results.feed.batchId | string | No | The batch ID for the feed, if provided |
| results.feed.modifiedDtm | integer | No | The most recent time the feed was modified. Format: yyyymmddThh:mm:ss.xxxz |
