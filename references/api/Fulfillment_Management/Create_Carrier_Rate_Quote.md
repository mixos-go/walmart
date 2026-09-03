---
title: Create_Carrier_Rate_Quote
category: Fulfillment_Management
api_name: Create_Carrier_Rate_Quote
method: POST
path: /v3/fulfillment/carrier-rate-quotes
---

**Category:** Fulfillment_Management
**API:** Create_Carrier_Rate_Quote

**Method:** POST
**HTTP Path:** https://marketplace.walmartapis.com/v3/fulfillment/carrier-rate-quotes

## API Description
Create Carrier Rate Quote

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
| shipmentId | string | Yes |  |
| shipmentSource | string | Yes |  |
| pickupFromDateTime | date-time | No |  |
| pickupToDateTime | date-time | No |  |
| deliveryFromDateTime | date-time | No |  |
| deliveryToDateTime | date-time | No |  |
| customer | object | Yes |  |
| customer.customerId | string | No |  |
| customer.customerName | string | No |  |
| originLocation | object | Yes |  |
| originLocation.locationName | string | No |  |
| originLocation.address | object | No |  |
| originLocation.address.addressLine1 | string | No |  |
| originLocation.address.addressLine2 | string | No |  |
| originLocation.address.city | string | No |  |
| originLocation.address.stateCode | string | No |  |
| originLocation.address.countryCode | string | No |  |
| originLocation.address.postalCode | string | No |  |
| originLocation.address.phone | string | No |  |
| originLocation.locationId | string | No |  |
| destinationLocation | object | Yes |  |
| destinationLocation.locationName | string | No |  |
| destinationLocation.address | object | No |  |
| destinationLocation.address.addressLine1 | string | No |  |
| destinationLocation.address.addressLine2 | string | No |  |
| destinationLocation.address.city | string | No |  |
| destinationLocation.address.stateCode | string | No |  |
| destinationLocation.address.countryCode | string | No |  |
| destinationLocation.address.postalCode | string | No |  |
| destinationLocation.address.phone | string | No |  |
| destinationLocation.locationId | string | No |  |
| returnLocation | object | Yes |  |
| returnLocation.locationName | string | No |  |
| returnLocation.address | object | No |  |
| returnLocation.address.addressLine1 | string | No |  |
| returnLocation.address.addressLine2 | string | No |  |
| returnLocation.address.city | string | No |  |
| returnLocation.address.stateCode | string | No |  |
| returnLocation.address.countryCode | string | No |  |
| returnLocation.address.postalCode | string | No |  |
| returnLocation.address.phone | string | No |  |
| shipmentPackages | array<object> | Yes |  |
| shipmentPackages.packageSequenceNumber | integer | No |  |
| shipmentPackages.weight | number | No |  |
| shipmentPackages.weightUOM | string | No |  |
| shipmentPackages.length | number | No |  |
| shipmentPackages.height | number | No |  |
| shipmentPackages.width | number | No |  |
| shipmentPackages.lengthUOM | string | No |  |
| shipmentPackages.labelInformation | object | No |  |
| shipmentPackages.labelInformation.labelData | string | No |  |
| shipmentPackages.labelInformation.labelFormat | string | No |  |
| shipmentPackages.labelInformation.trackingCode | string | No |  |
| shipmentPackages.labelInformation.referenceTrackingCode | string | No |  |
| shipmentPackages.labelInformation.epTrackerId | string | No |  |
| shipmentPackages.labelInformation.shipmentId | string | No |  |
| shipmentPackages.labelInformation.packageAsn | string | No |  |
| shipmentPackages.labelInformation.masterTrackingCode | string | No |  |
| shipmentPackages.labelInformation.master | boolean | No |  |
| shipmentPackages.billingWeight | number | No |  |
| shipmentPackages.netCharge | number | No |  |
| shipmentPackages.nominalCharge | number | No |  |
| shipmentPackages.assessorialCharge | number | No |  |
| shipmentPackages.serviceCharge | number | No |  |
| shipmentPackages.packageType | string | No |  |
| shipmentPackages.noOfPackages | integer | No |  |
| shipmentPackages.stackable | boolean | No |  |
| mode | string | Yes |  |
| freightClass | string | No |  |
| declaredValue | integer | No |  |
| loadTypes | array<object> | No |  |
| loadTypes.count | string | No |  |
| loadTypes.loadType | string | No |  |

## Response
| Field | Type | Required | Description |
| --- | --- | --- | --- |
| shipmentId | string | No |  |
| shipmentNumber | string | No |  |
| rateQuotes | array<object> | No |  |
| rateQuotes.quoteId | string | No |  |
| rateQuotes.estimatedDeliveryDateTime | date-time | No |  |
| rateQuotes.carrier | object | No |  |
| rateQuotes.carrier.carrierId | string | No |  |
| rateQuotes.carrier.carrierName | string | No |  |
| rateQuotes.currency | string | No |  |
| rateQuotes.discountCharge | number | No |  |
| rateQuotes.netCharge | number | No |  |
| rateQuotes.surchargeType | string | No |  |
| rateQuotes.surchargeValue | string | No |  |
| rateQuotes.totalBillingWeight | number | No |  |
| rateQuotes.status | string | No |  |
| rateQuotes.transitDays | string | No |  |
| rateQuotes.effectiveDate | date-time | No |  |
| rateQuotes.expiryDate | date-time | No |  |
| rateQuotes.mode | string | No |  |
| rateQuotes.sellerFreightClassCode | string | No |  |
| rateQuotes.freightCharge | number | No |  |
| rateQuotes.fuelCharge | number | No |  |
| rateQuotes.totalWeight | number | No |  |
| rateQuotes.totalVolume | number | No |  |
| rateQuotes.equipmentTypeCode | string | No |  |
| rateQuotes.serviceCode | string | No |  |
| rateQuotes.numberOfPallets | integer | No |  |
| rateQuotes.nominalCharge | number | No |  |
| rateQuotes.assessorialCharge | number | No |  |
| rateQuotes.serviceCharge | number | No |  |
| rateQuotes.minimumCharge | number | No |  |
| rateQuotes.declaredValue | string | No |  |
| rateQuotes.mixedSKUs | integer | No |  |
| rateQuotes.singleSKUs | integer | No |  |
| rateQuotes.freightReadyDate | date-time | No |  |
