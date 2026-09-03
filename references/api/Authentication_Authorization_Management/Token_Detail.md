---
title: Token_Detail
category: Authentication_Authorization_Management
api_name: Token_Detail
method: GET
path: /v3/token/detail
---

**Category:** Authentication_Authorization_Management
**API:** Token_Detail

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/token/detail

## API Description
Token Detail

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| expire_at | string | No | The timestamp when the token expires |
| issued_at | string | No | The timestamp when the token is issued |
| is_valid | boolean | No | Whether the token is valid; boolean value of true or false |
| is_channel_match | boolean | No | Whether the keys Seller used are correctly associated |
| scopes | object | No | The API categories with their corresponding access levels |
| scopes.reports | string | No |  (full_access, view_only, no_access) |
| scopes.item | string | No |  (full_access, view_only, no_access) |
| scopes.shipping | string | No |  (full_access, view_only, no_access) |
| scopes.price | string | No |  (full_access, view_only, no_access) |
| scopes.lagtime | string | No |  (full_access, view_only, no_access) |
| scopes.feeds | string | No |  (full_access, view_only, no_access) |
| scopes.returns | string | No |  (full_access, view_only, no_access) |
| scopes.orders | string | No |  (full_access, view_only, no_access) |
| scopes.rules | string | No |  (full_access, view_only, no_access) |
| scopes.inventory | string | No |  (full_access, view_only, no_access) |
| scopes.content | string | No |  (full_access, view_only, no_access) |
