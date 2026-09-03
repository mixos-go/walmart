---
title: Update_Shipping_Templates
category: Settings_Management
api_name: Update_Shipping_Templates
method: PUT
path: /v3/settings/shipping/templates/{templateId}
---

**Category:** Settings_Management
**API:** Update_Shipping_Templates

**Method:** PUT
**HTTP Path:** https://marketplace.walmartapis.com/v3/settings/shipping/templates/{templateId}

## API Description
Update Shipping Templates

## Request Parameters
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| templateId (path) | string | Yes | templateId |
| Authorization (header) | string | Yes | Basic authorization header. Base 64 encodes the Client ID and Client Secret retrieved in step two of the integration steps. |
| WM_SEC.ACCESS_TOKEN (header) | string | Yes | The access token retrieved in the Token API call |
| WM_CONSUMER.CHANNEL.TYPE (header) | string | No | A unique ID to track the consumer request by channel. Use the Consumer Channel Type received during onboarding |
| WM_QOS.CORRELATION_ID (header) | string | Yes | A unique ID which identifies each API call and used to track and debug issues; use a random generated GUID for this ID |
| WM_SVC.NAME (header) | string | Yes | Walmart Service Name |

## Request Body
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| name | string | Yes | Shipping Template Name |
| type | string | Yes | Shipping Template Type, should be CUSTOM or 3PL Specific (DEFAULT, CUSTOM, DELIVERR) |
| rateModelType | string | Yes | This is the shipping model type. TIERED_PRICING: This model means that you charge shipping based on the price of the item PER_SHIPMENT_PRICING: This model means that you charge shipping based on the weight of your items (per pound), or you charge shipping based on the number of items purchased in an (TIERED_PRICING, PER_SHIPMENT_PRICING) |
| status | string | Yes | Shipping Template Status, Can be ACTIVE or INACTIVE status (ACTIVE, INACTIVE) |
| shippingMethods | array<object> | Yes | Array of different ship methods of a Shipping Template |
| shippingMethods.shipMethod | string | No | \| Attribute \| Description \| Data Type \| \| ---- \| ----------------- \| ------- \| \| VALUE \| All Marketplace Sellers must offer Value shipping to Walmart.com customers for items that can't ship within expected transit times for standard shipping. \| string \| \| STANDARD \| You are required to offer standar (VALUE, STANDARD, THREE_DAY, TWO_DAY, FREIGHT) |
| shippingMethods.status | string | No | Shipping Method Status, Can be ACTIVE or INACTIVE status (ACTIVE, INACTIVE) |
| shippingMethods.configurations | array<object> | No | Contains an array of Regions, an array of Address Type, Transit Time and Per shipping charge or array of Tired Shipping Charge |
| shippingMethods.configurations.regions | array<object> | No | Supported Regions includes 48 State Street, 48 State – Street Po Box/Street, AK and HI – Street etc |
| shippingMethods.configurations.regions.regionCode | string | No |  |
| shippingMethods.configurations.regions.regionName | string | No |  |
| shippingMethods.configurations.regions.subRegions | array<object> | No |  |
| shippingMethods.configurations.regions.subRegions.subRegionCode | string | No |  |
| shippingMethods.configurations.regions.subRegions.subRegionName | string | No |  |
| shippingMethods.configurations.regions.subRegions.states | array<object> | No |  |
| shippingMethods.configurations.regions.subRegions.states.stateCode | string | No |  |
| shippingMethods.configurations.regions.subRegions.states.stateName | string | No |  |
| shippingMethods.configurations.regions.subRegions.states.stateSubregions | array<object> | No |  |
| shippingMethods.configurations.regions.subRegions.states.stateSubregions.stateSubregionCode | string | No |  |
| shippingMethods.configurations.regions.subRegions.states.stateSubregions.stateSubregionName | string | No |  |
| shippingMethods.configurations.addressTypes | array<string> | No | Supported address types like PO_BOX STREET MILITARY |
| shippingMethods.configurations.transitTime | integer | No | Time in transit |
| shippingMethods.configurations.perShippingCharge | object | No | Charge per shipping |
| shippingMethods.configurations.perShippingCharge.unitOfMeasure | string | No | Unit of Measure eg. LB |
| shippingMethods.configurations.perShippingCharge.shippingAndHandling | object | No | Shipping and Handling Charge |
| shippingMethods.configurations.perShippingCharge.shippingAndHandling.amount | number | No | The numerical amount for that charge. Example: 9.99 |
| shippingMethods.configurations.perShippingCharge.shippingAndHandling.currency | string | No | The type of currency for the charge. Example: USD for US Dollars |
| shippingMethods.configurations.perShippingCharge.chargePerWeight | object | No | Per Item Charge |
| shippingMethods.configurations.perShippingCharge.chargePerWeight.amount | number | No | Charge Per weight, value USD |
| shippingMethods.configurations.perShippingCharge.chargePerWeight.currency | string | No | Currency, eg. USD |
| shippingMethods.configurations.perShippingCharge.chargePerItem | object | No | Per Weight Charge |
| shippingMethods.configurations.perShippingCharge.chargePerItem.amount | number | No | Charge Per Item, value USD |
| shippingMethods.configurations.perShippingCharge.chargePerItem.currency | string | No | Currency, eg. USD |
| shippingMethods.configurations.tieredShippingCharges | array<object> | No | Tiered Shipping Charges |
| shippingMethods.configurations.tieredShippingCharges.minLimit | number | No | Minimum Limit |
| shippingMethods.configurations.tieredShippingCharges.maxLimit | number | No | Maximum Limit |
| shippingMethods.configurations.tieredShippingCharges.shipCharge | object | No | Details of Shipping Charge |
| shippingMethods.configurations.tieredShippingCharges.shipCharge.amount | number | No | Charge Per Item, value USD |
| shippingMethods.configurations.tieredShippingCharges.shipCharge.currency | string | No | Currency, eg. USD |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| id | string | No | Shipping Template ID |
| name | string | Yes | Shipping Template Name |
| type | string | Yes | Shipping Template Type, should be CUSTOM or 3PL Specific (DEFAULT, CUSTOM, DELIVERR) |
| rateModelType | string | Yes | This is the shipping model type. TIERED_PRICING: This model means that you charge shipping based on the price of the item PER_SHIPMENT_PRICING: This model means that you charge shipping based on the weight of your items (per pound), or you charge shipping based on the number of items purchased in an (TIERED_PRICING, PER_SHIPMENT_PRICING) |
| status | string | Yes | Shipping Template Status, Can be ACTIVE or INACTIVE status (ACTIVE, INACTIVE) |
| shippingMethods | array<object> | Yes | Array of different ship methods of a Shipping Template |
| shippingMethods.shipMethod | string | No | \| Attribute \| Description \| Data Type \| \| ---- \| ----------------- \| ------- \| \| VALUE \| All Marketplace Sellers must offer Value shipping to Walmart.com customers for items that can't ship within expected transit times for standard shipping. \| string \| \| STANDARD \| You are required to offer standar (VALUE, STANDARD, THREE_DAY, TWO_DAY, FREIGHT) |
| shippingMethods.status | string | No | Shipping Method Status, Can be ACTIVE or INACTIVE status (ACTIVE, INACTIVE) |
| shippingMethods.configurations | array<object> | No | Contains an array of Regions, an array of Address Type, Transit Time and Per shipping charge or array of Tired Shipping Charge |
| shippingMethods.configurations.regions | array<object> | No | Supported Regions includes 48 State Street, 48 State – Street Po Box/Street, AK and HI – Street etc |
| shippingMethods.configurations.regions.regionCode | string | No |  |
| shippingMethods.configurations.regions.regionName | string | No |  |
| shippingMethods.configurations.regions.subRegions | array<object> | No |  |
| shippingMethods.configurations.regions.subRegions.subRegionCode | string | No |  |
| shippingMethods.configurations.regions.subRegions.subRegionName | string | No |  |
| shippingMethods.configurations.regions.subRegions.states | array<object> | No |  |
| shippingMethods.configurations.regions.subRegions.states.stateCode | string | No |  |
| shippingMethods.configurations.regions.subRegions.states.stateName | string | No |  |
| shippingMethods.configurations.regions.subRegions.states.stateSubregions | array<object> | No |  |
| shippingMethods.configurations.regions.subRegions.states.stateSubregions.stateSubregionCode | string | No |  |
| shippingMethods.configurations.regions.subRegions.states.stateSubregions.stateSubregionName | string | No |  |
| shippingMethods.configurations.addressTypes | array<string> | No | Supported address types like PO_BOX STREET MILITARY |
| shippingMethods.configurations.transitTime | integer | No | Time in transit |
| shippingMethods.configurations.perShippingCharge | object | No | Charge per shipping |
| shippingMethods.configurations.perShippingCharge.unitOfMeasure | string | No | Unit of Measure eg. LB |
| shippingMethods.configurations.perShippingCharge.shippingAndHandling | object | No | Shipping and Handling Charge |
| shippingMethods.configurations.perShippingCharge.shippingAndHandling.amount | number | No | The numerical amount for that charge. Example: 9.99 |
| shippingMethods.configurations.perShippingCharge.shippingAndHandling.currency | string | No | The type of currency for the charge. Example: USD for US Dollars |
| shippingMethods.configurations.perShippingCharge.chargePerWeight | object | No | Per Item Charge |
| shippingMethods.configurations.perShippingCharge.chargePerWeight.amount | number | No | Charge Per weight, value USD |
| shippingMethods.configurations.perShippingCharge.chargePerWeight.currency | string | No | Currency, eg. USD |
| shippingMethods.configurations.perShippingCharge.chargePerItem | object | No | Per Weight Charge |
| shippingMethods.configurations.perShippingCharge.chargePerItem.amount | number | No | Charge Per Item, value USD |
| shippingMethods.configurations.perShippingCharge.chargePerItem.currency | string | No | Currency, eg. USD |
| shippingMethods.configurations.tieredShippingCharges | array<object> | No | Tiered Shipping Charges |
| shippingMethods.configurations.tieredShippingCharges.minLimit | number | No | Minimum Limit |
| shippingMethods.configurations.tieredShippingCharges.maxLimit | number | No | Maximum Limit |
| shippingMethods.configurations.tieredShippingCharges.shipCharge | object | No | Details of Shipping Charge |
| shippingMethods.configurations.tieredShippingCharges.shipCharge.amount | number | No | Charge Per Item, value USD |
| shippingMethods.configurations.tieredShippingCharges.shipCharge.currency | string | No | Currency, eg. USD |
| createdBy | string | No |  |
| modifiedBy | string | No |  |
| createdDate | number | No |  |
| modifiedDate | number | No |  |
