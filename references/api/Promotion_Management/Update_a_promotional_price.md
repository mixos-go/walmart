---
title: Update_a_promotional_price
category: Promotion_Management
api_name: Update_a_promotional_price
method: PUT
path: /v3/price
---

**Category:** Promotion_Management
**API:** Update_a_promotional_price

**Method:** PUT
**HTTP Path:** https://marketplace.walmartapis.com/v3/price

## API Description
Update a promotional price

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| promo (query) | boolean | Yes | The promotional price. Set to 'true' in order to retrieve promotional prices |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| offerId | string | No | This is applicable only for promotions |
| sku | string | Yes |  |
| replaceAll | string | No | This is applicable only for promotions (true, false) |
| pricing | array<object> | Yes |  |
| pricing.effectiveDate | date-time | No | This is applicable only for promotions |
| pricing.expirationDate | date-time | No | This is applicable only for promotions |
| pricing.promoId | string | No | This is applicable only for promotions |
| pricing.processMode | string | No | This is applicable only for promotions (UPSERT, DELETE) |
| pricing.currentPriceType | string | No | This is applicable only for both promotions and price (BASE, REDUCED, CLEARANCE) |
| pricing.currentPrice | object | No |  |
| pricing.currentPrice.currency | string | No |  (USD, CAD) |
| pricing.currentPrice.amount | number | No |  |
| pricing.comparisonPriceType | string | No | This is applicable only for promotions (BASE) |
| pricing.comparisonPrice | object | No | This is applicable only for promotions |
| pricing.comparisonPrice.currency | string | No |  (USD, CAD) |
| pricing.comparisonPrice.amount | number | No |  |
| pricing.priceDisplayCodes | string | No | Represent promo placement. This is applicable only for promotions (CART, CHECKOUT) |
| definitions | object | No |  |

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
| statusCode | integer | No |  |
| mart | string | No | Marketplace name. Example: Walmart-US |
| sku | string | No | An arbitrary alphanumeric unique ID, specified by the seller, which identifies each item. |
| message | string | No | A message of acknowledgement for a price update |
