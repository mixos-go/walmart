---
title: Promotional_prices
category: Promotion_Management
api_name: Promotional_prices
method: GET
path: /v3/promo/sku/{sku}
---

**Category:** Promotion_Management
**API:** Promotional_prices

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/promo/sku/{sku}

## API Description
Promotional prices

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| sku (path) | string | Yes | An arbitrary alphanumeric unique ID, specified by the seller, which identifies each item. This will be used by the seller in the XSD file to refer to each item. Special characters in the sku needing encoding are: ':', '/', '?', '#', '[', ']', '@', '!', '$', '&', "'", '(', ')', '*', '+', ',', ';', '= |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| payload | object | No |  |
| payload.itemIdentifier | object | No |  |
| payload.itemIdentifier.sku | string | No |  |
| payload.itemIdentifier.offerId | string | No |  |
| payload.itemIdentifier.itemId | string | No |  |
| payload.itemIdentifier.wpid | string | No |  |
| payload.itemIdentifier.productType | string | No |  |
| payload.pricingList | object | No |  |
| payload.pricingList.replaceAll | boolean | No |  |
| payload.pricingList.pricing | array<object> | No |  |
| payload.pricingList.pricing.currentPrice | object | No |  |
| payload.pricingList.pricing.currentPrice.value | object | No |  |
| payload.pricingList.pricing.currentPrice.value.value | string | No |  |
| payload.pricingList.pricing.currentPrice.value.currency | string | No |  |
| payload.pricingList.pricing.currentPrice.value.amount | number | No |  |
| payload.pricingList.pricing.currentPrice.uomType | string | No |  |
| payload.pricingList.pricing.currentPrice.minValue | object | No |  |
| payload.pricingList.pricing.currentPrice.minValue.value | string | No |  |
| payload.pricingList.pricing.currentPrice.minValue.currency | string | No |  |
| payload.pricingList.pricing.currentPrice.minValue.amount | number | No |  |
| payload.pricingList.pricing.currentPrice.maxValue | object | No |  |
| payload.pricingList.pricing.currentPrice.maxValue.value | string | No |  |
| payload.pricingList.pricing.currentPrice.maxValue.currency | string | No |  |
| payload.pricingList.pricing.currentPrice.maxValue.amount | number | No |  |
| payload.pricingList.pricing.currentPrice.perUnitValue | object | No |  |
| payload.pricingList.pricing.currentPrice.perUnitValue.value | string | No |  |
| payload.pricingList.pricing.currentPrice.perUnitValue.currency | string | No |  |
| payload.pricingList.pricing.currentPrice.perUnitValue.amount | number | No |  |
| payload.pricingList.pricing.currentPrice.minUnitValue | object | No |  |
| payload.pricingList.pricing.currentPrice.minUnitValue.value | string | No |  |
| payload.pricingList.pricing.currentPrice.minUnitValue.currency | string | No |  |
| payload.pricingList.pricing.currentPrice.minUnitValue.amount | number | No |  |
| payload.pricingList.pricing.currentPrice.maxUnitValue | object | No |  |
| payload.pricingList.pricing.currentPrice.maxUnitValue.value | string | No |  |
| payload.pricingList.pricing.currentPrice.maxUnitValue.currency | string | No |  |
| payload.pricingList.pricing.currentPrice.maxUnitValue.amount | number | No |  |
| payload.pricingList.pricing.currentPriceType | string | No |  (BASE, REDUCED, SAVINGS_AMT, SAVINGS_PCT, ROLLBACK, CLEARANCE, LIST_PRICE) |
| payload.pricingList.pricing.comparisonPrice | object | No |  |
| payload.pricingList.pricing.comparisonPrice.value | object | No |  |
| payload.pricingList.pricing.comparisonPrice.value.value | string | No |  |
| payload.pricingList.pricing.comparisonPrice.value.currency | string | No |  |
| payload.pricingList.pricing.comparisonPrice.value.amount | number | No |  |
| payload.pricingList.pricing.comparisonPrice.uomType | string | No |  |
| payload.pricingList.pricing.comparisonPrice.minValue | object | No |  |
| payload.pricingList.pricing.comparisonPrice.minValue.value | string | No |  |
| payload.pricingList.pricing.comparisonPrice.minValue.currency | string | No |  |
| payload.pricingList.pricing.comparisonPrice.minValue.amount | number | No |  |
| payload.pricingList.pricing.comparisonPrice.maxValue | object | No |  |
| payload.pricingList.pricing.comparisonPrice.maxValue.value | string | No |  |
| payload.pricingList.pricing.comparisonPrice.maxValue.currency | string | No |  |
| payload.pricingList.pricing.comparisonPrice.maxValue.amount | number | No |  |
| payload.pricingList.pricing.comparisonPrice.perUnitValue | object | No |  |
| payload.pricingList.pricing.comparisonPrice.perUnitValue.value | string | No |  |
| payload.pricingList.pricing.comparisonPrice.perUnitValue.currency | string | No |  |
| payload.pricingList.pricing.comparisonPrice.perUnitValue.amount | number | No |  |
| payload.pricingList.pricing.comparisonPrice.minUnitValue | object | No |  |
| payload.pricingList.pricing.comparisonPrice.minUnitValue.value | string | No |  |
| payload.pricingList.pricing.comparisonPrice.minUnitValue.currency | string | No |  |
| payload.pricingList.pricing.comparisonPrice.minUnitValue.amount | number | No |  |
| payload.pricingList.pricing.comparisonPrice.maxUnitValue | object | No |  |
| payload.pricingList.pricing.comparisonPrice.maxUnitValue.value | string | No |  |
| payload.pricingList.pricing.comparisonPrice.maxUnitValue.currency | string | No |  |
| payload.pricingList.pricing.comparisonPrice.maxUnitValue.amount | number | No |  |
| payload.pricingList.pricing.comparisonPriceType | string | No |  (BASE, REDUCED, SAVINGS_AMT, SAVINGS_PCT, ROLLBACK, CLEARANCE, LIST_PRICE) |
| payload.pricingList.pricing.savingsAmount | number | No |  |
| payload.pricingList.pricing.savingsPercent | number | No |  |
| payload.pricingList.pricing.priceDisplayCodes | object | No |  |
| payload.pricingList.pricing.priceDisplayCodes.isClearance | boolean | No |  |
| payload.pricingList.pricing.priceDisplayCodes.hidePriceForSOI | object | No |  |
| payload.pricingList.pricing.priceDisplayCodes.submapType | object | No |  |
| payload.pricingList.pricing.priceDisplayCodes.isRollback | boolean | No |  |
| payload.pricingList.pricing.priceDisplayCodes.isReducedPrice | boolean | No |  |
| payload.pricingList.pricing.priceDisplayCodes.isEligibleForAssociateDiscount | object | No |  |
| payload.pricingList.pricing.priceDisplayCodes.isStrikethrough | boolean | No |  |
| payload.pricingList.pricing.pickupDiscount | object | No |  |
| payload.pricingList.pricing.pickupDiscount.isPickUpDiscountEligible | boolean | No |  |
| payload.pricingList.pricing.pickupDiscount.pickupDiscountAmt | object | No |  |
| payload.pricingList.pricing.pickupDiscount.pickupDiscountAmt.value | string | No |  |
| payload.pricingList.pricing.pickupDiscount.pickupDiscountAmt.currency | string | No |  |
| payload.pricingList.pricing.pickupDiscount.pickupDiscountAmt.amount | number | No |  |
| payload.pricingList.pricing.effectiveDate | integer | No |  |
| payload.pricingList.pricing.expirationDate | integer | No |  |
| payload.pricingList.pricing.processMode | string | No |  (UPSERT, DELETE) |
| payload.pricingList.pricing.pid | string | No |  |
| payload.maxSalesRetailPrice | object | No |  |
| payload.maxSalesRetailPrice.value | string | No |  |
| payload.maxSalesRetailPrice.currency | string | No |  |
| payload.maxSalesRetailPrice.amount | number | No |  |
| payload.minAdvtPrice | object | No |  |
| payload.minAdvtPrice.value | string | No |  |
| payload.minAdvtPrice.currency | string | No |  |
| payload.minAdvtPrice.amount | number | No |  |
| payload.rebate | object | No |  |
| payload.rebate.rebateAmt | object | No |  |
| payload.rebate.rebateAmt.value | string | No |  |
| payload.rebate.rebateAmt.currency | string | No |  |
| payload.rebate.rebateAmt.amount | number | No |  |
| payload.rebate.infoUrl | string | No |  |
| payload.rebate.rebateType | string | No |  (AMOUNT, PRODUCT) |
| payload.rebate.startDate | date-time | No |  |
| payload.rebate.endDate | date-time | No |  |
| payload.additionalAttributes | object | No |  |
| payload.additionalAttributes.additionalAttribute | array<object> | No |  |
| payload.additionalAttributes.additionalAttribute.name | string | No |  |
| payload.additionalAttributes.additionalAttribute.value | string | No |  |
| header | object | No |  |
| header.headerAttributes | object | No |  |
| status | string | No |  |
