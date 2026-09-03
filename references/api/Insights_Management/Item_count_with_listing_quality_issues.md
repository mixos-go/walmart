---
title: Item_count_with_listing_quality_issues
category: Insights_Management
api_name: Item_count_with_listing_quality_issues
method: GET
path: /v3/insights/items/listingQuality/count
---

**Category:** Insights_Management
**API:** Item_count_with_listing_quality_issues

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/insights/items/listingQuality/count

## API Description
Item count with listing quality issues

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| viewTrendingItems (query) | boolean | No | Specify whether or not to include seller's items that are trending in the Listing Quality Score. |
| wfsFlag (query) | boolean | No | Specify whether or not to include WFS-eligible items in the overall Listing Quality Score. |
| hasIssue (query) | integer | No | Specify whether or not to include items that have issues in the Listing Quality Score. |
| type (query) | string | No | Specify whether to get item count by brand or category. Category is the default value when no type is specified. |
| limit (query) | integer | No | Specify number of items to return. The value is defaulted to 100 and the maximum value is 1000. |
| offset (query) | integer | No | Specify the offset of item list to be returned. |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| payload | array<object> | No |  |
| payload.name | string | No |  |
| payload.count | integer | No |  |
| payload.productType | array<object> | No | productType is only applicable for categories |
| payload.productType.name | string | No |  |
| payload.productType.count | integer | No |  |
