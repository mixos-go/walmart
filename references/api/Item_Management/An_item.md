---
title: An_item
category: Item_Management
api_name: An_item
method: GET
path: /v3/items/{id}
---

**Category:** Item_Management
**API:** An_item

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/items/{id}

## API Description
An item

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| id (path) | string | Yes | Represents the seller-specified unique ID for each item. Takes SKU code by default. If you require more specific item codes, such as GTIN, UPC, ISBN, EAN, or ITEM_ID, you need to use the productIdType query parameter and specify the desired code e.g. productIdType=GTIN. |
| productIdType (query) | string | Yes | Item code type specifier allows to filter by specific code type, (e.g. GTIN). |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| responseRecord | object | No |  |
| responseRecord.mart | string | No | The marketplace name. Example: Walmart_US (WALMART_US, WALMART_CA, ASDA_GM, WALMART_MEXICO) |
| responseRecord.sku | string | No | An arbitrary alphanumeric unique ID, specified by the seller, which identifies each item. |
| responseRecord.wpid | string | No | The Walmart Product ID assigned by Walmart to the item when listed on Walmart.com |
| responseRecord.upc | string | No | The 12-digit bar code used extensively for retail packaging in the United States |
| responseRecord.gtin | string | No | The GTIN-compatible Product ID (i.e. UPC or EAN). UPCs must be 12 or 14 digitis in length. EANs must be 13 digits in length. |
| responseRecord.productName | string | No | A seller-specified, alphanumeric string uniquely identifying the product name. Example: 'Sterling Silver Blue Diamond Heart Pendant with 18in Chain' |
| responseRecord.shelf | string | No | Walmart assigned an item shelf name |
| responseRecord.productType | string | No | A seller-specified, alphanumeric string uniquely identifying the Product Type. Example: 'Diamond' |
| responseRecord.price | object | No | Specifies item purchase price information, including currency and amount. |
| responseRecord.price.currency | string | No | The currency type. Example: USD for US Dollars (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| responseRecord.price.amount | number | No | The numerical amount of the price. Example: 9.99 |
| responseRecord.publishedStatus | string | No | The status of an item when the item is in the submission process. The status can be one of the following: PUBLISHED, READY_TO_PUBLISH, IN_PROGRESS, UNPUBLISHED, STAGE, or SYSTEM_PROBLEM. |
| responseRecord.additionalAttributes | object | No | Bag of additional attributes |
| responseRecord.additionalAttributes.nameValueAttribute | array<object> | No |  |
| responseRecord.additionalAttributes.nameValueAttribute.name | string | No |  |
| responseRecord.additionalAttributes.nameValueAttribute.type | string | No |  (LOCALIZABLE_TEXT, STRING, BOOLEAN, INTEGER, DECIMAL, DATE, TIMESTAMP) |
| responseRecord.additionalAttributes.nameValueAttribute.isVariant | boolean | No |  |
| responseRecord.additionalAttributes.nameValueAttribute.variantResourceType | string | No |  |
| responseRecord.additionalAttributes.nameValueAttribute.value | array<object> | No |  |
| responseRecord.additionalAttributes.nameValueAttribute.value.value | string | No |  |
| responseRecord.additionalAttributes.nameValueAttribute.value.group | string | No |  |
| responseRecord.additionalAttributes.nameValueAttribute.value.source | string | No |  |
| responseRecord.additionalAttributes.nameValueAttribute.value.rank | integer | No |  |
| responseRecord.additionalAttributes.nameValueAttribute.value.isVariant | boolean | No |  |
| responseRecord.unpublishedReasons | object | No | It outlines the reason for an item when unpublished ,that is, when 'publishedStatus' is set to 'UNPUBLISHED'. |
| responseRecord.unpublishedReasons.reason | array<string> | No |  |
| responseRecord.lifecycleStatus | string | No | The lifecycle status of an item describes where the item listing is in the overall lifecycle. Examples of allowed values are ACTIVE , ARCHIVED, RETIRED. |
