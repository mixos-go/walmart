---
title: Seller_Listing_Quality_Score
category: Insights_Management
api_name: Seller_Listing_Quality_Score
method: GET
path: /v3/insights/items/listingQuality/score
---

**Category:** Insights_Management
**API:** Seller_Listing_Quality_Score

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/insights/items/listingQuality/score

## API Description
Seller Listing Quality Score

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| viewTrendingItems (query) | boolean | No | Specify whether or not to include seller's items that are trending in the Listing Quality Score. |
| wfsFlag (query) | string | No | Specify whether or not to include WFS-eligible items in the overall Listing Quality Score. |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| payload | object | No |  |
| payload.overAllQuality | number | No | Over All Quality |
| payload.score | object | No | Score |
| payload.score.offerScore | number | No | Offer Score |
| payload.score.contentScore | number | No | Content Score |
| payload.score.ratingReviewScore | number | No | Rating Review Score |
| payload.postPurchaseQuality | object | No | Post Purchase Quality |
| payload.postPurchaseQuality.defectRatio | integer | No | Defect Ratio |
| payload.postPurchaseQuality.itemDefectCnt | integer | No | Item Defect Count |
