---
title: Catalog_Search
category: Item_Management
api_name: Catalog_Search
method: POST
path: /v3/items/catalog/search
---

**Category:** Item_Management
**API:** Catalog_Search

**Method:** POST
**HTTP Path:** https://marketplace.walmartapis.com/v3/items/catalog/search

## API Description
Catalog Search

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| page (query) | integer | No | number of page |
| limit (query) | integer | No | number of items |
| nextCursor (query) | string | No | nextCursor |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| query | object | No |  |
| query.field | string | No | \| Attribute \| Description \| Data Type \| --- \| ----------- \| ------- \| productName \| Product Name, can do white card search \| string \| \| sku \| An arbitrary alphanumeric unique ID, seller-specified, identifying each item \| string \| \| gtin \| Specifies a Global Trade Item Number (GTIN) search. GTIN must (productName, sku, gtin, wpid, upc, isbn, ean, itemId) |
| query.value | string | No |  |
| filters | array<object> | No |  |
| filters.field | string | No | \| Attribute \| Description \| Data Type \| --- \| ----------- \| ------- \| num_reviews \| The reviewed times for Items \| string \| \| customerRating \| Customer rating \| string \| \| lifecycleStatus \| The lifecycle status of an item describes where the item listing is in the overall lifecycle \| string \| \| publ (num_reviews, customerRating, lifecycleStatus, publishedStatus, unpublishedReasons, inventoryStatus, price, fulfillmentType) |
| filters.op | string | No |  (equals, between, greater_than, less_than) |
| filters.values | array<string> | No |  |
| sort | object | No |  |
| sort.field | string | No | \| Attribute \| Description \| Data Type \| --- \| ----------- \| ------- \| num_reviews \| The revied number for Items \| string \| \| customerRating \| An arbitrary alphanumeric unique ID, seller-specified, identifying each item \| string \| \| lifecycleStatus \| The lifecycle status of an item describes where th (num_reviews, customerRating, lifecycleStatus, publishedStatus, unpublishedReasons, inventoryStatus) |
| sort.order | string | No |  (ASC, DESC) |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| status | string | No | Response Status |
| payload | array<object> | No | Items included in the response list |
| payload.mart | string | No | The marketplace name. Example: Walmart_US (WALMART_US, WALMART_CA, ASDA_GM, WALMART_MEXICO) |
| payload.sku | string | No | An arbitrary alphanumeric unique ID, specified by the seller, which identifies each item. |
| payload.wpid | string | No | The Walmart Product ID assigned by Walmart to the item when listed on Walmart.com |
| payload.upc | string | No | The 12-digit bar code used extensively for retail packaging in the United States |
| payload.isbn | string | No | International Standard Book Number |
| payload.ean | string | No | Product ID, EANs must be 13 digits in length. |
| payload.gtin | string | No | The GTIN-compatible Product ID (i.e. UPC or EAN). UPCs must be 12 or 14 digitis in length. EANs must be 13 digits in length. |
| payload.itemId | string | No | A unique Id which identifies the item. |
| payload.productName | string | No | A seller-specified, alphanumeric string uniquely identifying the product name. Example: 'Sterling Silver Blue Diamond Heart Pendant with 18in Chain' |
| payload.shelf | string | No | Walmart assigned an item shelf name |
| payload.productType | string | No | A seller-specified, alphanumeric string uniquely identifying the Product Type. Example: 'Diamond' |
| payload.price | object | No | Specifies item purchase price information, including currency and amount. |
| payload.price.unit | string | No | The currency type. Example: USD for US Dollars (AED, AFN, ALL, AMD, ANG, AOA, ARS, AUD, AWG, AZN, BAM, BBD, BDT, BGN, BHD, BIF, BMD, BND, BOB, BRL, BSD, BTN, BWP, BYR, BZD, CAD, CDF, CHF, CLP, CNY, COP, CRC, CUP, CVE, CZK, DJF, DKK, DOP, DZD, EGP, ERN, ETB, EUR, FJD, FKP, GBP, GEL, GHS, GIP, GMD, GNF, GTQ, GYD, HKD, HNL, HRK, HTG, HUF, IDR, ILS, INR, IQD, IRR, ISK, JMD, JOD, JPY, KES, KGS, KHR, KMF, KPW, KRW, KWD, KYD, KZT, LAK, LBP, LKR, LRD, LSL, LTL, LVL, LYD, MAD, MDL, MGA, MKD, MMK, MNT, MOP, MRO, MUR, MVR, MWK, MXN, MYR, MZN, NAD, NGN, NIO, NOK, NPR, NZD, OMR, PAB, PEN, PGK, PHP, PKR, PLN, PYG, QAR, RON, RSD, RUB, RUR, RWF, SAR, SBD, SCR, SDG, SEK, SGD, SHP, SLL, SOS, SRD, STD, SYP, SZL, THB, TJS, TMT, TND, TOP, TRY, TTD, TWD, TZS, UAH, UGX, USD, UYU, UZS, VEF, VND, VUV, WST, XAF, XAG, XAU, XBA, XBB, XBC, XBD, XCD, XDR, XFU, XOF, XPD, XPF, XPT, XTS, XXX, YER, ZAR, ZMK, ZWL) |
| payload.price.amount | number | No | The numerical amount of the price. Example: 9.99 |
| payload.brand | string | No | Brand of Item. |
| payload.num_reviews | string | No | The reviewed times for Items. |
| payload.customerRating | string | No | Customer rating. |
| payload.manufacturer | string | No | manufacturer of Item. |
| payload.fulfillmentType | string | No | Fulfillment information. |
| payload.publishedStatus | object | No | The status of an item when the item is in the submission process. The status can be one of the following: PUBLISHED, READY_TO_PUBLISH, IN_PROGRESS, UNPUBLISHED, STAGE, or SYSTEM_PROBLEM. |
| payload.publishedStatus.status | string | No | An arbitrary alphanumeric unique ID, specified by the seller, which identifies each item. |
| payload.publishedStatus.reasons | array<string> | No | The Walmart Product ID assigned by Walmart to the item when listed on Walmart.com |
| payload.inventoryStatus | string | No | It indicates whether the product is in stock or not. |
| payload.lifecycleStatus | string | No | The lifecycle status of an item describes where the item listing is in the overall lifecycle. Examples of allowed values are ACTIVE , ARCHIVED, RETIRED. |
| payload.shop_ref | string | No |  |
| payload.shop_product_id | string | No |  |
| payload.shop_variant_id | string | No |  |
| payload.variantGroupId | string | No | Variant Id if the item is of type Variant |
| payload.variantGroupInfo | object | No | Additional variant group information if the item is of type Variant |
| payload.variantGroupInfo.isPrimary | boolean | No | Returns true if the item is a primary variant |
| payload.variantGroupInfo.groupingAttributes | object | No | The list of variant attributes used to create the variant item |
| payload.variantGroupInfo.groupingAttributes.name | string | No | Returns true if the item is a primary variant |
| payload.variantGroupInfo.groupingAttributes.value | string | No | The list of variant attributes used to create the variant item |
| payload.variantGroupInfo.primary | boolean | No |  |
| totalItems | integer | No | Total items for the query |
| limit | integer | No | Number of items shown in this page |
| nextCursor | string | No | Used for pagination to fetch the next set of items |
| statuss | string | No |  |
