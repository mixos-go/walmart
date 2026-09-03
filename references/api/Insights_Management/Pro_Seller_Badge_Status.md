---
title: Pro_Seller_Badge_Status
category: Insights_Management
api_name: Pro_Seller_Badge_Status
method: GET
path: /v3/insights/prosellerbadge
---

**Category:** Insights_Management
**API:** Pro_Seller_Badge_Status

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/insights/prosellerbadge

## API Description
Pro Seller Badge Status

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
| hasBadge | boolean | No | Specifies if the seller has the badge |
| isEligible | boolean | No | Specifies if the seller is eligible for the badge in the next refresh |
| badgedSince | date-time | No | Specifies when the seller received their badge |
| isProhibited | boolean | No | Specifies whether the seller is prohibited from participating in the Pro Seller badge program. |
| badgeStatus | string | No | Specifies the seller's badge status in detail. The possible values are "Become a Pro Seller", "You are a Pro Seller", "Pro Seller Badge at risk", "Eligible starting from YYYY-MM-DD", and "Not eligible for the Pro Seller Badge" |
| meetsCriteria | object | No | Shows whether the seller has met the requirements for the badge. |
| meetsCriteria.isOrdersCriteriaMet | boolean | No | Indicates whether the seller has met the minimum number of orders required. |
| meetsCriteria.isDeliveryDefectCriteriaMet | boolean | No | Indicates whether the seller has a low delivery defect, meeting the threshold for the badge. |
| meetsCriteria.isCancellationCriteriaMet | boolean | No | Indicates whether the seller has a low cancellation rate, meeting the threshold for the badge. |
| meetsCriteria.isListingQualityCatalogCriteriaMet | boolean | No | Indicates whether the seller is meeting the trending catalog requirement. |
| meetsCriteria.isActiveDaysCriteriaMet | boolean | No | Indicates whether the seller has met the minimum number of active days required. |
| criteriaData | object | No | Shows the criteria for the Pro Seller badge. |
| criteriaData.orders | integer | No | Number of orders received during the last 90 days. |
| criteriaData.deliveryDefectRate | string | No | Delivery Defect rate in the given timeframe. |
| criteriaData.cancellationRate | string | No | Cancellation rate in the given timeframe. |
| criteriaData.listingQualityCatalog | integer | No | Trending Catalog Quality Score coverage. |
| criteriaData.activeDays | integer | No | Days active on the platform. |
| recommendations | object | No | Recommendations on how to increase chances of Pro Seller Badge eligibility |
| recommendations.deliveryDefectRate | string | No | Recommendations on reducing the delivery defect rate |
| recommendations.cancellationRate | string | No | Recommendations on reducing the Cancellation rate |
| recommendations.listingQualityCatalog | string | No | Recommendations on increasing the trending item catalog coverage |
