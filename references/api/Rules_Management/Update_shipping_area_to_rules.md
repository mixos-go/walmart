---
title: Update_shipping_area_to_rules
category: Rules_Management
api_name: Update_shipping_area_to_rules
method: PUT
path: /v3/rules/actions
---

**Category:** Rules_Management
**API:** Update_shipping_area_to_rules

**Method:** PUT
**HTTP Path:** https://marketplace.walmartapis.com/v3/rules/actions

## API Description
Update shipping area to rules

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| ruleHeader | object | No |  |
| ruleHeader.version | string | No |  |
| rules | object | No |  |
| rules.ruleId | string | No | Unique identifier of the rule created for custom rule assortment. |
| rules.ruleStatus | string | No | Status of the rule post the rule creation. Allowed values are Active, Inactive, Submitted. |
| rules.actions | array<object> | No | Defines the two day state coverage areas. |
| rules.actions.twoDayShippingRegions | array<object> | No | List of two-day regions. |
| rules.actions.twoDayShippingRegions.regionCode | string | No | regionCode |
| rules.actions.twoDayShippingRegions.subRegions | array<object> | No |  |
| rules.actions.twoDayShippingRegions.subRegions.subRegionCode | string | No | subRegionCode |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| rules | array<object> | No |  |
| rules.conditions | array<object> | No | Seller creates conditions while defining the custom rule assortment.There are three condition which a seller can use : subCategories, price, weight. |
| rules.conditions.name | string | No | Name of the rule created for custom rule assortment. |
| rules.conditions.operator | string | No | Seller uses operator while defining conditions in the rule. Operators allowed for condition price and weight: EQUALS, GREATER_THAN, LESS_THAN,GREATER_THAN_OR_EQUALS,LESS_THAN_OR_EQUALS. and for condition subcategories : IN . |
| rules.conditions.value | string | No | Values for each condition. Value can be a comma separated strings for subcategories and numerical value for price and weight. |
| rules.description | string | No | Description of the rule created for custom rule assortment. |
| rules.name | string | No | Name of the rule created for custom rule assortment. |
| rules.priority | string | No | Priority of the rule created for custom rule assortment. |
| rules.ruleId | string | No | Unique identifier of the rule created for custom rule assortment. |
| rules.ruleStatus | string | No | Status of the rule post the rule creation. Allowed values are Active, Inactive, Submitted. |
| rules.skuProcessingStatus | string | No | When the rule gets activated, skuProcessingStatus represents the state of all items being processed for two-day. The two values for skuProcessingStatus are Processing and Completed. |
| rules.ruleAction | object | No | Defines the two day state coverage areas. |
| rules.ruleAction.twoDayShippingRegions | array<object> | No | List of two-day regions. |
| rules.ruleAction.twoDayShippingRegions.regionCode | string | No | regionCode |
| rules.ruleAction.twoDayShippingRegions.subRegions | array<object> | No |  |
| rules.ruleAction.twoDayShippingRegions.subRegions.subRegionCode | string | No | subRegionCode |
| status | string | No | status |
