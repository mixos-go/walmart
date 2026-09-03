---
title: All_items
category: Item_Management
api_name: All_items
method: GET
path: /v3/items
---

**Category:** Item_Management
**API:** All_items

**Method:** GET
**HTTP Path:** https://marketplace.walmartapis.com/v3/items

## API Description
All items

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| nextCursor (query) | string | No | Used for pagination when more than 200 items are retrieved.nextCursor value received in response will be same for all subsequent page requests. |
| sku (query) | string | No | An arbitrary alphanumeric unique ID, specified by the seller, which identifies each item. This will be used by the seller in the XSD file to refer to each item. |
| offset (query) | string | No | The object response to start with, where 0 is the first entity that can be requested. It can only be used when includeDetails is set to true. |
| limit (query) | string | No | The number of entities to be returned. It cannot be more than 50 entities. Use it only when the includeDetails is set to true. |
| lifecycleStatus (query) | string | No | The lifecycle status of an item describes where the item listing is in the overall lifecycle. Examples of allowed values are ACTIVE , ARCHIVED, RETIRED. |
| publishedStatus (query) | string | No | The published status of an item describes where the item is in the submission process. Examples of allowed values are PUBLISHED, UNPUBLISHED. |
| variantGroupId (query) | string | No | Variant Id to retrieve all items with the same variant id |
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
| ItemResponse | array<object> | Yes | Items included in the response list |
| ItemResponse.mart | string | No | The marketplace name. Example: Walmart_US (WALMART_US, WALMART_CA, ASDA_GM, WALMART_MEXICO) |
| ItemResponse.sku | string | No | An arbitrary alphanumeric unique ID, specified by the seller, which identifies each item. |
| ItemResponse.wpid | string | No | The Walmart Product ID assigned by Walmart to the item when listed on Walmart.com |
| ItemResponse.upc | string | No | The 12-digit bar code used extensively for retail packaging in the United States |
| ItemResponse.gtin | string | No | The GTIN-compatible Product ID (i.e. UPC or EAN). UPCs must be 12 or 14 digitis in length. EANs must be 13 digits in length. |
| ItemResponse.productName | string | No | A seller-specified, alphanumeric string uniquely identifying the product name. Example: 'Sterling Silver Blue Diamond Heart Pendant with 18in Chain' |
| ItemResponse.shelf | string | No | Walmart assigned an item shelf name |
| ItemResponse.productType | string | No | A seller-specified, alphanumeric string uniquely identifying the Product Type. Example: 'Diamond' |
| ItemResponse.price | object | No | Specifies item purchase price information, including currency and amount. |
| ItemResponse.price.currency | string | No | The currency type. Example: USD for US Dollars (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| ItemResponse.price.amount | number | No | The numerical amount of the price. Example: 9.99 |
| ItemResponse.publishedStatus | string | No | The status of an item when the item is in the submission process. The status can be one of the following: PUBLISHED, READY_TO_PUBLISH, IN_PROGRESS, UNPUBLISHED, STAGE, or SYSTEM_PROBLEM. |
| ItemResponse.additionalAttributes | object | No | Bag of additional attributes |
| ItemResponse.additionalAttributes.nameValueAttribute | array<object> | No |  |
| ItemResponse.additionalAttributes.nameValueAttribute.name | string | No |  |
| ItemResponse.additionalAttributes.nameValueAttribute.type | string | No |  (LOCALIZABLE_TEXT, STRING, BOOLEAN, INTEGER, DECIMAL, DATE, TIMESTAMP) |
| ItemResponse.additionalAttributes.nameValueAttribute.isVariant | boolean | No |  |
| ItemResponse.additionalAttributes.nameValueAttribute.variantResourceType | string | No |  |
| ItemResponse.additionalAttributes.nameValueAttribute.value | array<object> | No |  |
| ItemResponse.additionalAttributes.nameValueAttribute.value.value | string | No |  |
| ItemResponse.additionalAttributes.nameValueAttribute.value.group | string | No |  |
| ItemResponse.additionalAttributes.nameValueAttribute.value.source | string | No |  |
| ItemResponse.additionalAttributes.nameValueAttribute.value.rank | integer | No |  |
| ItemResponse.additionalAttributes.nameValueAttribute.value.isVariant | boolean | No |  |
| ItemResponse.unpublishedReasons | object | No | It outlines the reason for an item when unpublished ,that is, when 'publishedStatus' is set to 'UNPUBLISHED'. |
| ItemResponse.unpublishedReasons.reason | array<string> | No |  |
| ItemResponse.lifecycleStatus | string | No | The lifecycle status of an item describes where the item listing is in the overall lifecycle. Examples of allowed values are ACTIVE , ARCHIVED, RETIRED. |
| ItemResponse.variantGroupId | string | No | Variant Id if the item is of type Variant |
| ItemResponse.variantGroupInfo | object | No | Additional variant group information if the item is of type Variant |
| ItemResponse.variantGroupInfo.isPrimary | boolean | No | Returns true if the item is a primary variant |
| ItemResponse.variantGroupInfo.groupingAttributes | object | No | The list of variant attributes used to create the variant item |
| ItemResponse.variantGroupInfo.groupingAttributes.name | string | No | Returns true if the item is a primary variant |
| ItemResponse.variantGroupInfo.groupingAttributes.value | string | No | The list of variant attributes used to create the variant item |
| ItemResponse.variantGroupInfo.primary | boolean | No |  |
| additionalAttributes | object | No | Bag of additional attributes |
| additionalAttributes.nameValueAttribute | array<object> | No |  |
| additionalAttributes.nameValueAttribute.name | string | No |  |
| additionalAttributes.nameValueAttribute.type | string | No |  (LOCALIZABLE_TEXT, STRING, BOOLEAN, INTEGER, DECIMAL, DATE, TIMESTAMP) |
| additionalAttributes.nameValueAttribute.isVariant | boolean | No |  |
| additionalAttributes.nameValueAttribute.variantResourceType | string | No |  |
| additionalAttributes.nameValueAttribute.value | array<object> | No |  |
| additionalAttributes.nameValueAttribute.value.value | string | No |  |
| additionalAttributes.nameValueAttribute.value.group | string | No |  |
| additionalAttributes.nameValueAttribute.value.source | string | No |  |
| additionalAttributes.nameValueAttribute.value.rank | integer | No |  |
| additionalAttributes.nameValueAttribute.value.isVariant | boolean | No |  |
| totalItems | integer | No | Total items for the query |
| nextCursor | string | No | Used for pagination to fetch the next set of items |
